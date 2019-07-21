---
description: 実際に表示されているブラウザーウィンドウのみでの横／縦の長さを示す指標です。具体的には、ブラウザー
seo-description: 実際に表示されているブラウザーウィンドウのみでの横／縦の長さを示す指標です。具体的には、ブラウザー
seo-title: ブラウザーの幅／高さ
solution: Analytics
title: ブラウザーの幅／高さ
topic: 指標
uuid: 1c0d3ea9- e001-4152-9bfc-8fe6406bc755
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ブラウザーの幅／高さ

実際に表示されているブラウザーウィンドウのみでの横／縦の長さを示す指標です。具体的には、ブラウザー

Adobe Analytics では、訪問の初回ヒット時のブラウザーの高さと幅のみを使用します。同じ訪問中の残りのヒットでは、この属性を取得しません。The browser width/height dimensions capture similar but distinct values when compared with [mobile screen size](../../../components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150).

例えば、ブラウザーの幅または高さをモバイル解像度で分類する場合、次の違いを意識する必要があります。

* モバイルデバイスの解像度は、デバイスに関連付けられた物理的な値です。例えば、モバイルデバイスの解像度は、Galaxy S8 は 2,960 x 1,440 と表示されます。モバイルデバイスの解像度は、デバイスが識別されると、サードパーティのサービスから取得されます。
* これに対して、ブラウザーの高さおよび幅の値には、CSS（論理）値の 740 x 360 が表示されます。ブラウザーの値は、JavaScript／CSS データに依存します。
* 詳しくは、[このスレッド](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio)を参照してください。

