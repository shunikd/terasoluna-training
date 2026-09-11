# フィールドとメソッド

## この章で学ぶこと

- フィールドとは何かを理解する
- メソッドとは何かを理解する
- クラスの基本構造を理解する
- オブジェクトがデータと処理を持つことを理解する

## フィールドとは

フィールド（Field）とは、クラスが保持するデータである。

例えばユーザークラスを考える。

```text
ユーザー
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
        System.out.println("ユーザー名を表示");
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
