---
title: transactionID
description: この変数を使用して、オンラインとオフラインのデータをリンクします。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# transactionID

この変数 `transactionID` はトランザクションを一意に識別し、ヒットがデータソースを介してアップロードされたデータに結び付けられるようにします。 この変数は、他のチャネルのデータを使用し、AppMeasurementで収集したデータにリンクする場合に役立ちます。

> [!NOTE] この変数を使用する前に [!UICONTROL 、レポートスイートでトランザクション] IDストレージが有効になっていることを確認してください。 See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

ヒットを設定す `transactionID` ると、その時点で設定または持続するすべてのAnalytics変数の「スナップショット」が作成されます。 一致するトランザクションIDを持つデータソースを通じてアップロードされたデータは、これらの変数値に永続的に結び付けられます。

デフォルトでは、すべてのトランザクションIDの値（リンクおよびリンク解除）は、最大90日間記憶されます。 オフラインのインタラクションプロセスが90日を超える場合は、カスタマーケアに連絡して、この制限を延長してください。

## Adobe Experience Platform LaunchのトランザクションID

トランザクションIDは、Analytics拡張（グローバル変数）の設定時またはルールで設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「 [!UICONTROL Transaction ID] 」セクションを探します。

トランザクションIDは、データ要素を含む任意の文字列値に設定できます。

## AppMeasurementのs.transactionIDおよびカスタムコードエディターの起動

変数 `s.transactionID` は、トランザクションの一意の識別子を含む文字列です。 有効な値には、100バイトまでの英数字が含まれます。 デフォルト値は空の文字列です。

```js
s.transactionID = "ABC123";
```

1回のヒットに対して複数のトランザクションIDがある場合は、それぞれをコンマで区切ることができます。 複数のトランザクションIDには、100バイトの制限が適用されます。

```js
s.transactionID = "ABC123,XYZ456";
```

> [!NOTE] この変数を使用して複数のオフラインチャネルを統合する場合は、異なるチャネルがトランザクションIDと重ならないようにしてください。 例えば、コールセンターのトランザクションIDの値と販売リードのトランザク `1234` ションIDの値を持っている場合、それらのトランザクションは競合し `1234`、予期しない結果を引き起こす可能性があります。 トランザクションIDには、オフラインチャネルごとに一意の形式が含まれていることを確認し、必要に応じてそれらを区別します。 例えば、データソースとAppMeasurementの両方で、コールセンターのトランザク `call_1234` ションIDをに設定し、販売 `lead_1234` リードのトランザクションIDをに設定します。
