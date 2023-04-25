---
title: 開発環境への Adobe Analytics のデプロイ
description: タグを使用して、Adobe Analytics を開発環境にデプロイする方法を説明します。
feature: Launch Implementation
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 48%

---

# 開発環境への Analytics 実装のデプロイ

タグプロパティを作成して設定すると、サイトにライブラリをデプロイしてコードを実装する準備が整います。

## 前提条件 

[Adobe Analytics 用にタグプロパティを作成および設定する](create-analytics-property.md)：ツールにアクセスして、Analytics 実装用のスペースを作成します。

## アダプターと環境の作成

タグは、コードをデプロイする多くの組織的なワークフローに対応しています。Analytics の実装に最低限必要なコンポーネントを作成するには、次の手順に従います。タグ管理者は、組織内で作業して、アドビソリューションをデプロイするための正しいワークフローを確立できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. サイトに実装するタグプロパティをクリックします。
3. クリック **[!UICONTROL ホスト]**&#x200B;を選択し、「 **[!UICONTROL ホストを追加]**.
4. 名前を付ける `"Adobe managed"`を選択し、 **[!UICONTROL 管理者Adobe]** を選択します。 「保存」をクリックします。
5. に移動します。 **[!UICONTROL 環境]**&#x200B;を選択し、「 **[!UICONTROL 環境を追加]**.
6. 選択 **[!UICONTROL 開発]**、という名前を付けます。 `"Dev Environment"`を選択し、ドロップダウンリストからAdobeが管理するホストを選択します。 「**[!UICONTROL 保存]**」をクリックします。
7. Web インストール手順を示すモーダルウィンドウが表示されます。 私たちは後でこの窓に戻る。クリック **[!UICONTROL 閉じる]** 今のところ
8. クリック **[!UICONTROL 環境を追加]**&#x200B;を選択します。 **[!UICONTROL ステージング]**、という名前を付けます。 `"Staging Environment"`をクリックし、管理対象Adobeを選択します。 クリック **[!UICONTROL 作成]**&#x200B;次に、インストール手順モーダルウィンドウを閉じます。
9. クリック **[!UICONTROL 環境を追加]** 再度、 **[!UICONTROL 実稼動]**、という名前を付けます。 `"Production Environment"`をクリックし、管理対象Adobeを選択します。 クリック **[!UICONTROL 作成]**&#x200B;次に、インストール手順モーダルウィンドウを閉じます。

## 開発用ライブラリの構築

ここまでにおこなったすべての変更や設定にもかかわらず、実際にはコードは公開されていません。ライブラリ（変更の集まりのようなもの）を作成すれば、サイトで使用するコードを公開できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. サイトに実装するタグプロパティをクリックします。
3. 次をクリック： **[!UICONTROL 公開フロー]** 「 」タブで、「 **[!UICONTROL ライブラリを追加]**. 詳しくは、 [公開の概要](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=ja) （タグに関するドキュメント）を参照してください。
4. ライブラリに名前を付けます。 `'Initial changes'`をクリックし、開発環境を選択します。
5. クリック **[!UICONTROL 変更されたリソースをすべて追加]**:Adobe Analytics、ID サービスおよびコアが自動的に一覧表示されます。
6. 「**[!UICONTROL 保存]**」をクリックします。
7. 投稿ワークフロー画面に戻り、新しいライブラリの横にあるドロップダウンリストをクリックし、 **[!UICONTROL 開発用にビルド]**. 数秒後、ライブラリの黄色い点が緑色に変わり、ビルドが成功したことを示します。
8. に移動します。 **[!UICONTROL 環境]**&#x200B;をクリックしてから、開発環境の右側にあるインストールアイコンをクリックします。 この操作を実行すると、 Web インストール手順モーダルウィンドウが再び表示されます。
9. コードブロックをコピーして、組織の Web サイト所有者に提供します。

## Web サイトの開発環境にタグをインストール

Web サイトのコードを制御する場合は、コードの各ブロックをそれぞれの場所に実装します。

* メインタグは、 `<head>` タグを使用して貼り付けます。
* タグを同期的に読み込む場合は、終了タグのすぐ下に 2 つ目のコードブロックを含める必要があります `</body>` タグを使用して貼り付けます。 ライブラリタグを同期的に読み込むように選択するには、 **[!UICONTROL ライブラリを非同期で読み込み]** 」オプションを使用して、Web インストール手順を参照してください。

タグコードは通常、サイトの包括的なテンプレートに配置されます。 実装コードのみを含む空白のページは、次のようになります。

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

一般的な理由として、ステージングまたは実稼動環境にプッシュされた他のライブラリに要素が既に存在しているというものがあります。ライブラリを最初に作成する場合は、変更後のリソースのみがライブラリに追加されていることを確認します。

## 次の手順

[Analytics の実装を検証し、実稼動環境に公開する](validate-publish-prod.md)：Adobe Analytics の価値の活用を開始します。
