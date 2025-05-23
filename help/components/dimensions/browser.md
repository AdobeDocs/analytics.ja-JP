---
title: ブラウザー
description: 使用されたブラウザーの名前とバージョン。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 206df584deab5f6f9b8eeb09d9c8ad4983424eea
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 58%

---

# ブラウザー

「[!UICONTROL &#x200B; ブラウザー &#x200B;]」 [ ディメンション ](overview.md) は、ヒットを送信するブラウザーの名前とバージョンをレポートします。 このディメンションは、訪問者が最も一般的に使用するブラウザーを測定する場合に役立ちます。 サイトの新しいバージョンをテストする場合、このディメンションのトップブラウザーでテストを実行し、品質管理の取り組みを最大限に活かすことができます。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。Adobeは [DeviceAtlas](https://deviceatlas.com/) と提携して、ユーザーエージェントとブラウザー間のルックアップを管理しています。

* AppMeasurement実装の場合、このディメンションは初期設定の状態で動作します。
* Web SDK 実装の場合は、[ データストリームの設定 ](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja) 時に [!UICONTROL &#x200B; デバイス検索 &#x200B;] を有効にします。

## ディメンション項目

ディメンション項目には、使用するブラウザー名とバージョンが含まれます。同じブラウザーの異なるバージョンは、別々のディメンション項目です。

一部のディメンション項目には、バージョン番号の代わりに `"(unknown version)"` が含まれます。このディメンション項目は、Adobeがまだルックアップテーブルに追加していない最新のブラウザーリリースを参照します。 ブラウザーは頻繁に更新されるので、特定のブラウザーの `"(unknown version)"` は、共通で一時的なものです。アドビは、通常、月別メンテナンスリリース時に参照テーブルを更新します。