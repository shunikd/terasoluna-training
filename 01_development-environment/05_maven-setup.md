# Mavenのインストールおよび設定手順

## 前提条件

Mavenを利用するために、事前にJava（JDK）がインストールされている必要がある。

Javaの確認：

```powershell
java --version
```

コマンド実行結果：

```text
openjdk 21.0.2 2024-01-16
OpenJDK Runtime Environment (build 21.0.2+13-58)
OpenJDK 64-Bit Server VM (build 21.0.2+13-58, mixed mode, sharing)
```

コンパイラの確認

```powershell
javac --version
```

コマンド実行結果：

```text
javac 21.0.2
```

## 1. Mavenのダウンロード

Apache Maven公式サイトへアクセス

https://maven.apache.org/download.cgi

以下をダウンロードする。

```text
Binary zip archive
apache-maven-x.x.x-bin.zip
```

## 2. Mavenの配置

ダウンロードしたzipファイルを任意のフォルダで解凍する。

解凍結果：

```text
C:\tools\apache-maven-3.9.16
```

## 3. 環境変数の設定

[OpenJDKのインストールおよび設定](./03_java-setup.md)を参照して、新しいシステム環境変数とPATHを設定する。

### MAVEN_HOME

```text
変数名: MAVEN_HOME
変数値: C:\tools\apache-maven-3.9.16
```

### PATH

```text
%MAVEN_HOME%\bin
```

## 4. 動作確認

VS Code上でターミナルを開き、以下のコマンドを実行する。

```powershell
mvn -version
```

コマンド実行例：

```text
Maven home: C:\tools\apache-maven-3.9.16
Java version: 21.0.2, vendor: Oracle Corporation, runtime: C:\Program Files\Java\jdk-21.0.2
Default locale: ja_JP, platform encoding: UTF-8
OS name: "windows 11", version: "10.0", arch: "amd64", family: "windows"
```
