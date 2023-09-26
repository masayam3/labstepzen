---
title: Mastering Enterprise-Level GraphQL
---


<FeatureCard
  title="Mastering Enterprise-Level GraphQL"
  color="dark"
  >

![banner](images/graphql-banner.png)

</FeatureCard>

<AnchorLinks>
  <AnchorLink>Introduction</AnchorLink>
  <AnchorLink>Prerequisites</AnchorLink>
  <AnchorLink>Business Context</AnchorLink>
  <AnchorLink>Lab Overview</AnchorLink>
  <AnchorLink>1 - Install Node.JS</AnchorLink>
  <AnchorLink>2 - Install IDE</AnchorLink>
  <AnchorLink>3 - Setup StepZen</AnchorLink>
  <AnchorLink>4 - Build your GraphQL API from a REST API</AnchorLink>
  <AnchorLink>5 - Adding a new REST API in your GraphQL API</AnchorLink>
  <AnchorLink>6 - Autogenerate GraphQL Schemas from MySQL Database</AnchorLink>
  <AnchorLink>7 - Creating a composition of building blocks using @materializer</AnchorLink>
  <AnchorLink>8 - Create a GraphQL Proxy API in APIC</AnchorLink>
  <AnchorLink>9 - Editing and Testing the GraphQL Proxy API</AnchorLink>
  <AnchorLink>10 - Create a Product and apply GraphQL RateLimits</AnchorLink>
  <AnchorLink>11 - Explore the API from Developer Portal</AnchorLink>
  <AnchorLink>Summary</AnchorLink>
</AnchorLinks>

***

## Lab Overview

ハイブリッド クラウドの採用の増加により、データはさまざまなクラウドやオンプレミス環境だけでなく、データ ウェアハウス、レイク、レイクハウスなどのさまざまな種類のデータ ストアにも、あらゆる場所に保存されるようになりました。API は、さまざまなデータ ソースとアプリケーション間の重要なコネクターとして機能します。これは、企業がアプリケーションやエクスペリエンスを強化するために必要なデータを取得するために、これまで以上に多くの API に依存し、作成していることを意味します。

GraphQL は、企業がデータを操作するための頼りになるクエリ言語として急速に普及し、REST API とデータ システムへの投資を重ねる API の新しい標準として浮上しています。GraphQL API はアプリケーション チームにとって非常に使いやすいものですが、その構築を担当する API プロバイダー チームにとっては課題となる可能性があります。私たちは、宣言的に構築された API の方が単純に優れていると信じています。これにより、クリーンなコード行が減り、デプロイ時間が短縮され、パフォーマンス、コスト、信頼性の最適化が組み込まれた API で最初の実装が可能になります。

宣言的にプログラミングする場合、システムを構成することになります。また、すべてのクエリにわたって、さまざまな状況に適用できる普遍的なルールをシステムに提供することになります。結果として得られるコードは耐障害性が向上し、(DRY 原則に従って) ソフトウェア パターンの繰り返しが減り、理解と保守が容易になります。重要なのは、これにより、本来なら自分でコーディングする必要がある作業をプラットフォームが実行できるようになります。

StepZen を使用すると、開発者は複数のバックエンドから必要なデータを取得する単一の GraphQL API を簡単に構築してデプロイできます。API は、バックエンド プロトコル、スキーマ、認証に関係なく、適切なデータを確実に配信します。開発者がインフラストラクチャを管理しないように API を管理します。

StepZen の宣言型アプローチを使用すると、開発者は GraphQL ビルディング ブロックを構成して GraphQL スキーマを作成することで、GraphQL API (およびフェデレーション グラフ) を構築できます。強力なイントロスペクション機能は、エンタープライズ データの GraphQL モデルをわずか数行のコードで構築および構成できることを意味します。

API を宣言的に構築するため、StepZen は API を理解し、実行時に最適化の決定を下すことができ、低レイテンシーと高スループットを実現し、バックエンドへの負担を最小限に抑えます。

API Connect を使用すると、開発者は API を簡単に管理、保護、ソーシャル化、監視できます。StepZen の前に API Connect を配置すると、GraphQL、REST、SOAP、その他の形式の API をすべて 1 つの製品に組み込んだ API 製品を簡単に構築できます。その後、独自の使用条件を持つさまざまな API プランに基づいて API 製品を販売することができます。製品とプランを設定すると、セルフサービスの開発者ポータルを使用してそれらを宣伝し、エンド ユーザーにソーシャル化することができます。これにより、顧客は、積極的に関与しなくても、API 製品を見つけて試し、支払いを行うことができます。最後に、API の使用状況を監視して、問題だけでなく傾向も把握できます。

API Connect 管理は、新しい GraphQL API と既存の REST API を統合すると同時に、新しい StepZen GraphQL API に最高クラスのセキュリティも提供します。脅威保護、レート制限、収益化はすべて、すべてのトランザクションの入力 GraphQL クエリの高度にカスタマイズされた分析に基づいて行うことができ、ユーザーによるわずかな宣言的アサーションが必要です。スキーマのどの部分がより高価であるかを API Connect に伝えると、API Connect はそれを顧客からのすべてのクエリに合わせてカスタマイズします。

