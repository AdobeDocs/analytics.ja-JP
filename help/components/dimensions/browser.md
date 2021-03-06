---
title: ブラウザー
description: 使用されたブラウザーの名前とバージョン。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '178'
ht-degree: 100%

---

# ブラウザー

「ブラウザー」ディメンションは、ヒットを送信するブラウザーの名前とバージョンをレポートします。このディメンションは、訪問者が最もよく使用するブラウザーを把握するのに役立ちます。サイトの新しいバージョンをテストする場合、このディメンションのトップブラウザーでテストを実行し、品質管理の取り組みを最大限に活かすことができます。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、使用するブラウザー名とバージョンが含まれます。同じブラウザーの異なるバージョンは、別々のディメンション項目です。

一部のディメンション項目には、バージョン番号の代わりに `"(unknown version)"` が含まれます。このディメンション項目は、アドビが参照テーブルに追加していない最新のブラウザーリリースを参照します。ブラウザーは頻繁に更新されるので、特定のブラウザーの `"(unknown version)"` は、共通で一時的なものです。アドビは、通常、月別メンテナンスリリース時に参照テーブルを更新します。
