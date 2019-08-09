---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: DFA クエリ文字列パラメーターの更新
solution: Analytics
title: DFA クエリ文字列パラメーターの更新
topic: Data Connectors
uuid: adf585ac-84ff-44c1- a48d- b072726c8494
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# DFA クエリ文字列パラメーターの更新{#update-your-dfa-query-string-parameter}

DFA 統合の前に既に Adobe Analytics で広告キャンペーンをトラッキングしている場合、すべてのキャンペーン（電子メール、検索またはバナー）で同じクエリ文字列パラメーターを使用して、ランディングページ上の参照するキャンペーン ID を識別できます。

DFA 広告キャンペーン用に DFA データからビュースルーおよびクリックスルーデータをいつリクエストするかを理解するには、Data Connectors は、訪問者がいつ DFA キャンペーンバナー広告をクリックしたかを識別する必要があります。これを可能にするために、異なるクエリ文字列パラメーターを DFA 広告キャンペーンのランディングページ URL に追加して、Data Connectors が Web サイトで実施する DFA 広告キャンペーンページと他の広告キャンペーンページを区別できるようにする必要があります。DFAに使用されるJavaScriptプラグイン `dfa_overrideParam` （ ["Webサイトのデータ収集コード](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)の更新」を参照）。

>[!CAUTION]
>
>キャンペーン変数は他のキャンペーンに使用できますが、DFAキャンペーンには使用しないでください。キャンペーン変数を DFA キャンペーンのランディングページに設定すると、アドビはインプレッション数とクリック数を DFA キャンペーンのクリックスルーに結び付けることができなくなります。訪問ごとに 1 度、Adobe コレクションサーバーは、以前のクリックスルーまたはビュースルーについて DFA サーバーをチェックします。このため、DFA プラグインコード（[Web サイトのデータコレクションコードの更新](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)を参照）のみを共通のランディングページに含めて、特に低速インターネット接続を使用するユーザーに対しては、ページ読み込み時間を遅くする不要なリダイレクトをおこなわないようにしてください。

