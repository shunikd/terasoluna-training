# パッケージとクラス

## この章で学ぶこと

- パッケージの役割を理解する
- クラスの役割を理解する
- Javaのパッケージ構成を理解する
- Javaの命名規則を理解する



## パッケージとは

パッケージとは、関連するクラスをまとめて管理する仕組みである。

OSのフォルダと似た役割を持っている。

例)

```text
jp.co.sample
├─ controller
├─ service
├─ repository
└─ entity
```

Javaではクラス数が増えるため、パッケージで整理して管理する。



## クラスとは

クラスとは、オブジェクトを生成するための設計図である。

例)

```java
public class User {

}
```

後続の章で学習するが、

- ユーザー
- 商品
- 注文

などをクラスとして表現する。



## パッケージとクラスの関係

クラスはパッケージの中に所属する。

例)

```java
package jp.co.sample;

public class User {

}
```

パッケージ名

```text
jp.co.sample
```

クラス名

```text
User
```



## ディレクトリ構成との関係

パッケージはディレクトリ構成と対応する。

例)

```java
package jp.co.sample.user;
```

ディレクトリ

```text
jp/
└─ co/
   └─ sample/
      └─ user/
         └─ User.java
```



## パッケージ名の命名規則

パッケージ名はすべて小文字で記述する。

例)

```java
package jp.co.sample;
```

```java
package jp.co.sample.user;
```



### すべて小文字にする理由

Javaではクラス名との区別を明確にするため、パッケージ名は小文字で記述する慣習となっている。

例)

```java
package jp.co.sample.service;

public class UserService {

}
```

```text
jp.co.sample.service ← パッケージ名
UserService          ← クラス名
```



## ドメイン名を逆順にする理由

パッケージ名は世界中で重複しないようにするため、所有しているドメイン名を逆順にして利用する。

例)

会社ドメイン

```text
sample.co.jp
```

パッケージ名

```java
jp.co.sample
```

システム名を追加する場合

```java
jp.co.sample.order
```

```java
jp.co.sample.customer
```



## クラス名の命名規則

クラス名はパスカルケース（PascalCase）で命名する。

パスカルケースとは、各単語の先頭を大文字にして連結する命名規則である。

例)

```java
User
```

```java
UserInfo
```

```java
UserService
```

```java
OrderController
```



### 推奨されない例

```java
user
```

```java
userinfo
```

```java
user_service
```



## クラス名とファイル名

Javaでは public クラス名とファイル名を一致させる必要がある。

例)

```java
public class User {
}
```

ファイル名

```text
User.java
```



正しい例

```java
public class UserService {
}
```

```text
UserService.java
```



誤った例

```java
public class UserService {
}
```

```text
Sample.java
```

コンパイル時にエラーとなる。



## Javaの主な命名規則

|対象|命名規則|例|
|---|---|---|
|クラス名|PascalCase|UserService|
|インターフェース名|PascalCase|UserRepository|
|メソッド名|camelCase|getUserName|
|フィールド名|camelCase|userName|
|ローカル変数|camelCase|userCount|
|定数|UPPER_SNAKE_CASE|MAX_COUNT|
|パッケージ名|lowercase + reverse domain|jp.co.sample.user|



### 定数の命名規則

定数は通常、すべて大文字で記述し、単語間をアンダースコア(_)で区切る。

例)

```java
MAX_COUNT
DEFAULT_TIMEOUT
SYSTEM_NAME
```

定数は変更されない値であることを分かりやすくするため、大文字で記述する慣習となっている。

例)

```java
private static final int MAX_COUNT = 100;
```





## 💡 ポイント

- パッケージはクラスを整理するための仕組みである
- クラスはオブジェクトの設計図である
- パッケージ名はすべて小文字で記述する
- パッケージ名はドメイン名を逆順で記載することが多い
- クラス名はPascalCaseで命名する
- publicクラス名とファイル名は一致させる
- 定数はUPPER_SNAKE_CASEで命名する



## まとめ

```text
パッケージ
 └─ クラス
      └─ オブジェクト（次章で説明）
```

Javaではパッケージを利用してクラスを整理し、クラスを利用してプログラムを構築する。


⬅️ 前へ: 03_jdk-jre-jvm.md

🏠 README.md

➡️ 次へ: 05_object-oriented-programming.md