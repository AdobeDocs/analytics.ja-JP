---
description: Analysis Workspaceでプロジェクトをキュレーションする方法を説明します。 キュレーションでは、プロジェクトを共有する前に、コンポーネントへのアクセスを制限します。
keywords: Analysis Workspace キュレーション
title: プロジェクトをキュレーション
feature: Curate and Share
role: User, Admin
exl-id: 5e23be83-586a-4543-9be9-65c631b8b0b7
source-git-commit: 41d067ab852f4eb5c4a1368ade364fdb706bb9d9
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 60%

---

# プロジェクトのキュレーション

キュレーションを使用すると、プロジェクトを共有する前にコンポーネント（ディメンション、指標、セグメント、日付範囲）を制限できます。受信者がプロジェクトを開くと、自身のためにキュレートしたコンポーネントの限られたセットが表示されます。 キュレーションはオプションですが、プロジェクトを共有する前に行うことをお勧めします。

>[!NOTE]
> 製品プロファイルは、ユーザーに表示されるコンポーネントを管理する主要メカニズムです。Adobe Experience Cloud Admin Console で管理されます。キュレーションはセカンダリフィルターです。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ プロジェクトをキュレーション ](https://video.tv.adobe.com/v/328267?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## プロジェクトキュレーションの適用

1. **[!UICONTROL 共有]**/**[!UICONTROL プロジェクトデータをキュレーション]** を選択します。
プロジェクトで使用されるコンポーネントは自動的に追加されます。
プロジェクトに複数のレポートスイートがある場合、プロジェクト内の各レポートスイートのキュレートドロップターゲットが表示されます。
1. （任意）他のコンポーネントを追加するには、共有するコンポーネントを左側のパネルからデータビューの **[!UICONTROL コンポーネントをキュレーション]** ドロップゾーンにドラッグします。
1. 「**[!UICONTROL 完了]**」を選択します。


![](assets/curation-field.png)

受信者がキュレートされたプロジェクトを開くと、定義したキュレートされたコンポーネントセットのみが表示されます。


## プロジェクトキュレーションの削除

プロジェクトのキュレーションを削除し、左側のレールのコンポーネントの完全なセットを復元するには：

1. **[!UICONTROL 共有]**/**[!UICONTROL プロジェクトデータをキュレーション]** を選択します。
1. **[!UICONTROL キュレーションを削除]** を選択します。
1. 「**[!UICONTROL 完了]**」を選択します。

## 仮想レポートスイートキュレーション

多数のプロジェクトに同時に適用できるように、レポートスイートレベルでキュレーションを適用する場合は、[仮想レポートスイート内のコンポーネントをキュレーション](https://experienceleague.adobe.com/ja/docs/analytics/components/virtual-report-suites/vrs-components)できます。

>[!NOTE]
>
> 仮想レポートスイートキュレーションは常に、プロジェクトのキュレーション前に適用されます。キュレートされたプロジェクトに特定のコンポーネントが含まれている場合でも、キュレートされた仮想レポートスイートにこれらのコンポーネントが含まれていないと、除外されます。
> 

## コンポーネントキュレーションオプション

キュレートされたプロジェクトまたは仮想レポートスイートでは、受信者に、左側のパネルに **[!UICONTROL すべて表示]** コンポーネントを表示するオプションが表示されます。 「[!UICONTROL すべてを表示]」では、以下に応じて異なるコンポーネントセットを表示します。

* ユーザーの権限レベル（管理者／非管理者）
* プロジェクトの役割（所有者／編集者／その他）
* 適用されるキュレーションのタイプ（仮想レポートスイートまたはプロジェクト）
* ユーザーが所有または共有するコンポーネント。 所有／共有コンポーネントには、セグメント、計算指標、日付範囲が含まれます。 eVar、prop、カスタムイベントなど、実装されたコンポーネントは含まれません。

注意：管理者以外の閲覧ロールは、プロジェクトの左側のパネルにアクセスできないので、以下の表から省略されています。

| キュレーションのタイプ | 管理者 | 管理者以外のプロジェクト所有者または編集の役割 | 管理者以外の重複ロール |
|---|---|---|---|
| **キュレートされた仮想レポートスイート** | キュレーションされていないすべての仮想レポートスイートコンポーネント | この役割が所有しているか、この役割と共有されている、キュレーションされていない仮想レポートスイートコンポーネント | この役割が所有しているか、この役割と共有されている、キュレーションされていない仮想レポートスイートコンポーネント |
| **キュレートされたプロジェクト** | キュレーションされていないすべてのプロジェクトコンポーネント | キュレーションされていないすべてのプロジェクトコンポーネント | この役割が所有しているか、この役割と共有されているキュレーションされていないプロジェクトコンポーネント |
| **キュレートされた仮想レポートスイートのキュレートされたプロジェクト** | **[!UICONTROL キュレーションされていないプロジェクトコンポーネント]**&#x200B;および&#x200B;**[!UICONTROL キュレーションされていない仮想レポートスイートコンポーネント]**&#x200B;に表示されるキュレーションされていないすべてのコンポーネント | この役割が所有しているか、この役割と共有されている、キュレーションされていないすべてのプロジェクトコンポーネントおよびキュレーションされていない仮想レポートスイートコンポーネント | この役割が所有しているか、この役割と共有されている、キュレーションされていない仮想レポートスイートおよびプロジェクトコンポーネント |
