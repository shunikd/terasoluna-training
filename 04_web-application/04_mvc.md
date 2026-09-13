# MVC

## 1. 概要

前章では、Java Webアプリケーションを構成するServletとJSPについて説明した。

Servletはリクエストの受付や処理制御を担当し、JSPは画面表示を担当する。

このように役割を分離して開発する考え方を体系化した設計パターンがMVC（Model-View-Controller）である。

本章では、Java Webアプリケーションで広く採用されているMVCアーキテクチャについて説明する。

## 2. MVCとは

MVC（Model-View-Controller）とは、アプリケーションの責務を3つの役割に分割する設計パターンである。

画面表示、処理制御、業務ロジックを分離することで、保守性や拡張性の高いシステムを実現できる。

```mermaid
flowchart TD

    Controller[Controller<br>（処理制御）]

    Model[Model<br>（業務ロジック）]

    View[View<br>（画面表示）]

    Controller <--> View

    Controller <--> Model

```

### MVCを構成する要素

MVCは以下の3つの要素で構成される。

| 要素 | 役割 |
|--------|--------|
| Model | 業務ロジックやデータ処理を担当する |
| View | 画面表示を担当する |
| Controller | リクエスト受付や画面遷移制御を担当する |

## 3. Java WebアプリケーションにおけるMVC

Java Webアプリケーションでは、ServletとJSPを利用してMVCを実現することが一般的である。

```mermaid
flowchart TD

    Controller["Servlet"]

    Model["Service<br/>DAO<br/>Entity"]

    View["JSP"]

    Controller <--> View

    Controller <--> Model

```

| MVC | Java Webアプリケーション |
|--------|--------|
| Model | Service、DAO、Entity |
| View | JSP |
| Controller | Servlet |



## 4. MVCでの処理の流れ

利用者が画面へアクセスした場合の処理の流れを示す。

```mermaid
sequenceDiagram

    actor User as 利用者

    participant C as Controller(Servlet)

    participant M as Model(Service/DAO)

    participant V as View(JSP)

    User->>C: HTTP Request

    C->>M: 業務処理依頼

    M-->>C: 処理結果

    C->>V: 画面表示依頼

    V-->>User: HTML Response
```


## 5. Model（業務ロジック）

Modelは業務ロジックやデータ処理を担当する。

例えば以下のような処理はModelに実装される。

- 会員情報取得
- 注文金額計算
- 在庫確認
- ポイント計算
- データベース操作

```mermaid
flowchart LR

    Service[Service]

    DAO[DAO]

    Entity[Entity]

    DB[(Database)]

    Service --> DAO

    DAO --> DB

    DAO --> Entity
```

### Modelの責務

- 業務ルールの実装
- データ加工
- データベースアクセス
- 外部システム連携

### Modelのコード例

```java
@RequestScoped
public class UserService {

    public User findById(Long id) {

        User user = new User();

        user.setName("Taro Yamada");

        return user;
    }
}
```

#### コードポイント

```
public User findById(Long id)
```

利用者情報を取得する業務処理を実装している。

実際のシステムではDAOやJPAを利用してデータベースから取得する。

## 6. View（画面表示）

Viewは利用者へ画面を表示する役割を担当する。

Java Webアプリケーションでは主にJSPが利用される。

```mermaid
flowchart RL

    Data[処理結果]

    JSP[JSP]

    HTML[HTML]

    Browser[Webブラウザ]

    Data --> JSP

    JSP --> HTML

    HTML --> Browser
```

### Viewの責務

- HTML生成
- データ表示
- レイアウト管理
- 画面描画

### Viewが持つべきでない責務

- 業務ロジック
- SQL実行
- データベースアクセス

### Viewのコード例

```java
<html>
<body>
    <h1>ユーザ情報</h1>

    名前：${user.name}
</body>
</html>
```

#### コードポイント

```
${user.name}
```

Controllerから渡されたデータを表示している。

データの表示のみを行い、業務ロジックは実装しない。


## 7. Controller（処理制御）

Controllerは利用者からのリクエストを受け取り、適切な業務処理と画面表示を制御する。

Java Webアプリケーションでは主にServletが担当する。

```mermaid
flowchart LR

    Browser[Webブラウザ]

    Servlet[Servlet]

    Service[Service]

    JSP[JSP]

    Browser --> Servlet

    Servlet --> Service

    Service --> Servlet

    Servlet --> JSP
```

### Controllerの責務

- リクエスト受付
- 入力値取得
- 業務処理呼び出し
- 画面遷移制御
- Viewへのデータ受け渡し

### Controllerのコード例

```java
@WebServlet("/user")
public class UserServlet extends HttpServlet {

    @Inject
    private UserService userService;

    @Override
    protected void doGet(
            HttpServletRequest request,
            HttpServletResponse response)
            throws ServletException, IOException {

        User user = userService.findById(1L);

        request.setAttribute("user", user);

        request.getRequestDispatcher("/user.jsp")
               .forward(request, response);
    }
}
```

#### コードポイント

```
User user = userService.findById(1L);
```
業務ロジックを直接実装するのではなく、ModelであるServiceへ処理を依頼している。


```
request.setAttribute("user", user);
```
画面へ表示するためのデータをViewへ渡している。

```
forward(request, response);
```
表示するJSPを決定している。



## 8. MVCのメリット

MVCを採用することで、各コンポーネントの責務を明確に分離できる。

### メリット

- 保守性が向上する
- 再利用性が向上する
- テストしやすくなる
- 役割分担が明確になる
- 機能追加が容易になる

## 9. MVCを採用しない場合

すべての処理をJSPやServletへ記述すると、業務ロジックと画面表示が混在する。

```mermaid
flowchart LR

    Program["Servlet/JSP
    画面表示
    業務処理
    DBアクセス
    画面遷移"]

    DB[(Database)]

    Program --> DB
```

このような構造では、機能追加や修正時の影響範囲が大きくなり、保守が困難になる。


> [!NOTE]
> ### Coffee Break: MVCはJava以外でも使われる
>
> MVCはJava特有の考え方ではなく、多くのWebフレームワークで採用されている。
>
> 例えば以下のようなフレームワークでもMVCの考え方が利用されている。
>
> - Spring MVC
> - ASP.NET MVC
> - Ruby on Rails
> - Laravel
>
> フレームワークごとに名称や実装方法は異なるが、「画面」「処理制御」「業務ロジック」を分離するという考え方は共通している。

## 10. まとめ

MVCは、アプリケーションをModel、View、Controllerの3つの役割に分割する設計パターンである。

Java Webアプリケーションでは、一般的にServletがController、JSPがView、ServiceやDAOがModelを担当する。

責務を明確に分離することで、保守性・拡張性・再利用性の高いアプリケーションを実現できる。