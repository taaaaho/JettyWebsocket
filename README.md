# JettyWebsocket

## Jettyを用いてWebsokcet通信を行うサーバーを立てる

### EclipseでMavenプロジェクトを作成する
Eclipse > File > New > Maven Project を選択する  
※無い場合はOtherから検索可能  

GroupIdとArtifactIdは適当な名称をつけて作成する。  
ここでは一旦以下のように指定している。  
* GroupId => JettyWebsocket
* ArtifactId => jetty  

### Jettyのライブラリをpom経由で読み込む
**1.pom.xmlを開いて以下を追記する**

```
  <dependencies>
    <!-- https://mvnrepository.com/artifact/org.eclipse.jetty.websocket/javax-websocket-server-impl -->
    <dependency>
      <groupId>org.eclipse.jetty.websocket</groupId>
      <artifactId>javax-websocket-server-impl</artifactId>
      <version>9.4.11.v20180605</version>
    </dependency>
  </dependencies>
```
  
pom全体だとこんな感じ
```
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>JettyWebsocket</groupId>
  <artifactId>jetty</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  
  <dependencies>
    <!-- https://mvnrepository.com/artifact/org.eclipse.jetty.websocket/javax-websocket-server-impl -->
    <dependency>
      <groupId>org.eclipse.jetty.websocket</groupId>
      <artifactId>javax-websocket-server-impl</artifactId>
      <version>9.4.11.v20180605</version>
    </dependency>
  </dependencies>
</project>
```

**2.Maven Buildを実行する**  
プロジェクトを右クリックから「Run as > Maven Build」を選択する。  
ビルドのプロパティでGoalは「test」と記載して「Run」をクリック。  
コンソールにログが表示されるので正常終了していることを確認する。  
ビルドが正常終了すると、「Maven Dependencies」に必要なファイルが作成される。  


### Jettyサーバーを起動するソースを記述する  
今回は起動の確認がわかりやすいようにタスクトレイに格納されるアプリにしています。  
Windowsの場合は右下のトレイに、Macの場合は上部に指定してアイコンが表示されるようになります。  
ソースはjettyServer.javaです。  
階層は以下  
Jetty > src/main/java > jettyServer > JettyServer.java  
icon.pngにアプリのアイコンとなる画像を指定してください。  

※タスクトレイに収納する必要が無い場合は、「ImageIcon 〜 SystemTray」の行は全て不要です。  