このラボが終了するまでに、StepZen と API Connect を組み合わせて、異種のバックエンド (バックエンド間のリンクを含む) を単一の API に結合するための世界クラスのシステムをデプロイし、API を保護し、顧客にソーシャル化して、その呼び出しを監視しました。

始めましょう！

***

## 前提条件

IBM API Connect 環境が必要です。このラボの一環として、AWS で IBM API Connect as a Service を使用します。アカウントをお持ちでない場合は、30 日間の試用アカウントを作成するために、次の手順に従ってください <a href="https://ibm-integration.github.io/learninghub/labs/trial-aws/#1-start-your-ibm-api-connect-trial-on-aws" target="_blank">documentation</a> 

StepZen アカウントが必要です。StepZen は、開発者が GraphQL API を構築する簡単な方法を提供します。StepZen は宣言型プログラミング アプローチ (HOW を明示的に指定せずに、プログラムが何を行うかを記述する) を採用しており、その結果、コードがより小さく直感的になり、実行時のパフォーマンスが向上し、価値実現までの時間が短縮されます。StepZen は柔軟性が非常に高いように設計されています。他の API アプローチと互換性があり、サービスとして (SaaS) で利用できるほか、プライベート クラウドやオンプレミス データ センターでの展開もサポートしています。アカウントをお持ちでない場合は、無料の StepZen アカウントを使用して開始できます。(クレジットカードは必要ありません)。 <a href="https://stepzen.com/signup" target="_blank">here</a>

***

## ビジネスの背景

あなたの会社は、API の新しい標準として GraphQL に投資することを決定しました。GraphQL は API 用のクエリ言語であり、REST API リクエストと比較して、アプリケーション クライアントが API リクエストで取得するデータをより詳細に制御できるようになります。

あなたは、開発者があらゆる場所に保存されているデータを使用して GraphQL API を構築する簡単な方法を模索したいと考えています。電子商取引アプリケーションを例に考えてみましょう。GraphQL は、1 回の呼び出しで、顧客情報、注文番号、配送ステータスなど、さまざまなサブシステムにあるデータを結合し、期待される形式で返すことができます。GraphQL API はアプリケーション チームにとって非常に使いやすいものですが、その構築、セキュリティ保護、ソーシャル化、管理を担当する API チームにとっては課題となる可能性があります。これらの API の構築プロセスを容易にするために、データへのフェデレーション アクセスのための宣言的アプローチを使用して GraphQL API を作成する方法を検討したいと考えています。

一方、開発者は、社内での GraphQL API の使用管理に問題を抱えています。

GraphQL には、REST API に比べて次のような特別な利点があります。

  - アプリケーションクライアントは、必要なデータのみをリクエストできます。たとえば、銀行口座レコードを取得する場合は、各口座の口座番号と現在の残高のみを要求し、顧客名や住所の詳細は要求しません。REST API リクエストでは、バックエンド REST サービスがさまざまなデータ サブセットに個別のエンドポイントまたはパラメータを提供するか、アプリケーション クライアントが完全なレコードを取得して不要なデータを破棄する必要があります。

  - アプリケーション クライアントは、単一のリクエストで複数の関連リソースを取得できます。たとえば、顧客の銀行口座レコードには、顧客が保有する他の金融商品を参照する配列が含まれる場合があります。アプリケーション クライアントが特定の顧客の銀行口座の詳細と、その顧客の他の金融商品の詳細を取得したい場合、クライアントは REST API を使用してまず銀行口座の詳細を取得し、次にそれぞれの銀行口座の詳細を個別にリクエストします。他の製品。GraphQL API は、クライアントが 1 回のリクエストでこのすべての情報を取得できるように設計できます。

ただし、この柔軟性にはレート制限に関するセキュリティ上の課題が伴います。これは、一見非常によく似た 2 つのリクエストが、非常に異なる量のデータを返す可能性があり、複数の REST API リクエストが必要であったものが、それぞれがレート制限にカウントされる可能性があるため、単一の GraphQL API リクエストしか必要としない可能性があるためです。 。したがって、取得されるデータの量を反映するレート制限制御を課すことが重要です。

***

## ラボの概要

このラボでは、GraphQL ドメインでゼロからエンタープライズに移行する方法を学びます。最初に、StepZen を使用して、異なるソース (REST API と MySQL) からデータを取得してフェデレーション GraphQL API を作成する方法を学びます。その後、IBM API Connect を使用して、StepZen からバックエンド GraphQL サーバーをプロキシする GraphQL API プロキシ定義を作成し、GraphQL API へのリクエストによってサーバーから返されるデータ量を反映するレート制限制御を定義します。

