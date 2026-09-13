# Mavenの基礎知識

## Mavenとは

MavenはJavaプロジェクトのビルド管理ツールです。

主に以下の機能を提供します。

- ライブラリ（依存関係）の管理
- ソースコードのコンパイル
- テスト実行
- JAR/WARファイル作成
- プロジェクト構成の標準化

Java開発では非常によく利用されるツールです。

---

# Mavenのメリット

## 依存関係管理

必要なライブラリを自動でダウンロードできます。

例

```xml
<dependency>
    <groupId>org.postgresql</groupId>
    <artifactId>postgresql</artifactId>
    <version>42.7.7</version>
</dependency>
```

手動でJARファイルを配置する必要がありません。

---

## ビルド自動化

コンパイルやテストを自動で実行できます。

```bash
mvn compile
```

---

## プロジェクト構成の統一

Mavenでは標準ディレクトリ構成が定義されています。

そのため、どのプロジェクトでも似た構成になります。

---

# Mavenの基本概念

## プロジェクトオブジェクトモデル（POM）

Mavenはpom.xmlという設定ファイルで管理されます。

```text
Project Object Model
↓
pom.xml
```

Mavenの動作設定や依存関係を記述します。

---

## pom.xml

Mavenプロジェクトの中心となるファイルです。

例

```xml
<project>
    <groupId>com.example</groupId>
    <artifactId>sample</artifactId>
    <version>1.0.0</version>
</project>
```

---

## groupId

プロジェクトや組織を識別するIDです。

例

```xml
<groupId>com.example</groupId>
```

通常はドメイン名を逆順にした形式を使用します。

---

## artifactId

成果物（アプリケーション名やライブラリ名）です。

例

```xml
<artifactId>sample-web</artifactId>
```

---

## version

プロジェクトのバージョンを管理します。

例

```xml
<version>1.0.0</version>
```

---

## Dependency（依存関係）

利用するライブラリを定義します。

例

```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>5.13.4</version>
</dependency>
```

Mavenが自動的にダウンロードします。

---

## Repository

ライブラリが保管されているサーバです。

代表例

```text
Maven Central Repository
```

Mavenは必要なライブラリを自動取得します。

---

# Mavenの標準ディレクトリ構成

```text
project
├─ pom.xml
└─ src
    ├─ main
    │   ├─ java
    │   ├─ resources
    │   └─ webapp
    └─ test
        ├─ java
        └─ resources
```

---

## src/main/java

Javaソースコード

```text
src/main/java
```

---

## src/main/resources

設定ファイル

```text
application.properties
logback.xml
```

---

## src/test/java

テストコード

```text
JUnitテスト
```

---

## target

ビルド成果物

```text
target/
```

コンパイル後に生成されるためGit管理対象外とすることが一般的です。

---

# Mavenのライフサイクル

Mavenにはビルド手順があらかじめ定義されています。

```text
validate
↓
compile
↓
test
↓
package
↓
verify
↓
install
↓
deploy
```

---

# よく利用するコマンド

## バージョン確認

```bash
mvn -version
```

---

## コンパイル

```bash
mvn compile
```

実施内容

- ソースコードのコンパイル

生成先

```text
target/classes
```

---

## テスト実行

```bash
mvn test
```

実施内容

- JUnitテスト実行

---

## パッケージ作成

```bash
mvn package
```

実施内容

- コンパイル
- テスト
- JAR/WAR作成

生成先

```text
target/
```

例

```text
sample-1.0.0.jar
```

---

## ローカルリポジトリ登録

```bash
mvn install
```

ローカルリポジトリへ成果物を配置します。

格納先

```text
%USERPROFILE%\.m2\repository
```

---

## クリーン

```bash
mvn clean
```

実施内容

```text
targetディレクトリ削除
```

---

## クリーン＋ビルド

```bash
mvn clean package
```

開発現場でよく利用されます。

---

# Mavenリポジトリ

## ローカルリポジトリ

PC内に保存されるライブラリ

```text
C:\Users\ユーザー名\.m2\repository
```

---

## リモートリポジトリ

インターネット上のライブラリ保管場所

例

```text
Maven Central
```

---

# 依存関係追加例

PostgreSQL JDBC Driver

```xml
<dependency>
    <groupId>org.postgresql</groupId>
    <artifactId>postgresql</artifactId>
    <version>42.7.7</version>
</dependency>
```

---

# よくある開発の流れ

## 1. ソース修正

Javaコードを修正

---

## 2. コンパイル

```bash
mvn compile
```

---

## 3. テスト

```bash
mvn test
```

---

## 4. パッケージ作成

```bash
mvn package
```

---

## 5. 実行確認

生成されたJAR/WARを実行

---

## 6. Gitへコミット

```bash
git add .
git commit -m "機能追加"
```

---

# Gitとの関係

開発現場では以下のように利用します。

```text
Git
↓
ソースコードの変更履歴管理

Maven
↓
ビルド・依存関係管理
```

役割が異なるため、通常は両方を併用します。

---

# よく使うコマンド一覧

| 操作 | コマンド |
|--------|----------|
| バージョン確認 | `mvn -version` |
| コンパイル | `mvn compile` |
| テスト | `mvn test` |
| パッケージ作成 | `mvn package` |
| ローカル登録 | `mvn install` |
| 成果物削除 | `mvn clean` |
| クリーン＋ビルド | `mvn clean package` |
| 依存関係取得 | `mvn dependency:resolve` |

---

# まとめ

- MavenはJavaのビルド管理ツール
- pom.xmlでプロジェクトを設定する
- ライブラリを自動管理できる
- コンパイル、テスト、パッケージ作成を自動化できる
- Java開発ではGitとMavenを組み合わせて利用する
- 日常業務では `clean`、`compile`、`test`、`package`、`install` をよく利用する



## 5. Mavenプロジェクト作成

任意の作業フォルダへ移動

```powershell
cd C:\work
```

雛形を生成

```powershell
mvn archetype:generate `
  -DgroupId=com.example `
  -DartifactId=test `
  -DarchetypeArtifactId=maven-archetype-quickstart `
  -DinteractiveMode=false
```

生成後

```text
test
├─ pom.xml
└─ src
    ├─ main
    │   └─ java
    └─ test
        └─ java
```

---

## 6. コンパイル

プロジェクトへ移動

```powershell
cd test
```

コンパイル

```powershell
mvn compile
```

---

## 7. テスト実行

```powershell
mvn test
```

---

## 8. パッケージ作成

```powershell
mvn package
```

生成物

```text
target\test-1.0-SNAPSHOT.jar
```

---

## 9. クリーン

生成物を削除

```powershell
mvn clean
```

---

## よく使うコマンド

依存関係取得

```powershell
mvn dependency:resolve
```

コンパイル

```powershell
mvn compile
```

テスト

```powershell
mvn test
```

JAR作成

```powershell
mvn package
```

インストール

```powershell
mvn install
```

クリーン

```powershell
mvn clean
```

バージョン確認

```powershell
mvn -version
```
