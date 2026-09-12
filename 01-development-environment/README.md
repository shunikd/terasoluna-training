# 開発環境および開発ツールのセットアップ

本書は、TERASOLUNA Server Framework for Javaを利用して、Java Webアプリケーション開発環境を準備するための手順をまとめたものです。

Java開発環境には以下のツールを使用します。

- Visual Studio Code
- OpenJDK
- Git
- Apache Maven
- Apache Tomcat
- PostgreSQL
- TERASOLUNA Server Framework for Java

## 本書の方針

本書は執筆時点（2026年9月）の最新バージョンである

TERASOLUNA Server Framework for Java 5.11.0.RELEASE を利用します。

また、開発環境の各ソフトウェアについては、TERASOLUNA公式の検証済み環境（Tested Environment）で動作確認されているバージョンを採用します。

| ソフトウェア | バージョン |
|-------------|-------------|
| OpenJDK | 21.0.9 |
| Git | 最新安定版 |
| Maven | 最新安定版 |
| Tomcat | 11.0.15 |
| PostgreSQL | 18.1 |

※ OpenJDKは TERASOLUNA の検証済み環境に含まれる Java 21 系を採用しています。

参考:
- [動作検証環境](https://github.com/terasolunaorg/terasoluna-gfw-functionaltest/wiki/Tested-Environment)
- [TERASOLUNA 5.11.0.RELEASE](https://github.com/terasolunaorg/terasoluna-gfw/releases)

## 対象者

- Java開発の学習者
- TERASOLUNAを利用したWebアプリケーション開発者
- 新規に開発環境を構築するメンバ


## 開発ツールの設定手順

以下の順番で実施してください。

| No | ドキュメント | 内容 |
|---|---|---|
| 1 | 開発ツール一覧 | [📃](./01_development-tools-list.md) |
| 2 | VSCodeのインストールおよび設定 | [📃](./02_vscode-setup.md) |
| 3 | OpenJDKのインストールおよび環境変数設定 | [📃](./03_java-setup.md) |
| 4 | gitのインストールおよび設定 | [📃](./04_git-setup.md) |
| 5 | Mavenのインストールおよび設定 | [📃](./05_maven-setup.md) |
| 6 | Tomcatのインストールおよび設定 | [📃](./06_tomcat-setup.md) |
| 7 | PostgreSQLのインストールおよび設定 | [📃](./07_postgresql-setup.md) |
| 8 | TERASOLUNA Server Framework for Javaのブランクプロジェクト設定 | [📃](./10_terasoluna-setup.md) |

## 注意事項

- インストール手順は Windows を前提としています。MacOSやLinuxをご利用の場合は適宜読み替えて実施してください。
- 管理者権限が必要になる場合があります。
- プロジェクトごとに使用バージョンが異なる場合は、プロジェクトの指示を優先してください。