このラボでは、次のセクションを完了します。

  - 1 - Node.JS をインストールする
  - 2 - IDE をインストールする
  - 3 - StepZen のセットアップ
  - 4 - REST API から GraphQL API を構築する
  - 5 - GraphQL API に新しい REST API を追加する
  - 6 - MySQL データベースから GraphQL スキーマを自動生成する
  - 7 - @materializer を使用してビルディング ブロックのコンポジションを作成する
  - 8 - APIC で GraphQL プロキシ API を作成する
  - 9 - GraphQL プロキシ API の編集とテスト
  - 10 - プロダクトを作成し、GraphQL RateLimits を適用する
  - 11 - 開発者ポータルから API を探索する

***

## 1 - Node.JS をインストールする


このセクションでは、Node.JS をマシンにインストールします。始めましょう！

1. ラボ環境を起動し、ブラウザを開きます。

![](images/install-ide-1.png)

2. <a href="https://nodejs.org" target="_blank">下記URLURL</a>を開きます (1). そして、推奨されるnode.jsバージョンをダウンロードしてください。
```
https://nodejs.org
```

![](images/install-node-1.png)

3. Nodeのインストールモジュールをマシンに保存し、実行します。

![](images/install-node-2.png)

4. デフォルト値を受け入れ、 **Install** をクリックしてインストールを完了します。

![](images/install-node-3.png)

5. 完了したら **Finish** をクリックします。


***

## 2 - IDE をインストールする

**統合開発環境 (Integrated Development Environment:IDE)** は、プログラムの開発、コンパイル、リンク、デバッグに必要なものがすべて含まれたソフトウェアです。さらに、IDE には通常、統合ヘルプ、名前補完、自動フォーマット、場合によってはバージョン管理システムなど、その他の便利な編集機能が多数バンドルされています。したがって、これらすべてのことを個別に実行することもできますが、IDE をインストールして、単一のインターフェイスからすべてにアクセスできるようにする方がはるかに簡単です。

このラボでは、IDE を使用して GraphQL スキーマを調査します。好みの IDE を使用してください。特に希望がない場合は、以下の手順に従って Visual Studio Code をインストールできます。

1. ブラウザで <a href="https://code.visualstudio.com/Download" target="_blank">下記URL</a> を開きます(1). そして、お使いの OS に固有の VSCode ユーザー インストーラーをダウンロードします (2).
```
https://code.visualstudio.com/Download
```

![](images/install-ide-2.png)

2. VSCode インストールをマシンに保存し、実行します。

![](images/install-ide-3.png)

3. インストール手順に従って完了します。

![](images/install-ide-4.png)

4. 最後に、**Launch Visual Studio Code** オプションをチェックし、**Finish** をクリックします。

![](images/install-ide-5.png)

5. **Welcome** タブを閉じても構いません。

![](images/install-ide-6.png)

6. **Terminal** メニューを開き**New Terminal** をクリックします。

![](images/install-ide-7.png)

7. 素晴らしい！Visual Studio Code の下部にターミナル ウィンドウが表示されるはずです。以下のコマンドを入力して、ノードのインストールが正常かどうかを確認します (コマンドの結果として、ノードのバージョンが表示されるはずです)。
```
node -v
```

![](images/install-ide-8.png)

8. Windows マシンを使用している場合は、VS Code ターミナルでスクリプトを実行できるように PowerShell 実行ポリシーを変更する必要があります。実行ポリシーは、PowerShell セキュリティ戦略の一部です。実行ポリシーは、PowerShell プロファイルなどの構成ファイルをロードできるかどうか、またはスクリプトを実行できるかどうかを決定します。やりましょう！Visual Studio Code のターミナル ウィンドウで、以下のコマンドを実行します。
```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Bypass
```

![](images/powershell-policy-1.png)

  それだ！これでラボの準備が整いました。息を整えて、ラボを楽しんでください。

***

## 3 - StepZen のセットアップ

このセクションでは、StepZen の使用を開始します。StepZen CLI をインストールし、StepZen アカウントでログインします。StepZen アカウントをお持ちでない場合は、前提条件セクションの作成方法を確認してください。

StepZen を使用すると、開発者は複数のバックエンドから必要なデータを取得する単一の GraphQL API を簡単に構築してデプロイできます。StepZen CLI は、StepZen API を作成、アップロード、デプロイ、テストするための主要なツールです。StepZen CLI を使用すると、StepZen のスキーマ、構成、エンドポイントを管理できます。CLI には、ブラウザーからローカルにデプロイした API を探索およびテストできる組み込みの Schema Explorer も付属しています。StepZen CLI は npm 経由で利用できるので、インストールしましょう。

1. ターミナルで以下のコマンドを実行して StepZen CLI をインストールします。
```
npm install -g stepzen
```

![](images/setup-sz-1.png)

2. それでは、StepZenAccount でログインしてみましょう。ブラウザ ウィンドウに戻り<a href="http://www.stepzen.com" target="_blank">下記URL</a> を開きます(1) **Log In** link をクリックします(2).
```
http://www.stepzen.com
```

![](images/setup-sz-2.png)

