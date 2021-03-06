---
title: 分類セットを作成
description: 分類セットを作成する際に使用できるフィールドと説明。
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: ht
source-wordcount: '191'
ht-degree: 100%

---

# 分類セットを作成

分類セットマネージャーを使用して、分類セットを作成できます。

>[!NOTE]
>
>この機能は現在、限定リリース中です。この機能へのアクセスをご希望の場合は、アドビカスタマーケアまたは担当のアカウントマネージャーにお問い合わせください。プロビジョニングのリクエストは分類チームに転送されます。

**[!UICONTROL コンポーネント]**／**[!UICONTROL 分類セット]**／**[!UICONTROL セット]**／**[!UICONTROL 追加]**

分類セットを作成する際に、次のフィールドを使用できます。

* **[!UICONTROL 名前]**：分類セットを識別するために使用されるテキストフィールド。このフィールドは作成時には編集できませんが、後で名前を変更できます。
* **[!UICONTROL 列名]**：作成する分類ディメンションの名前。 このフィールドは、Analysis Workspace で使用されるディメンション名で、分類データを書き出す際の列名です。
* **[!UICONTROL タイプ]**：分類のタイプを示すラジオボタン。 通常、プライマリ分類が使用され、ルックアップ分類は[サブ分類](../c-sub-classifications.md)を表します。
* **[!UICONTROL 購読]** この分類セットが適用されるレポートスイートおよびディメンション。複数のレポートスイートのサポートが予定されています。

![分類セットを作成](../assets/classification-set-create.png)

特定のレポートスイート + 変数に分類セットが存在する場合、代わりに分類がスキーマに追加されます。
