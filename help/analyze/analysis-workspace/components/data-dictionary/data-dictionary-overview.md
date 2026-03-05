---
description: Analysis Workspace のデータ辞書を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ辞書の概要
feature: Components
role: User, Admin
exl-id: ecc62287-dc20-41b3-9430-f14ea9fc05e6
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 90%

---


# データ辞書の概要 {#data-dictionary-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="データディクショナリ"
>abstract="データ辞書は、ユーザーと管理者の両方にとって、Analytics 環境のコンポーネントを追跡したり理解を深めたりするのに役立ちます。<br/>Analytics 管理者は、データ辞書内の各コンポーネントに関する情報を調整する責任があります。"

<!-- markdownlint-enable MD034 -->


Analysis Workspace のデータ辞書は、ユーザーと管理者の両方が Analytics 環境のコンポーネントを追跡し、よりよく理解するのに役立ちます。

Analytics 管理者は、データ辞書の各コンポーネントに関する情報を調整して、ユーザーが利用できるようにする責任があります。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace のデータ辞書](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/data-dictionary-in-analysis-workspace){target="_blank"}を参照してください。

>[!ENDSHADEBOX]



## ユーザーにとってのメリット

データ辞書は、ユーザーが使用可能な各コンポーネントをよりよく理解するのに役立ちます。

データ辞書には、次の情報が含まれます。

* コンポーネントの機能と使用目的。

* 表示しているコンポーネントで通常使用されるコンポーネント。

* 表示しているコンポーネントに類似するコンポーネント。

* コンポーネントがシステム管理者によって承認済みであるかどうか。

データ辞書へのアクセス方法と、データ辞書に含まれる情報について詳しくは、[データ辞書でのコンポーネント情報の表示](view-data-dictionary.md)を参照してください。

## 管理者にとってのメリット

データ辞書は、システム管理者が Analytics 環境内のコンポーネントを追跡し、キュレートするのに役立ちます。

Analytics 管理者は、次の目的でデータ辞書を使用できます。

* 統合が必要な重複コンポーネントを識別します。

* データを収集していないコンポーネントを識別して、更新または削除できるようにします。

* まだ承認されていないコンポーネントを識別します。

* コンポーネントの説明を Analysis Workspace で直接更新します。データ要素のコンポーネントの説明に対して行われた更新は、レポートスイートに反映されます。

  同様に、レポートスイートのコンポーネントの説明に対して行われた更新は、Analysis Workspaceに反映されます。

  コンポーネントの説明をAnalysis Workspaceまたはレポートスイートに追加する方法について詳しくは、[&#x200B; コンポーネントの説明の追加 &#x200B;](/help/analyze/analysis-workspace/components/add-component-descriptions.md) を参照してください。

## データ辞書へのアクセス

Analysis Workspace 内で、次のいずれかの方法でデータ辞書にアクセスできます。

![左側のパネルのデータ辞書アイコン](assets/data-dictionary-access.png)

* ボタンパネルの ![ブックマーク](/help/assets/icons/Bookmark.svg) から。



* コンポーネントの情報ポップオーバー内の ![ブックマーク](/help/assets/icons/Bookmark.svg) から。


データ辞書で使用できる様々なオプションについて詳しくは、[データ辞書でのコンポーネント情報の表示](view-data-dictionary.md)を参照してください。

## データ辞書の更新とキュレーション

Adobe Analytics 管理者は、[データ辞書の正常性の監視](monitor-data-dictionary-health.md)で説明しているように、組織のデータ辞書を正常に保持する責任があります。

このプロセスの一環として、Adobe Analytics 管理者は、[データ辞書でのコンポーネントエントリの編集](edit-entries-data-dictionary.md)で説明しているように、データ辞書内の各コンポーネントに関する情報を編集できます。

## データ辞書を移動、最小化または閉じる

データ辞書を開くと（[データ辞書へのアクセス](#access-the-data-dictionary)で説明しているように）、Analysis Workspace の上にウィンドウとして表示されます。

データ辞書ウィンドウは、次のいずれかの方法で操作できます。

* Analysis Workspace 内の任意の領域にドラッグ

  Analysis Workspace を閉じて再度開いた場合、データ辞書ウィンドウは最後に移動した場所に残ります。<!--True?-->

* ウィンドウを最小化します。

  最小化すると、データ辞書は、Analysis Workspace の右下隅に青いタブとして表示されます。

  青いタブを選択すると、データ辞書が開き、最後に表示していたコンポーネントが表示されます。

* ウィンドウを閉じます。


<!--
# Data Dictionary overview

The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment.   

Analytics administrators are responsible for curating information about each component in the Data Dictionary to make it available to users.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data dictionary](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/data-dictionary-in-analysis-workspace){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Benefits for users

The Data Dictionary helps users gain a better understanding of each component that is available to them. 

Information available in the Data Dictionary includes: 

* A component's function and intended use

* Components typically used with the one you are viewing

* Components that are similar to the one you are viewing

* Whether a component is approved by the system administrator 

For information about how to access the Data Dictionary and for details about the information it contains, see [View component information in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Benefits for administrators

The Data Dictionary helps system administrators keep track of and curate the components in their Analytics environment. 

Following are some of the ways Analytics administrators can use the Data Dictionary: 

* Identify duplicate components that need to be consolidated.

* Identify components that aren't collecting any data so they can be either updated or deleted.

* Identify components that are not yet approved.

* Update component descriptions directly in Analysis Workspace. Any updates made to component descriptions in the Data Dictionary are reflected in the Report Suite.

  Similarly, any updates made to component descriptions in the Report Suite are reflected in Analysis Workspace.

  For more information about adding component descriptions in either Analysis Workspace or in a Report Suite, see [Add component descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Access the Data Dictionary

You can access the Data Dictionary in any of the following ways within Analysis Workspace:

* From the **Data Dictionary** icon in the left rail.

  ![Data Dictionary icon in the left rail](assets/data-dictionary-access-icon.png)

* From the **Data Dictionary** icon within the info popover of a component. 

  ![Data Dictionary icon in info popover](assets/data-dictionary-access-infopopover.png)


For detailed information about the various options available in the Data Dictionary, see [View component information in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Update and curate the Data Dictionary

Analytics administrators are responsible for maintaining a healthy Data Dictionary for their organization, as described in [Monitor Data Dictionary Health](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).

As part of this process, Analytics administrators can edit information about each component in the data dictionary, as described in [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

## Move, minimize, or close the Data Dictionary

When you open the Data Dictionary (as described in [Access the Data Dictionary](#access-the-data-dictionary)), it displays as a window on top of Analysis Workspace. 

You can manipulate the Data Dictionary window in any of the following ways:

* Drag it to any area within Analysis Workspace 

  If you close and re-open Analysis Workspace, the Data Dictionary window remains in the location where you last moved it.

* Minimize it

  When minimized, the Data Dictionary appears as a blue tab in the lower-right corner of Analysis Workspace.

  When you select the blue tab, the Data Dictionary opens to the component you were most recently viewing. 

* Close it

-->