3. 個人アカウントをお持ちの場合は、ログインしてください。ラボの所有者から提供されたアカウントを使用している場合は、受け取ったユーザー名とパスワードを使用してログインします。

![](images/setup-sz-3.png)

4. StepZen ダッシュボード ページの左側のメニューで、**Account**ページ (鍵アイコン) を開きます。

![](images/setup-sz-5.png)

5. ここには、CLI を使用してログインするために必要な情報がすべて揃っています。**Account**名 (1) と**Admin Key**(2)。それらは次のステップで使用します。

![](images/setup-sz-6.png)

6. Visual Studio Code ターミナル ウィンドウで、以下のコマンドを実行して StepZen CLI にログインし、[your_account]をアカウント ページのアカウント値 (1) に置き換えます。

```
stepzen login -a [your_account]
```

![](images/setup-sz-7.png)

7. 次に、管理者キーを入力する必要があります。「アカウント」ページから管理者キーの値 (2) をコピーして貼り付けます。

![](images/setup-sz-8.png)

  これで、graphQL API を構築する準備が整いました。
  
***

## 4 - REST API から GraphQL API を構築する

StepZen CLI を使用すると、REST インターフェイスを備えたバックエンド用の GraphQL API を数分で作成できます。

REST バックエンドがある場合、StepZen を使用して GraphQL API を作成するには 2 つの方法があります。

  - コマンドライン インターフェイス (CLI) コマンド stepzen import curl を使用して、既存の REST エンドポイントを指定します。StepZen はエンドポイントをイントロスペクトし、GraphQL スキーマを自動生成します。
  - スキーマ コードを .graphql GraphQL スキーマ定義言語 (SDL) ファイルに記述します。強力な GraphQL ディレクティブ @rest を使用して REST エンドポイントに接続すると、わずか数行のコードで機能するスキーマが完成します。)

このセクションでは、既存の REST API で stepzen importcurl を使用する方法を学習します。このコマンドは、curl リクエストを StepZen に送信し、JSON レスポンスから GraphQL タイプを解析します。

GraphQL API を構築する前に、新しいディレクトリを作成し、このディレクトリ内に StepZen ワークスペースを初期化しましょう。

Visual Studio Code ターミナルで以下のコマンドを実行して新しいディレクトリを作成します。

1. Visual Studio Code ターミナルで以下のコマンドを実行して新しいディレクトリを作成します。
```
mkdir product-demo
```

![](images/build-rest1-1.png)

2. 新しいディレクトリに変更します。
```
cd product-demo
```

![](images/build-rest1-2.png)

3. 現在のディレクトリで StepZen ワークスペースを初期化する必要があります。以下のコマンドを実行します。
```
stepzen init --endpoint=api/product-demo
```

![](images/build-rest1-3.png)

4. 次に、StepZen を利用して REST エンドポイントをイントロスペクトし、GraphQL スキーマを自動生成しましょう。ここでは、事前に作成された REST API を使用します。
```
stepzen import curl "https://introspection.apis.stepzen.com/customers" --query-name "customers"
```

![](images/build-rest1-4.png)

5. 無事、最初の GraphQL API が作成されました。graphQL スキーマを調べてみましょう。Visual Studio Code で, **Explorer** icon をクリックし(1) **Open Folder** をクリックします(2).

![](images/build-rest1-5.png)

6. 新しく作成した **product-demo** フォルダーを選択し (1) **Select Folder** をクリックします(2).

![](images/build-rest1-6.png)

7. 必要であれば **Yes, I trust the authors** ボタンをクリックします。

![](images/build-rest1-7.png)

8. GraphQL スキーマを確認するには、**curl** フォルダーを開き **index.graphql** ファイルを選択します (1)。 .graphQL ファイルをチェックしてください (2)。

![](images/build-rest1-8.png)

9. 必要に応じて、 **View > Terminal** をクリックして、ターミナルウィンドウを再度表示します。

![](images/build-rest1-9.png)

  この GraphQL はまだデプロイしません。その前に、別の REST エンドポイントをインポートしましょう。
  
***

## 5 - GraphQL API に新しい REST API を追加する

このセクションでは、別のエンドポイントをインポートします。やりましょう！

1. 以下のコマンドを実行して、別の REST API をインポートします。
```
stepzen import curl "https://introspection.apis.stepzen.com/orders" --query-name "orders" --query-type "Order"
```

![](images/build-rest2-1.png)

2. 新しいgraphQLスキーマを確認するには **curl-01** フォルダーを開き、新しい **index.graphql** ファイルを開きます (1). 新しいスキーマを試してみてください (2).

![](images/build-rest2-2.png)

3. 3番目のスキーマとしてOpen the third schema, the **index.graphql** file in the **product-demo** folder (1) and check this schema is referencing the other two schemas (2).

![](images/build-rest2-3.png)

4. Now, you are able to run the command below to initialize your endpoint.
```
stepzen start
```

![](images/build-rest2-4.png)

