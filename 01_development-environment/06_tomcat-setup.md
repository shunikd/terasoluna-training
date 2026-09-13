# Tomcat セットアップ手順

## 前提条件

Tomcatを利用するために、事前にJava（JDK）がインストールされている必要があります。

Javaの確認

```powershell
java --version
```

実行例

```text
openjdk 21.0.2 2024-01-16
OpenJDK Runtime Environment (build 21.0.2+13-58)
OpenJDK 64-Bit Server VM (build 21.0.2+13-58, mixed mode, sharing)
```

## 1. Tomcatのダウンロード

Apache Tomcat公式サイトへアクセス

https://tomcat.apache.org/

利用するバージョンを選択し、以下をダウンロードする。

```text
Core
- 64-bit Windows zip
```

例

```text
apache-tomcat-10.1.xx.zip
```

## 2. Tomcatの配置

ダウンロードしたZIPファイルを展開する。

例

```text
C:\tools\apache-tomcat-10.1.xx
```

ディレクトリ構成

```text
apache-tomcat-10.1.xx
├─ bin
├─ conf
├─ lib
├─ logs
├─ temp
├─ webapps
└─ work
```

## 3. 環境変数の設定（任意）

### CATALINA_HOME

システム環境変数を作成

```text
変数名: CATALINA_HOME
変数値: C:\tools\apache-tomcat-10.1.xx
```

### PATH

以下を追加

```text
%CATALINA_HOME%\bin
```

## 4. Tomcatの起動

PowerShellを開く。

Tomcatのbinディレクトリへ移動

```powershell
cd C:\tools\apache-tomcat-10.1.xx\bin
```

起動

```powershell
.\startup.bat
```


## 5. Tomcatの動作確認

ブラウザを開く。

```text
http://localhost:8080
```

Tomcatのトップページが表示されれば起動成功。
