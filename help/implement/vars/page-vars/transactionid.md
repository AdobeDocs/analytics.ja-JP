---
title: transactionID
description: この変数を使用して、オンラインとオフラインのデータをリンクします。
feature: Appmeasurement Implementation
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 75%

---

# transactionID

`transactionID` 変数は、ヒットが [&#x200B; トランザクション ID データソース &#x200B;](/help/import/data-sources/transactionid.md) を介してアップロードされたデータにディメンション値を提供できるように、トランザクションを一意に識別します。 この変数は、オンラインチャネルデータから収集された値を使用してオフラインチャネルデータに入力する場合に役立ちます。

>[!NOTE]
>
> この変数を使用する前に、レポートスイートで[!UICONTROL トランザクション ID ストレージ]が有効になっていることを確認してください。詳しくは、『管理者ユーザガイド』の「[一般的なアカウント設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)」を参照してください。

`transactionID` でヒットを設定すると、その時点で設定または持続するすべての Analytics 変数の「スナップショット」が作成されます。スナップショットに含まれるディメンションのリストについては、[&#x200B; トランザクション ID データソース &#x200B;](/help/import/data-sources/transactionid.md) を参照してください。 Adobeは、最大 25 か月間、すべてのトランザクション ID 値（リンク済みおよびリンク解除）を記憶します。

## Web SDK を使用したトランザクション ID

トランザクション ID は、次の変数にマッピングされます。

* [XDM オブジェクト &#x200B;](/help/implement/aep-edge/xdm-var-mapping.md):`xdm.commerce.order.payments[3].transactionID` または `xdm.commerce.order.payments.transactionID`
* [Data オブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.transactionID` または `data.__adobe.analytics.xact`

## Adobe Analytics 拡張機能を使用したトランザクション ID

トランザクション ID は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」ドロップダウンリストをAdobe Analyticsに設定し、「[!UICONTROL &#x200B; アクションタイプ &#x200B;]」を [!UICONTROL &#x200B; 変数を設定 &#x200B;] に設定します。
6. 「[!UICONTROL トランザクション ID]」セクションを探します。

トランザクション ID は、データ要素を含む任意の文字列値に設定できます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.transactionID

`s.transactionID` 変数は、トランザクションの一意の ID を含む文字列です。有効な値には、100 バイトまでの英数字が含まれます。デフォルト値は空の文字列です。

```js
s.transactionID = "ABC123";
```

1 回のヒットに対して複数のトランザクション ID がある場合は、それぞれをコンマで区切ることができます。100 バイトの上限は複数のトランザクション ID に対しても適用されます。

```js
s.transactionID = "ABC123,XYZ456";
```

>[!TIP]
>
> この変数を使用して複数のオフラインチャネルを統合する場合は、異なるチャネルがトランザクション ID と重ならないようにしてください。例えば、コールセンターのトランザクション ID の値が `1234` で販売リードのトランザクション ID の値が `1234` である場合、これらが競合し、予期しない結果を引き起こす可能性があります。トランザクション ID には、オフラインチャネルごとに一意の形式が含まれていることを確認し、必要に応じてそれらを区別します。例えば、データソースと AppMeasurement の両方で、コールセンターのトランザクション ID を `call_1234` に設定し、販売リードのトランザクション ID を `lead_1234` に設定します。
