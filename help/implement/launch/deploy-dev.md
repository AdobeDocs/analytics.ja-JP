---
title: 開発環境への Adobe Analytics のデプロイ
description: タグを使用して、Adobe Analytics を開発環境にデプロイする方法を説明します。
feature: Tags
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
role: Admin, Developer
TQID: https://experienceleague.adobe.com/l6uxAdaT4qKfiGWjecrwKzdKHoc-J4Ysc2ebKfmP-w4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 48%

---

# 開発環境への Analytics 実装のデプロイ

タグプロパティを作成して設定すると、サイトにライブラリをデプロイしてコードを実装する準備が整います。

## 前提条件

[Adobe Analytics 用にタグプロパティを作成および設定する](create-analytics-property.md)：ツールにアクセスして、Analytics 実装用のスペースを作成します。

## アダプターと環境の作成

タグは、コードをデプロイする多くの組織的なワークフローに対応しています。 Analytics の実装に最低限必要なコンポーネントを作成するには、次の手順に従います。 タグ管理者は、組織内で作業して、アドビソリューションをデプロイするための正しいワークフローを確立できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. サイトに実装するタグプロパティをクリックします。
3. 「**[!UICONTROL ホスト]**」をクリックし、「**[!UICONTROL ホストを追加]**」をクリックします。
4. `"Adobe managed"`という名前を付け、種類ドロップダウンリストで「**[!UICONTROL Adobeで管理]**」を選択します。 「保存」をクリックします。
5. **[!UICONTROL 環境]**&#x200B;に移動し、**[!UICONTROL 環境を追加]**&#x200B;をクリックします。
6. 「**[!UICONTROL 開発]**」を選択し、「`"Dev Environment"`」という名前を付け、ドロップダウンリストから「Adobe managed host」を選択します。 「**[!UICONTROL 保存]**」をクリックします。
7. Web インストール手順を示すモーダルウィンドウが表示されます。 後でこのウィンドウに戻ります。今は&#x200B;**[!UICONTROL 閉じる]**&#x200B;をクリックしてください。
8. **[!UICONTROL Add Environment]**&#x200B;をクリックし、**[!UICONTROL Staging]**&#x200B;を選択して`"Staging Environment"`という名前を付け、次にAdobe Managed Hostを選択します。 「**[!UICONTROL Create]**」をクリックし、インストール手順モーダルウィンドウを閉じます。
9. **[!UICONTROL Add Environment]**&#x200B;をもう一度クリックし、**[!UICONTROL Production]**&#x200B;を選択し、`"Production Environment"`という名前を付け、次にAdobe Managed Hostを選択します。 「**[!UICONTROL Create]**」をクリックし、インストール手順モーダルウィンドウを閉じます。

## 開発用ライブラリの構築

ここまでにおこなったすべての変更や設定にもかかわらず、実際にはコードは公開されていません。 ライブラリ（変更の集まりのようなもの）を作成すれば、サイトで使用するコードを公開できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. サイトに実装するタグプロパティをクリックします。
3. 「**[!UICONTROL 公開フロー]**」タブをクリックし、「**[!UICONTROL ライブラリを追加]**」をクリックします。 このページについて詳しくは、タグ ドキュメントの[公開の概要](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=ja)を参照してください。
4. ライブラリ `'Initial changes'`に名前を付け、開発環境を選択します。
5. **[!UICONTROL 変更済みのすべてのリソースを追加]**&#x200B;をクリックすると、Adobe Analytics、Identity Service、Coreが自動的に一覧表示されます。
6. 「**[!UICONTROL 保存]**」をクリックします。
7. 公開ワークフロー画面に戻り、新しいライブラリの横にあるドロップダウンリストをクリックし、**[!UICONTROL 開発用にビルド]**&#x200B;をクリックします。 数秒後、ライブラリ上の黄色いドットが緑色に変わり、ビルドが正常に実行されたことを示します。
8. **[!UICONTROL 環境]**&#x200B;に移動し、開発環境の右側にあるインストールアイコンをクリックします。 このアクションにより、Web インストール手順モーダルウィンドウが再度表示されます。
9. コードブロックをコピーし、組織のweb サイト所有者に提供します。

## Web サイトの開発環境にタグをインストール

web サイトのコードを管理する場合は、各コードブロックをそれぞれの場所に実装します。

* メインタグは、サイトの`<head>` タグに属しています。
* タグを同期して読み込む場合は、サイトのクロージング `</body>` タグのすぐ下にある2番目のコードブロックも含める必要があります。 Web インストール手順の「**[!UICONTROL ライブラリを非同期で読み込む]**」オプションを切り替えることで、ライブラリタグを同期して読み込むことができます。

タグコードは、通常、サイトの包括的なテンプレートに配置されます。 実装コードのみを含む空白のページは、次のようになります。

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <!-- Only include this extra code if you load tags synchronously -->
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## トラブルシューティング

**ビルドに失敗しました。**

一般的な理由として、ステージングまたは実稼動環境にプッシュされた他のライブラリに要素が既に存在しているというものがあります。 ライブラリを最初に作成する場合は、変更後のリソースのみがライブラリに追加されていることを確認します。

## 次の手順

[Analytics の実装を検証し、実稼動環境に公開する](validate-publish-prod.md)：Adobe Analytics の価値の活用を開始します。