This command does three things
  - Deploys the code in the current directory (or the directory provided via the --dir flag) to the specified endpoint on StepZen.
  - Watches the directory for changes and automatically deploys them to the endpoint specified.
  - Share a URL with StepZen's Schema Explorer that enables you to test your API by exploring the queries and types available and querying the API running on StepZen.

![](images/build-rest2-4-2.png)

5. The StepZen dashboard provides a playground for testing your GraphQL API. Let's open it to explore our GraphQL API. Scroll down your terminal page to see the Dashboard URL of your API. Copy and paste it in you browser window.

![](images/build-rest2-5.png)

6. In StepZen Dahsboard you can play with different queries. Go ahead and click **Execute Query** button (1) to test the orders query.  Check the result data (2).

![](images/build-rest2-6.png)

7. You are welcome to play with the Builder section (1), to create queries with different values. For example, delete the order query, and create a customers query with some fields (2). Execute the query again (3) and check the result data (4).

![](images/build-rest2-7.png)

  With these results, we are consuming data from two different REST APIs. And you can do that with APIs from different types of data sources as well.  In the next section, you will inspect data from a MySQL database.

***

## 6 - Autogenerate GraphQL Schemas from MySQL Database

There are two ways to create your GraphQL API with StepZen when you have a SQL database backend.
  - Use the command-line interface (CLI) command stepzen import [mysql | postgresql] to specify your database - StepZen introspects it and auto-generates a GraphQL schema for you.
  - Write your schema code in a .graphql GraphQL Schema Definition Language (SDL) file. Use the GraphQL directive @dbquery to connect the database, and with just a few lines of code, you have a working schema.)

In this section, you will learn how to use stepzen import mysql. In this lab, you will use a sample MySQL database from StepZen.

1. Back to your terminal, cancel the current execution (CTRL+C). And execute the command below to create a GraphQL API that connects data from a database backend.
```
stepzen import mysql --db-host='db.introspection.stepzen.net' --db-database='introspection' --db-user='testUserIntrospection' --db-password='HurricaneStartingSample1934' --name=mysql
```

![](images/build-mysql-1.png)

2. To check the new graphQL schema, open the **mysql** folder and open the new **index.graphql** file (1). You are welcome to explore the new schema (2).

![](images/build-mysql-2.png)

  Before deploying the new API, in the next section you will merge the MySQL database and REST API endpoints.

***

## 7 - Creating a composition of building blocks using @materializer

Now that you have multiple subgraphs, you can link types across subgraphs with @materializer. Let's do it!

1. On the **index.graphql** from **mysql** folder (1), scroll down to see the ‘*type Query*’ declaration. Below the sentence "**Queries for type ‘Address’**" include the query code below (2).
```
getAddressById(id: Int!): [Address]
@dbquery(
  type: "mysql"
  query: """
  SELECT * FROM `address` where `id` = ?
  """
  configuration: "mysql_config"
)
```

  This code is defining a getAddressById query to select address from mySQL database.

![](images/merge-blocks-1.png)

  **Save** the file (File > Save or CTRL+S).

2. Now open the **index.graphql** file from **curl** folder (1), this is the schema from customers REST API.  Scroll down to see the ‘*type RootEntry*’ section.  By now, the address is coming from the REST API endpoint. Let's change it to get this value from MySQL database. Replace the current address type definition (address: Address) for the code below (2).
```
address: [Address]
  @materializer (query: "getAddressById")
```

![](images/merge-blocks-2.png)

  **Save** the file (File > Save or CTRL+S).

3. Let's deploy the new API. And refresh the StepZen Dashboard.
```
stepzen start
```

![](images/merge-blocks-3.png)

4. On the StepZen Dashboard page, use the Builder section (1), to create a customers query including address attributes (2). Execute the query again (3) and check the result data is coming from Rest and MySQL database (4).

![](images/merge-blocks-4.png)

  Great! You created a GraphQL API by doing a composition from REST API and MySQL database. Next section you will see how to use IBM API Connect to manage this API.

5. Before you move to APIC section, take a copy of your API endpoint (1) and the Authorization header (2). You will need them later to invoke your API.

![](images/merge-blocks-5.png)

One important point to highlight here is about how StepZen controls access to GraphQL schemas and endpoints.

As you build out your GraphQL APIs, you will want to add access control mechanisms to prevent unauthorized use of these endpoints. StepZen supports two different solutions for this problem.
  - API Keys: You can use API keys to control access to the entire endpoint. API keys are the default access control mechanism.
  - Field Policies: You can use Field policies to control access to specific entry point fields on the endpoint. Field policies provide fine-grained access control to your GraphQL API, using a model similar to attribute-based access control.

StepZen provides two different types of API keys for use with an account: Admin Keys and API Keys. Admin keys provide administrative-level access to your account, and should only be used at development time. API keys provide more limited access to your account, and should be used for production.

In this lab, for simplification purpose, you will use the Admin Keys to access your API. In a real environment, you should use API Keys or Field Policies to improve your API’s security.

***

## 8 - Create a GraphQL Proxy API in APIC

