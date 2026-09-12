# フィールドとメソッド

## この章で学ぶこと

- フィールドとは何かを理解する
- メソッドとは何かを理解する
- クラスの基本構造を理解する
- オブジェクトがデータと処理を持つことを理解する

## フィールドとは

フィールド（Field）とは、クラスが保持するデータである。

例えばユーザクラスを考える。

```text
ユーザ
├─ 名前
├─ 年齢
└─ メールアドレス
```

これらのデータをフィールドとして表現する。

```java
public class User {

    String name;

    int age;

    String mailAddress;

}
```

## メソッドとは

メソッド（Method）とは、クラスが持つ処理である。

例えば、

- 名前を表示する
- 年齢を取得する
- メールを送信する

といった処理をメソッドとして定義する。

```java
public class User {

    public void printName() {
        System.out.println("ユーザ名を表示");
    }

}
```

## フィールドとメソッドの関係

```java
public class User {

    String name;                 // フィールド

    public void printName() {    // メソッド
        System.out.println(name);
    }

}
```

```text
User
├─ name
└─ printName()
```

フィールドはデータを保持し、メソッドはそのデータを利用して処理を実行する。

## クラスの基本構造

Javaのクラスは一般的に以下の構造を持つ。

```java
public class User {

    // フィールド
    String name;

    // メソッド
    public void printName() {
        System.out.println(name);
    }

}
```

## 実際に利用する

Userクラス

```java
public class User {

    String name;

    public void printName() {
        System.out.println(name);
    }

}
```

利用側

```java
User user = new User();

user.name = "田中";

user.printName();
```

実行結果

```text
田中
```

## メソッドの戻り値

メソッドは値を返すことができる。

例)

```java
public String getName() {
    return name;
}
```

```java
String userName = user.getName();
```

### returnとは

returnは呼び出し元へ値を返す命令である。

```java
public String getName() {
    return name;
}
```

```text
nameの値を返す
```

## メソッドの引数

メソッドには値を渡すことができる。

例)

```java
public void setName(String name) {

}
```

呼び出し

```java
user.setName("田中");
```

### 引数とは

引数（Parameter）はメソッドへ渡す値である。

```java
public void setName(String name) {
}
```

ここでは

```java
String name
```

が引数となる。

## フィールドとメソッドの例

```java
public class User {

    String name;

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

}
```

利用

```java
User user = new User();

user.setName("田中");

System.out.println(user.getName());
```

実行結果

```text
田中
```

## thisとは

thisは現在のオブジェクト自身を表す。

例)

```java
this.name = name;
```

左側

```java
this.name
```

フィールド

右側

```java
name
```

引数

を表している。

## まとめ

- フィールドはクラスが保持するデータである
- メソッドはクラスが持つ処理である
- メソッドは戻り値を返すことができる
- メソッドには引数を渡すことができる
- フィールドとメソッドを組み合わせてクラスを構成する

```text
クラス
├─ フィールド（データ）
└─ メソッド（処理）
```

例)

```java
public class User {

    String name;

    public String getName() {
        return name;
    }

}
```

オブジェクトはデータ（フィールド）と処理（メソッド）を持つことで、現実世界のモノを表現できる。

⬅️ [前へ](./07_class-and-object.md) ➡️ [次へ](./09_constructor.md) 🏠 [ホーム](./README.md)