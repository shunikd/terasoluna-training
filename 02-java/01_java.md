# Javaとは

## この章で学ぶこと

- Javaとはどのようなプログラミング言語なのか理解する
- Javaがどのようなシステムで使われているか知る
- TERASOLUNA FrameworkとJavaの関係を理解する

## Javaとは

Java（ジャバ）は、世界中で利用されているプログラミング言語の一つである。

Webアプリケーション、業務システム、スマートフォンアプリ、組み込み機器など、さまざまなシステムの開発に利用されている。

本書で学習するTERASOLUNA FrameworkもJavaを利用して作られているため、TERASOLUNAを理解するためにはJavaの基礎知識が必要となる。

## Javaでできること

Javaはさまざまなシステム開発で利用されている。

例)

- Webアプリケーション
- 業務システム
- 銀行システム
- 在庫管理システム
- スマートフォンアプリ(Android)

## Javaがよく利用される理由

### 1. OSに依存しにくい

JavaはWindows、macOS、Linuxなど異なるOS上で動作できる。

```text
Javaプログラム
       ↓
Windows / macOS / Linux
```

同じプログラムを複数のOSで実行しやすい特徴を持つ。

### 2. 大規模システム開発に向いている

Javaは企業向けの業務システムで広く利用されている。

例)

- 銀行システム
- 販売管理システム
- 人事管理システム

そのため多くの企業で採用されている。

### 3. ライブラリやフレームワークが豊富

Javaには様々な便利なライブラリやフレームワークが存在する。

例)

|名称|用途|
|---|---|
|Spring Framework|Webアプリケーション開発|
|TERASOLUNA Framework|業務システム開発|
|JUnit|テスト|
|MyBatis|データベースアクセス|

開発者はこれらを利用することで効率よくシステムを作ることができる。

## Javaのエディション

Javaには用途に応じて複数のエディションが存在する。

主に以下の2つを理解しておけばよい。

|エディション|概要|
|---|---|
|Java SE (Standard Edition)|Javaの標準機能を提供する基本パッケージ|
|Java EE (Enterprise Edition)|企業向けWebシステム開発のための拡張仕様|


### Java SE (Standard Edition)

Java SEはJavaの基本機能を提供する。

例)

- クラス
- オブジェクト指向
- コレクション(List、Map、Set)
- 例外処理
- 入出力
- ネットワーク通信

本章で学習する内容の多くはJava SEの機能である。

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello Java");
    }
}
```


### Java EE (Enterprise Edition)

Java EEは企業向けシステム開発のための仕様群である。

主に以下のような機能を提供する。

- Webアプリケーション
- トランザクション管理
- データベース連携
- セキュリティ
- REST API

```text
ブラウザ
    ↓
Webサーバ
    ↓
Javaアプリケーション
    ↓
データベース
```

銀行システムや業務システムなどの大規模なWebアプリケーション開発で利用されてきた。


### Jakarta EE

現在のJava EEは「Jakarta EE」という名称に変更されている。

Spring FrameworkやTERASOLUNA FrameworkもJakarta EEの技術を利用して動作している。

なお、本書ではJakarta EEの詳細は扱わず、Spring FrameworkおよびTERASOLUNA Frameworkを中心に学習する。


### TERASOLUNAとの関係

TERASOLUNA Frameworkは以下の技術を組み合わせて構成されている。

```text
Java SE
   ↓
Jakarta EE
   ↓
Spring Framework
   ↓
TERASOLUNA Framework
```

そのため、まずはJava SEの基礎知識を理解することが重要である。

## まとめ

- Javaは世界中で利用されているプログラミング言語である
- 業務システムやWebアプリケーション開発で広く利用されている
- JavaはWindowsとmacOSの両方で実行できる
- TERASOLUNA FrameworkはJavaを利用して開発するためのフレームワークである
- TERASOLUNAを学ぶ前にJavaの基礎を理解する必要がある

## 参考資料

### Oracle Java Documentation

Javaの公式ドキュメント

https://docs.oracle.com/en/java/