IBM API Connect enables you to create a GraphQL API proxy definition that proxies a backend GraphQL server. API Connect extends the GraphQL standard by providing, in a GraphQL API definition, the ability to configure a range of settings that are used to calculate the complexity of a GraphQL request and an associated cost that counts towards the rate limit.

For this part of the lab, you need to have an API Connect environment. If necessary, check the Prerequisites section to learn how to create your API Connect on AWS Trial Account.

1. If you received a lab account from your lab monitor, you need to open <a href="https://privateemail.com/" target="_blank">your email inbox</a> to get your APIC environment URL.  On your inbox (log in with your lab user and password), search for **IBM SaaS** (1), open the "**Your API Connect trial is ready**" email (2).

![](images/apic-proxy-1.png)

2. Now, click **Access trial** button.

![](images/apic-proxy-2.png)

3. Log in with your APIC user and password (same user and password received from your lab monitor or using the account that you created).

![](images/apic-proxy-3.png)

4. Here, you are on your API Connect Enterprise as a Service environment. API Connect Enterprise as a Service is a cloud-based edition of IBM API Connect. Using API Connect Enterprise as a Service enables you to work in the cloud to create, manage, secure, and socialize APIs using our latest user experiences, innovation, and industry standards for full API lifecycle management.

  API Connect Enterprise as a Service uses software-as-a-service as a delivery model. With this model, API Connect is hosted on Amazon Web Services and is managed by IBM. You pay for using the software without worrying about owning and maintaining the underlying infrastructure. With API Connect Enterprise as a Service, you pay for usage through your AWS bill.

  Let's see how to create a GraphQL Proxy API.  On the **Home** page (1), scroll down and click on **Develop API** tile (2).

![](images/apic-proxy-4.png)

5. Then click **Add->API**.

![](images/apic-proxy-5.png)

6. To create a GraphQL proxy, select **From Existing GraphQL service (GraphQL proxy)** (1). When you point to an existing GraphQL server, API Connect introspects the service and automatically creates a GraphQL proxy service. Then click **Next** (2).

![](images/apic-proxy-6.png)

