# Webアプリケーション開発

## ブランクプロジェクトを動かす

1. TERASOLUNA Server Framework for Javaのブランクプロジェクトをダウンロードする。

    ``` PowerShell
    mvn archetype:generate "-DarchetypeGroupId=org.terasoluna.gfw.blank" 
    ```

    ``` PowerShell
    Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): : 3443
    ```

    ``` PowerShell
    Choose org.terasoluna.gfw.blank:terasoluna-gfw-multi-web-blank-xmlconfig-jsp-mybatis3-archetype version: 
    1: 5.9.0.RC1
    2: 5.9.0.RC2
    3: 5.9.0.RELEASE
    4: 5.10.0.RELEASE
    5: 5.10.1.RC1
    6: 5.10.1.RELEASE
    7: 5.11.0.RC1
    8: 5.11.0.RELEASE
    Choose a number: 8: 8
    ```

    ``` PowerShell
    Define value for property 'groupId': com.nkkt
    ```

    ``` PowerShell
    Define value for property 'artifactId': fms
    ```

    ``` PowerShell
    Define value for property 'version' 1.0-SNAPSHOT: 1.0.0-SNAPSHOT
    ```

    ``` PowerShell
    Define value for property 'version' 1.0-SNAPSHOT: 1.0.0-SNAPSHOT
    ```

    ``` PowerShell
    Confirm properties configuration:
    groupId: com.nkkt.report
    artifactId: report
    version: 1.0.0-SNAPSHOT
    package: com.nkkt.report
    Y: Y
    ```

2. ブランクプロジェクトをビルドする。

    ``` PowerShell
    cd report
    ```
    reportフォルダ配下のpom.xmlを以下の通り修正する。

    ``` PowerShell
    # 変更前
    <modules>
        <module>report-env</module>
        <module>report-domain</module>
        <module>report-web</module>
        <module>report-initdb</module>
        <module>report-selenium</module>
    </modules>

    # 変更後
    <modules>
        <module>report-env</module>
        <module>report-domain</module>
        <module>report-web</module>
        <module>report-initdb</module>
        <!--
        <module>report-selenium</module>
        -->
    </modules>
    ```

    この状態で下記のコマンドを実行し、ビルドする。

    ``` PowerShell
    mvn install
    ```

    mvn installコマンドを実行すると、report-webフォルダのtargetフォルダにreport-web.warが出来上がる。

    Community Server ConnectorsのSERVERSペインからTomcatを選択し、右クリックをして「Add Deployment」をクリックし、画面上部の選択肢から「File」を選択してクリックする。

    ファイル選択用のダイアログが表示されるので、先ほど作成したreport-web.warを選択する。
