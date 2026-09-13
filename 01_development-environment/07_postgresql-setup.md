# PostgreSQL セットアップ手順

## 前提条件

- Windows 10 / 11
- 管理者権限を持つユーザ
- Javaアプリケーションから接続する場合はJDKをインストール済み

## 1. PostgreSQL のダウンロード

PostgreSQL公式サイトへアクセス

[PostgreSQL Downloads](https://www.postgresql.org/download/windows/)

Windows版インストーラー（EnterpriseDB）をダウンロードする。

## 2. PostgreSQL のインストール

ダウンロードしたインストーラを起動する。

### インストール項目

以下はデフォルト設定で問題ない。

```text
PostgreSQL Server
pgAdmin 4
Stack Builder
Command Line Tools
```


## 3. パスワード設定

インストール中に管理者ユーザー（postgres）のパスワードを設定する。

例

```text
ユーザー名：postgres
パスワード：postgres
```

※学習用以外では推測されにくいパスワードを設定すること。

## 4. ポート番号設定

デフォルト設定

```text
5432
```

他のアプリケーションと競合しない限り変更不要。

## 5. インストール確認

PowerShellを起動し、バージョンを確認する。

```powershell
psql --version
```

実行例

```text
psql (PostgreSQL) 17.x
```

## 6. PostgreSQL サービス確認

サービス一覧を確認する。

```powershell
Get-Service *postgres*
```

実行例

```text
Status   Name
------   ----
Running  postgresql-x64-17
```

## 7. PostgreSQL へ接続

PowerShellで実行

```powershell
psql -U postgres
```

パスワード入力後、以下のように表示されれば成功

```text
postgres=#
```

終了

```sql
\q
```