7. Enter the following values:

   Title: **customers** (1)
   GraphQL server URL: [*Your API URL copied from StepZen Dashboard*] (for example: https://wanaka.stepzen.net/api/product-demo/__graphql) (2)

![](images/apic-proxy-7.png)

8. As described earlier in this lab, your StepZen API is using an API Key approach to control access to the entire endpoint. Because of that, you need to include the API Key in the Authorization Header of the HTTP Header. Here you will include that to read the API Schema for introspection to setup this proxy API, and it will be used this one time only and not be saved for later to call the API itself. Let's do it!

   In the *HTTP Header* section, click **Add** (1) to enter **Authorization** (2) as *Header* and paste the *API Key value* that you copied from the *StepZen Dashboard Headers* section as *Value* (3). Then click *Next* (4).

![](images/apic-proxy-8.png)

9. The schema validator reports warning and errors if found. Ignore the Schema warning by now, will fix this warning in later steps. In the Paths section, select **all** the available endpoints (1), then click **Next** (2).

![](images/apic-proxy-9.png)

10. Keep both **Secure using Client ID** and **CORS** checked (1) and click **Next** (2).

![](images/apic-proxy-10.png)

11. Great! API Connect successfully created a GraphQL proxy API.

![](images/apic-proxy-11.png)

***

## 9 - Editing and Testing the GraphQL Proxy API

1. Now, let’s edit the API to view more details on the proxy API just created. Click **Edit API** to continue.

![](images/apic-edit-1.png)

2. GraphQL APIs are structured the same as REST APIs with some additional options. Just like REST APIs, you will be able to add security schemas, paths and definitions from the left menu bar. You can also view the *Gateway*, *Test* and *Explorer* tabs similar to REST APIs. You will notice a new tab for GraphQL APIs. Click on **GraphQL Schema** tab to view the schema.

![](images/apic-edit-2.png)

3. The GraphQL Schema tab displays Type  for every type in your GraphQL schema, and Type Weight information for the cost or expense of each type. The weighting factor is used when calculating the type cost for a request to the GraphQL API. For example, a field that requires extensive CPU or memory use on the server to retrieve its value would be given a higher cost. Click **View** in the *Warning* message.

![](images/apic-edit-3.png)

4. In addition to the warning details, the Warning window gives an option to fix the warning by applying the limits. While this Artificial Intelligence is often very accurate, for a real scenario it is important to carefully examine the results and only accept them when they are accurate, since this affects the security of your application.  In our case, click **Apply all** (1), then click **Apply** (2).

![](images/apic-edit-4.png)

5. After applying the recommendations, the warning message is removed. Click **Save** to save the API definition .

![](images/apic-edit-5.png)

6. Now, let’s open the **Gateway** view.

![](images/apic-edit-6.png)

7. The flow is automatically created as part of the initial API creation. You may apply additional logic by dragging and dropping items from the palette to the canvas. Let's do a small change to allow Authorization header propagation. Scroll down the flow (1) and on the **Otherwise** ramification (2),  you should see a **graphql-invoke** node, click on it to edit (3).

![](images/apic-edit-7.png)

8. On the *graphql-invoke* node definition, scroll down to see the *Header control* section. Click on **Add allowlist** to add a new header in the list.

![](images/apic-edit-8.png)

9. Enter **Authorization** as the new header allowed (1) and click **Save** button (2). This means that we will send the Authorization header on to the backend.

![](images/apic-edit-9.png)

10. Now, let's test the API. To publish the API toggle the button from offline to **online**.

![](images/apic-edit-10.png)

11. After successfully publishing the API to API Gateway, additional tabs appear on the screen. Select **Test** tab to test the API.

![](images/apic-edit-11.png)

12. The Test feature also includes a GraphQL Editor. Enter the following GraphQL query in the GraphQL Editor. It is not JSON, but looks somewhat similar to the JSON that will come back as the response.  You may use **Prettify** option to improve the visualization of the GraphQL query.
```
{
  customers {
    email
    id
    name
    address {
      city
      countryRegion
      postalCode
      stateProvince
    }
  }
}
```

![](images/apic-edit-12.png)

13. Now you need to include the Authorization heard. Open the **Parameters** tab.

![](images/apic-edit-13.png)

14. Everytime that you invoke your API you need to pass your API Key as the Authorization header. So let's include it in our test. On the bottom of the Parameters list, include a new parameter with the following value:

    Key: **Authorization** (1)
    Located In: **header** (2)
    Value: *[paste the API Key value that you copied from the StepZen Dashboard Headers]* (3)

![](images/apic-edit-14.png)

15. Now click the **Send** button (1) and open the **GraphiQL** tab (2) again to see the result.

![](images/apic-edit-15.png)

16. On the Trace section, you should see an HTTP Status: 200 (1) and in the Response data you have the data returned from your GraphQL API (2).

![](images/apic-edit-16.png)

17. Great, but you can simplify it, by hard coding the Authorization header parameter in your GraphQL API Proxy flow. Let's do it! Open the **Gateway** tab again.

![](images/apic-edit-17.png)

18. On the **Otherwise** (1) which starts with a *Parse*, you will add a node before the *graphql-invoke* node.  On the *Palette* view, scroll down to see the *Policies* section (2). Drag and drop the **Set Variable** (3) node between the "*ratelimit expected*" node and the "*graphql-invoke*" node (4).

![](images/apic-edit-18.png)

19. Enter **set-authorization** as Title (1) and click **Add action** (2).

![](images/apic-edit-19.png)

20. Keep **Set** (1) as the type of the action. On the Set field, enter **message.headers.Authorization** (2) as the name of the variable to be set. Select **String** (3) as type of the value to set. And in the *Value* field, paste the *API Key value that you copied from the StepZen Dashboard Headers* (4).

![](images/apic-edit-20.png)

21. Then click **Save**.

![](images/apic-edit-21.png)

22. Let's test our API again, this time without passing the Authorization token. Open the **Test** tab (1), and click the **Execute Query** button (2). (Note: if you want, you can check in the Parameters tab that there isn't an Authorization header parameter).

![](images/apic-edit-22.png)

23. Great! Now your GraphQL Proxy is running and available to be used. You are welcome to change the GraphQL query to test more scenarios. You can also use the **Example** button to help start your creativity. Next section you will learn how to create a product to apply GraphQL RateLimits. On breadcrumbs, return to **Develop** page.

![](images/apic-edit-23.png)

***

## 10 - Create a Product and apply GraphQL RateLimits

1. Click **Add->Product**.

![](images/apic-product-1.png)

2. Select **New product** (1) and click **Next** (2).

![](images/apic-product-2.png)

3. Name the product as **Customers Product** (1) and click **Next** (2).

![](images/apic-product-3.png)

4. Add Customers API to the product by selecting **customers** (1). Then click **Next** (2).

![](images/apic-product-4.png)

5. The *Default Plan* contains traditional rate limiting options, but in the next steps, you will be able to list GraphQL Rate Limits. For now, just click **Next**.

![](images/apic-product-5.png)

6. Publish the Product to Sandbox Catalog by selecting **Publish product** (1). Accept the default for *Visibility* and *Subscribability* (2) and click **Next** (3).

![](images/apic-product-6.png)

7. Great! You have your new product. Click **Done**.

![](images/apic-product-7.png)

8. Back to the *Develop* view, open **Products** tab (1) and click on **Customers Product** (2).

![](images/apic-product-8.png)

9. Open the **Plans** section (1), and on the *Default Plan*, open the **context menu** (2) and select **Edit** (3).

![](images/apic-product-9.png)

10. Scroll down, and now you can see the GraphQL rate limits. You will be able to adjust GraphQL cost parameters from this section (including costs per field or type). You can set a limit or make it unlimited. In this tutorial, you will not be making any changes.

    If you want to understand how the GraphQL rate limits work, check this <a href="https://www.ibm.com/docs/en/api-connect/10.0.x?topic=api-securing-graphql-by-using-client-id" target="_blank">documentation page</a>.

