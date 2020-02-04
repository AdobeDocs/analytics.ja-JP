---
title: 購入イベント
description: 購入イベントを使用して、「注文件数」、「数量」および「売上高」指標のデータを収集します。
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# 購入イベント

購入イベントは変数内の値で `events` す。 この値は、サイトが生み出す売上高に関するデータを収集する組織に役立ちます。 変数と変数に大きく依存 `products` し `purchaseID` ます。

購入イベントを設定すると、次の指標に影響します。

* 「注文件数」指標は1増分されます
* 「数量」指標は、変数内の製品数だけ増分されま `products` す
* 「売上高」指標は、変数内の価格パラメーターの合計で増加しま `products` す

## Adobe Experience Platform Launchでの購入イベントの設定

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. [イベント セクションを探し、[イベント]ドロップダウンを[購入]に設] 定します 。

となど、その他の依存変数は、「起 `products` 動」に専 `purchaseID` 用フィールドを持っていません。 これらの変数に対して、AppMeasurement構文に従ったカスタムコードエディターを使用します。

## AppMeasurementでの購入イベントの設定とカスタムコードエディターの起動

購入イベントは、イベント変数の一部として設定される文字列です。

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## 購入イベントの重複除外

購入イベントを発生させると、アドビは次の項目を確認します。

* ヒットに変数が含まれてい `purchaseID` るか。 そうでない場合、アドビはヒットの情報を使用して「一時的な購入ID」を作成します。 この一時的な購入 ID は、ヒットの訪問者にのみ適用されます。以前の5つの一時的な購入IDは、レポートスイートごとの訪問者IDごとに保存されます。
* 一時的な購入IDは、保存されている直近5つの一時的な購入IDのいずれかに一致しますか。 一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。
* 変数が定義さ `purchaseID` れている場合、すべての訪問者に対してレポートスイートで既に収集されている値と一致しますか。 一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。
