# Javaを実際に動かしてみる

## 1. VSCode上でターミナルを開き、「HelloWorld」を出力させよう

### 要件

```text
クラス名：HelloWorld

ターミナルから以下を出力する

Hello World
```

### 実行コマンド

```text
javac HelloWorld.java

java HelloWorld
```

## 2. 以下のパッケージとクラスを作成してみよう

### 要件

#### パッケージ

```java
jp.co.sample.practice
```

#### クラス

```java
User
Product
Order
```

## 3. クラス・フィールド・メソッドを作ろう

### Userクラス仕様

| 項目     | 内容    |
| -------- | ------ |
| userId   | String |
| userName | String |

### 実装するメソッド

```java
printInfo()
```

#### 出力

```text
ユーザID:U001
ユーザ名:田中
```

## 4. オブジェクト指向を体験しよう

### Userクラス仕様

| 項目     | 内容    |
| -------- | ------ |
| userId   | String |
| userName | String |

### コンストラクタ仕様

```java
User(String userId, String userName)
```

### Mainクラス

下記の3人のユーザを生成し、以下をターミナルに表示する。

```text
U001 田中
U002 鈴木
U003 佐藤
```

## 5. 型・制御構文・Collectionを体験しよう

### 要件

Userを5件作成する。

```text
List<User>
```

作成後、拡張for文を使って、Listの内容をターミナルに表示する。

## 6. ファイル読込と例外処理を体験しよう

### 要件

以下のファイルを読み込み、例外処理を実装する。

```text
users.txt
```

ファイルがない場合に例外が発生してコンパイルエラーになることを確認する。