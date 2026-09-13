# Gitのインストールおよび設定手順

## 1. Gitのインストール

公式サイトから最新の64bit版 Git for Windows をダウンロードしてインストールする。

※基本はデフォルトの設定値のままインストールしてよい。

- https://git-scm.com/download/win

インストール後、VS Code のターミナルで以下のコマンドを実行し、Git が正しくインストールされていることを確認する。

```powershell
git --version
```

コマンド実行結果例：

```text
git version 2.55.0.windows.5
```

## 2. ユーザ情報の設定

Gitにコミット作成者情報を登録する。

設定確認：

```powershell
git config --global --list
```

コミット作成者情報の登録：

```powershell
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

設定確認：

```powershell
git config --global --list
```

※リモートリポジトリへの接続設定（認証設定）は別手順を参照すること。
