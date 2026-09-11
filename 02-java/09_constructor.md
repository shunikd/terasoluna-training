# コンストラクタ

## この章で学ぶこと

- コンストラクタとは何かを理解する
- オブジェクト生成時の処理を理解する
- 引数付きコンストラクタを理解する
- newとの関係を理解する


## コンストラクタとは

コンストラクタ（Constructor）とは、オブジェクト生成時に実行される特別なメソッドである。

例)

```java
User user = new User();
```

上記コードでは、

```java
new User()
```

が実行される際にコンストラクタが呼び出される。


## コンストラクタの特徴

コンストラクタには以下の特徴がある。

- クラス名と同じ名前を持つ
- 戻り値を持たない
- オブジェクト生成時に自動的に呼び出される

例)

```java
public class User {

    public User() {
        System.out.println("コンストラクタが実行されました");
    }

}
```


## コンストラクタの動作

クラス

```java
public class User {

    public User() {
        System.out.println("User生成");
    }

}
```

利用

```java
User user = new User();
```

実行結果

```text
User生成
```


## オブジェクト生成の流れ

```mermaid
flowchart LR

    NEW["new User()"]

    CONSTRUCTOR["コンストラクタ"]

    OBJECT["Userオブジェクト"]

    NEW --> CONSTRUCTOR
    CONSTRUCTOR --> OBJECT
```


## デフォルトコンストラクタ

コンストラクタを定義しない場合、Javaはデフォルトコンストラクタを自動生成する。

例)

```java
public class User {

}
```

内部的には以下と同じ意味になる。

```java
public class User {

    public User() {

    }

}
```


## 引数付きコンストラクタ

コンストラクタには引数を指定できる。

例)

```java
public class User {

    String name
```