---
title: フィールドベースのステッチ
description: フィールドベースのステッチを使用してデータをステッチする場合の前提条件と制限事項を理解します。
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 23%

---


# フィールドベースのステッチ

デバイス間の分析には、データを結合する2つの異なる方法があります。 この方法は、 [prop](/help/implement/vars/page-vars/prop.md) や [](/help/implement/vars/page-vars/evar.md)eVarなどのAnalytics変数に依存して、個人識別子を格納します。 この変数をベースに、デバイスを相互にリンクします。

## フィールドベースのステッチに固有の前提条件

フィールドベースのステッチを使用してデバイス間の分析を実装する場合は、次の操作が必要です。 組織内のチームやアドビのアカウントマネージャーと協力して、以下のすべての条件を満たすようにします。

>[!IMPORTANT]
>
>すべての前提条件を満たしていない場合、クロスデバイス分析を有効にできないか、データを結び付ける際に結果の質が低下する可能性があります。

* 「 [概要」ページに表示されるすべての前提条件](overview.md)。
* ユーザーがログインしたり電子メールを開いたりする場合など、可能な限り個々のユーザーを一意に識別するpropまたはeVarを設定する必要があります。 この要件は、すべてのプラットフォーム（使用する場合はモバイルアプリを含む）に適用されます。フィールドベースのステッチ用にプロビジョニングされた場合、目的の識別変数をアカウントマネージャーに伝えます。

## フィールドベースのステッチに固有の制限事項

* フィールドベースのステッチは、ユーザーの識別率が高いレポートスイートで最も効果的です。 レポートスイートの識別率またはログイン率が低い場合は、 [Co-opグラフの使用を検討](device-graph.md)。

## 次の手順

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).