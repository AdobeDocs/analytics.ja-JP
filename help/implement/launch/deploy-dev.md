---
title: 開発環境への Adobe Analytics のデプロイ
description: タグを使用して、Adobe Analytics を開発環境にデプロイする方法を説明します。
feature: Tags
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '587'
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
3. **[!UICONTROL ホスト]** をクリックしてから、**[!UICONTROL ホストを追加]** をクリックします。
4. `"Adobe managed"` という名前を付け、「タイプ」ドロップダウンリストで **[!UICONTROL Adobeによって管理]** を選択します。 「保存」をクリックします。
5. **[!UICONTROL 環境]** に移動し、「**[!UICONTROL 環境を追加]**」をクリックします。
6. **[!UICONTROL Development]** を選択して `"Dev Environment"` という名前を付け、ドロップダウン・リストからAdobeが管理するホストを選択します。 「**[!UICONTROL 保存]**」をクリックします。
7. Web インストール手順を示すモーダルウィンドウが表示されます。 後でこのウィンドウに戻ります。ここでは「**[!UICONTROL 閉じる]**」をクリックします。
8. 「**[!UICONTROL Add Environment]**」をクリックし、「**[!UICONTROL Staging]**」を選択して `"Staging Environment"` という名前を付け、Adobeが管理するホストを選択します。 **[!UICONTROL 作成]** をクリックして、インストール手順のモーダルウィンドウを閉じます。
9. **[!UICONTROL Add Environment]** を再度クリックし、「**[!UICONTROL Production]**」を選択し、`"Production Environment"` という名前を付けて、Adobeが管理するホストを選択します。 **[!UICONTROL 作成]** をクリックして、インストール手順のモーダルウィンドウを閉じます。

## 開発用ライブラリの構築

ここまでにおこなったすべての変更や設定にもかかわらず、実際にはコードは公開されていません。ライブラリ（変更の集まりのようなもの）を作成すれば、サイトで使用するコードを公開できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. サイトに実装するタグプロパティをクリックします。
3. **[!UICONTROL 公開フロー]** タブをクリックしてから、「**[!UICONTROL ライブラリを追加]** をクリックします。 このページについて詳しくは、タグドキュメントの [ 公開の概要 ](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=ja) を参照してください。
4. ライブラリに「`'Initial changes'`」という名前を付け、開発環境を選択します。
5. 「**[!UICONTROL 変更されたリソースをすべて追加]**」をクリックすると、Adobe Analytics、ID サービス、コアが自動的に一覧表示されます。
6. 「**[!UICONTROL 保存]**」をクリックします。
7. 公開ワークフロー画面に戻り、新しいライブラリの横にあるドロップダウンリストをクリックして、「開発用にビルド **[!UICONTROL をクリックし]** す。 数秒後、ライブラリの黄色い点が緑色に変わり、ビルドが成功したことを示します。
8. **[!UICONTROL 環境]** に移動し、開発環境の右側にあるインストールアイコンをクリックします。 このアクションを実行すると、web インストール手順モーダルウィンドウが再び表示されます。
9. コードブロックをコピーして、組織の web サイト所有者に提供します。

## Web サイトの開発環境にタグをインストール

Web サイトのコードを制御する場合は、コードの各ブロックをそれぞれの場所に実装します。

* メインタグは、サイトの `<head>` タグに属しています。
* タグを同期的に読み込む場合は、サイトの終了 `</body>` タグのすぐ下に 2 番目のコードブロックを含める必要もあります。 Web インストール手順で「**[!UICONTROL ライブラリを非同期で読み込む]**」オプションを切り替えることで、ライブラリタグを同期して読み込むように選択できます。

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

一般的な理由として、ステージングまたは実稼動環境にプッシュされた他のライブラリに要素が既に存在しているというものがあります。ライブラリを最初に作成する場合は、変更後のリソースのみがライブラリに追加されていることを確認します。

## 次の手順

[Analytics の実装を検証し、実稼動環境に公開する](validate-publish-prod.md)：Adobe Analytics の価値の活用を開始します。
