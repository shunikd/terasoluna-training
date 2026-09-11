# 🧪 Java基礎 総合問題

## 🎯 目的

本問題はJava基礎章で学習した内容の理解度を確認するための総合問題である。

---

# 問題1

以下の説明として正しいものを選択せよ。

```text
Javaソースコード(.java)
        ↓
      javac
        ↓
クラスファイル(.class)
        ↓
       JVM
        ↓
       実行
```

1. JVMはJavaソースコードをコンパイルする
2. javacはクラスファイルを実行する
3. javacはJavaソースコードをコンパイルする
4. JVMはJARを生成する

---

## 解答

3

### 解説

javacはJavaソースコード(.java)をコンパイルし、クラスファイル(.class)を生成する。

JVMは生成されたクラスファイルを実行する。

---

# 問題2

JDKとJREについて正しい説明を選択せよ。

1. JREにはjavacが含まれる
2. JDKはJREを含む
3. JREはJDKを含む
4. JVMはJDKを含む

---

## 解答

2

### 解説

```text
JDK
 └─ JRE
     └─ JVM
```

という関係になっている。

---

# 問題3

以下のクラス名として推奨されるものを選択せよ。

1. userService
2. user_service
3. UserService
4. USER_SERVICE

---

## 解答

3

### 解説

クラス名はPascalCaseで記述する。

例)

```java
User
UserService
OrderController
```

---

# 問題4

以下のパッケージ名として適切なものを選択せよ。

1. JP.CO.SAMPLE
2. User.Service
3. jp.co.sample.service
4. USER.SERVICE

---

## 解答

3

### 解説

パッケージ名は通常すべて小文字で記述する。

---

# 問題5

以下のうちオブジェクト生成を行っているコードを選択せよ。

```java
1. User user;

2. User user = new User();

3. int age = 20;

4. String name;
```

---

## 解答

2

### 解説

```java
new User()
```

がオブジェクト生成である。

---

# 問題6

以下のコードについて答えよ。

```java
public class User {

    String name;

    public void printName() {
        System.out.println(name);
    }

}
```

### 設問

1. クラス名は何か
2. フィールド名は何か
3. メソッド名は何か

---

## 解答

1.

```text
User
```

2.

```text
name
```

3.

```text
printName
```

---

# 問題7

以下のコードについて答えよ。

```java
public class User {

    public User() {
        System.out.println("生成");
    }

}
```

コンストラクタはどれか。

---

## 解答

```java
public User() {
}
```

### 解説

コンストラクタはクラス名と同じ名前を持つ。

---

# 問題8

以下のアクセス修飾子のうち、同じクラス内のみアクセス可能なものはどれか。

1. public
2. protected
3. private

---

## 解答

3

### 解説

privateは同じクラス内からのみアクセス可能である。

---

# 問題9

以下のコードについて答えよ。

```java
public interface UserService {

}
```

UserServiceは何か。

1. クラス
2. インターフェース
3. メソッド
4. パッケージ

---

## 解答

2

### 解説

interfaceキーワードが利用されているため、インターフェースである。

---

# 問題10

以下のうち参照型を選択せよ。

1. int
2. boolean
3. String
4. long

---

## 解答

3

### 解説

Stringは参照型である。

---

# 問題11

以下のうちListを利用した宣言として正しいものを選択せよ。

1.

```java
List<User>
```

2.

```java
List<User> users
```

3.

```java
List<int>
```

4.

```java
User<List>
```

---

## 解答

2

### 解説

Listは複数の要素を保持するCollectionである。

またGenericsには参照型を指定する。

---

# 問題12

例外を発生させるキーワードはどれか。

1. catch
2. throws
3. throw
4. finally

---

## 解答

3

### 解説

```java
throw new Exception();
```

のように利用する。

---

# 問題13

以下のコードを実行した場合の結果を答えよ。

```java
for (int i = 0; i < 3; i++) {

    System.out.println(i);

}
```

---

## 解答

```text
0
1
2
```

---

# 問題14

JARについて正しい説明を選択せよ。

1. Javaソースコードそのものである
2. JVMそのものである
3. クラスファイル等をまとめたファイルである
4. DB接続用ファイルである

---

## 解答

3

### 解説

JAR(Java Archive)は複数のクラスファイルや設定ファイルをまとめた成果物である。

---

# 🎓 総合問題

以下のコードを読み、設問に答えよ。

```java
package jp.co.sample.user;

public class User {

    private String name;

    public User(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

}
```

### 設問

1. パッケージ名は何か
2. クラス名は何か
3. フィールド名は何か
4. アクセス修飾子は何か
5. コンストラクタはどれか
6. getName()の戻り値の型は何か

---

## 解答

1.

```text
jp.co.sample.user
```

2.

```text
User
```

3.

```text
name
```

4.

```text
private
```

5.

```java
public User(String name)
```

6.

```text
String
```

---

## ✅ 総合評価

以下が理解できていれば、Java基礎としては十分である。

- Java実行の仕組み
- JDK/JRE/JVM
- パッケージとクラス
- オブジェクト指向
- クラスとオブジェクト
- フィールドとメソッド
- コンストラクタ
- アクセス修飾子
- 継承とインターフェース
- 型
- CollectionとGenerics
- 例外処理
- 制御構文
- JAR

次章ではWebアプリケーションの基礎について学習する。