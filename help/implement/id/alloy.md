---
title: Web SDK JavaScript ライブラリを使用した訪問者の識別
description: Web SDK JavaScript ライブラリを実装する際に、訪問者を正しく識別します。
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%

---

# Web SDK JavaScript ライブラリを使用した訪問者の識別

Adobe Experience Platform Web SDK（`alloy.js`）は、Analytics を含むすべてのAdobe Experience Cloud アプリケーションに対して、統合された最新のデータ収集アプローチを提供します。 ID データを拡張して、XDM の `identityMap` を使用してカスタム ID と複数の名前空間をサポートすることができます。 Adobeでは、高度なシナリオを実現するために、他の ID 管理オプションを使用して、Adobe Experience Cloud ID サービスを Analytics のプライマリ ID として使用することをお勧めします。

組織で Web SDK JavaScript ライブラリを使用してAdobe Analyticsにデータを送信する場合、訪問者の識別に必要な設定は最小限です。 訪問者 ID サービスは、ライブラリにネイティブにベイク処理されます。ただし、**[!UICONTROL コマンドで]** 0&rbrace;Edge Domain&rbrace; を設定する必要があります。 `configure`このフィールドを目的の値に設定すると、追加の設定を行わなくても訪問者の識別が機能します。
