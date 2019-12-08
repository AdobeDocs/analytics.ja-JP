---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# javascriptVersion

 変数は、ブラウザーでサポートされている JavaScript のバージョンを示します。


<!-- 

javascriptVersion.xml

 -->

この変数は、ページコードが開始されてから *`doPlugins`* が実行されるまでの間に設定されます。

> [!NOTE]この変数は読み取り専用です。設定しないでください。

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| j | 1.0、1.1、1.2、... 1.7 | 1.7 | トラフィック／技術／JavaScript のバージョン |

JavaScript ファイルのバージョン H.10 以降では、バージョン 1.7（H.10 がリリースされた時点で最新のバージョン）までが正確に検出されます。JavaScript ファイルの前のバージョンでは、バージョン 1.3 までのみが検出されました。
