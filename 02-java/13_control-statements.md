# 制御構文

## この章で学ぶこと

- 制御構文とは何かを理解する
- 条件分岐を理解する
- 繰り返し処理を理解する
- Collectionと組み合わせた処理を理解する

## 制御構文とは

制御構文とは、プログラムの処理の流れを制御する仕組みである。

例)

- 条件によって処理を変える
- 同じ処理を繰り返す
- 処理を途中で終了する

Javaでは主に以下を利用する。

|分類|構文|
|---|---|
|条件分岐|if、switch|
|繰り返し|for、while|
|繰り返し(拡張)|enhanced for|

## if文

条件によって処理を分岐する。

例)

```java
int age = 20;

if (age >= 18) {
    System.out.println("成人");
}
```

実行結果

```text
成人
```

## if-else文

条件に応じて処理を切り替える。

```java
int age = 15;

if (age >= 18) {
    System.out.println("成人");
} else {
    System.out.println("未成年");
}
```

実行結果

```text
未成年
```

## if-else if文

複数条件を判定する。

```java
int score = 85;

if (score >= 90) {

    System.out.println("A");

} else if (score >= 80) {

    System.out.println("B");

} else {

    System.out.println("C");

}
```

実行結果

```text
B
```

## switch文

値によって処理を分岐する。

```java
int month = 3;

switch (month) {

    case 1:
        System.out.println("1月");
        break;

    case 2:
        System.out.println("2月");
        break;

    case 3:
        System.out.println("3月");
        break;

    default:
        System.out.println("その他");

}
```

実行結果

```text
3月
```

## for文

指定回数だけ繰り返し処理を行う。

```java
for (int i = 0; i < 3; i++) {

    System.out.println(i);

}
```

実行結果

```text
0
1
2
```

## for文の構造

```java
for (初期値; 条件式; 増減式) {
}
```

例)

```java
for (int i = 0; i < 10; i++) {
}
```

## enhanced for文

Collectionや配列を扱う際によく利用する。

例)

```java
List<String> users =
    List.of(
        "田中",
        "鈴木",
        "佐藤"
    );

for (String user : users) {

    System.out.println(user);

}
```

実行結果

```text
田中
鈴木
佐藤
```

## while文

条件を満たしている間、処理を繰り返す。

```java
int count = 0;

while (count < 3) {

    System.out.println(count);

    count++;

}
```

実行結果

```text
0
1
2
```

## break

繰り返し処理を終了する。

```java
for (int i = 0; i < 10; i++) {

    if (i == 5) {
        break;
    }

    System.out.println(i);

}
```

実行結果

```text
0
1
2
3
4
```

## continue

現在の処理をスキップして次の繰り返しへ進む。

```java
for (int i = 0; i < 5; i++) {

    if (i == 2) {
        continue;
    }

    System.out.println(i);

}
```

実行結果

```text
0
1
3
4
```

## よく利用する制御構文

実務では以下を頻繁に利用する。

### 条件分岐

```java
if
```

### Collectionのループ

```java
for (User user : users)
```

### nullチェック

```java
if (user != null)
```

## まとめ

- 制御構文は処理の流れを制御する仕組みである
- ifは条件分岐に利用する
- switchは値による分岐に利用する
- forは繰り返し処理を行う
- enhanced forはCollectionの操作で頻繁に利用する
- whileは条件を満たす間繰り返す

|目的|構文|
|---|---|
|条件分岐|if|
|値による分岐|switch|
|繰り返し|for|
|Collectionのループ|enhanced for|
|条件付きループ|while|

一般的なWebアプリケーション開発では特に以下を頻繁に利用する。

```java
if (...)
```

```java
for (User user : users)
```

まずはこの2つを読めるようになることが重要である。

⬅️ [前へ](./12_collections-and-generics.md) ➡️ [次へ](./14_exception-handling.md) 🏠 [ホーム](./README.md)