![](images/apic-product-10.png)

11. On the left menu, click **Manage** icon to manage our Sandbox catalog.

![](images/apic-product-11.png)

    Next section, you will explore the Developer Portal.

***

## 11 - Explore the API from Developer Portal

Now that you’ve published your API, you need to make sure that your API consumers can discover it and use it. Your Developer Portal will allow customers to view the APIs, sign up and subscribe to plans in a self-service manner, test the APIs, download the OpenAPI - Swagger documents and more. Let’s explore it.

1. Let’s get our Portal URL. On *Manage* page, open the **Sandbox** catalog.

![](images/apic-portal-1.png)

2. Click **Catalog settings** (1) and open the **Portal** tab (2).

![](images/apic-portal-2.png)

3.Great, here you have your **Portal URL**. Copy it, and open it in a new browser tab.

  'Note':  if you don't have a portal URL in your environment, go ahead and create a new portal. It will require a few minutes for the portal to be ready.

![](images/apic-portal-3.png)

4. This Developer Portal is your public-facing website and therefore it is highly flexible and customizable, but we’ll be using the default design.  Note that all of these next steps are simulating what your API Consumer, your end-user customer, will do to find, buy, and use your API.  Click **Create account** to create a new developer account.

![](images/apic-portal-4.png)

5. Complete the registration form, go ahead and use any personal email.  Take note of the username (not email) and password. You will need them later to log in to the Developer Portal.

![](images/apic-portal-5.png)

6. You will receive an email to activate your new developer account.  Click on the link to validate the registration.

![](images/apic-portal-6.png)

7. **Sign in** (1) to Developer Portal using your developer's *username* and *password* (2).

![](images/apic-portal-7.png)

8. Developer Portal displays all the products that are currently published. In your case, no Apps created yet. As a consumer/developer, we’re going to create a new application in the portal. This will give us an API key, allowing us to call our APIs. Click **Create a new App**.

![](images/apic-portal-8.png)

9. Enter **Consumers Application** as the **App Title** (1). Click **Save** (2).

![](images/apic-portal-9.png)

10. On the **Credentials** dialog box, copy the *API Key* (1), copy the *API Secret* (2), then click **OK** (3).

![](images/apic-portal-10.png)

11. You have not subscribed to any APIs, so let’s do it now. Click on **Why not browse the available APIs?** link.

![](images/apic-portal-11.png)

12. Click on **Customers Product 1.0.0**.

![](images/apic-portal-12.png)

13. In the **Default Plan** section, click **Select**.

![](images/apic-portal-13.png)

14. Select the **Consumers Application**.

![](images/apic-portal-14.png)

15. Confirm the subscription by clicking **Next**.

![](images/apic-portal-15.png)

16. Click **Done**.

![](images/apic-portal-16.png)

17. You are now back at the product screen. Let’s explore your API here. Click the **customers 1.0.0 API**.

![](images/apic-portal-17.png)

18.From *Overview* page, you can download the OpenAPI Document and get the API Endpoint. Note the portal has everything you need to call your API. Open the **Try it** tab.

![](images/apic-portal-18.png)

19. Paste the API Key that you copied in the previous step (1). Paste the GraphQL below in the GraphQL editor (2). And click on **Execute Query** button (3).
```
{
  customers {
    email
    id
    name
    address {
      city
      countryRegion
      postalCode
      stateProvince
    }
  }
}
```


![](images/apic-portal-19.png)

20. Great! Your GraphQL Proxy API is running and available for your ecosystem. You are welcome to continue to test the API, using the GraphQL Editor. Submit requests with different field names and watch how quickly the results are returned in the results window. If this was a REST API multiple end points would be needed to achieve the same result.

![](images/apic-portal-20.png)

21. That was the experience as the API Consumer, your paying customer.  Now we return to your experience as an API Provider with an API that is being called, and you have analytics information about the usage of the application.  Open the **Apps** page (1) and select the **Consumers Application** (2).

![](images/apic-portal-21.png)

22. In this page, the developers can view information and insights about the application.

![](images/apic-portal-22.png)

Congratulations! You have successfully completed this lab!


***


## Summary

Let’s summarize what you’ve done today.

In this lab you moved from Zero to Enterprise in the GraphQL domain. Initially you learned how to use StepZen to create a a federated GraphQL API by pulling data from disparate sources (REST API and MySQL). After that you learned how to use IBM API Connect to create a GraphQL API proxy definition that proxies a backend GraphQL API from StepZen, and you verified how to define rate limiting controls that reflect the amount of data that is returned from the server by a request to the GraphQL API.

Check this <a href="https://stepzen.com/docs" target="blank">page</a>, for more technical information about StepZen. And for more information about API Connect Enterprise as a Service, visit this <a href="https://www.ibm.com/docs/en/api-connect/saas?topic=api-connect-enterprise-as-service-overview" target="blank">page</a>.
