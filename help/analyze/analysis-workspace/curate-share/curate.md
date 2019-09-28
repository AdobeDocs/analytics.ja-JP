---
description: キュレーションを使用すると、プロジェクトを共有する前にコンポーネントを制限できます。社内のマーケティング担当者およびその他のアナリストでないユーザーと、プロジェクトおよびそのコンポーネントを共有できます。プロジェクトに注釈を付けたりタグを適用したりします。
keywords: Analysis Workspace
seo-description: キュレーションを使用すると、プロジェクトを共有する前にコンポーネントを制限できます。社内のマーケティング担当者およびその他のアナリストでないユーザーと、プロジェクトおよびそのコンポーネントを共有できます。プロジェクトに注釈を付けたりタグを適用したりします。
seo-title: キュレーション／共有の概要
solution: Analytics
title: キュレーション／共有の概要
topic: Reports & Analytics
uuid: 267e9678-95a1-4195-8ba4-e8a53c28ea0d
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# キュレーション／共有の概要

キュレーションを使用すると、プロジェクトを共有する前にコンポーネントを制限できます。社内のマーケティング担当者およびその他のアナリストでないユーザーと、プロジェクトおよびそのコンポーネントを共有できます。プロジェクトに注釈を付けたりタグを適用したりします。

**ビデオ概要**

>[!VIDEO](https://www.youtube.com/watch?v=LJJRskdmlOg&index=79&t=0s&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)

**[!UICONTROL Workspace]** /共有 **[!UICONTROL /プロジ]****[!UICONTROL ェクトデータのキュレーション]**

## プロジェクトデータのキュレーション

1. プロジェクトを作成およびキュレーションするための権限を指定します。

   Before creating or curating an Analysis Workspace project, administrators must add you to a [group](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) with the **[!UICONTROL Analysis Workspace Access]** permission enabled, or to the **[!UICONTROL All Report Access]** user group. ( **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]**).

1. [プロジェクトを作成し](../../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md#task_C2C698ACC7954062A28E4784911E6CF2) 、保存して、共有 **[!UICONTROL /プロジェクトデータをキ]** ュレーションをクリックします ****。
1. 共有したいコンポーネントを、左側にあるドラッグ可能なコンポーネントスタックから「**[!UICONTROL キュレートされたコンポーネント]」フィールドにドラッグします。**

   ![](assets/curated-components.png)

   >[!IMPORTANT]
   >
   >プロジェクトを共有する場合は、コンポーネントのキュレーションは必要ありません。 プロジェクトをすべての利用可能なデフォルトコンポーネント、または選択したコンポーネントと共有できます。To preserve all of the default components in a project, a best practice is to create a copy of a project for yourself (using **[!UICONTROL Save As]**) prior to curating components. プロジェクト内でコンポーネントをキュレーションすると、その他のコンポーネントをそのプロジェクトで使用できなくなります。

1. 「**[!UICONTROL 完了]**」をクリックします。

生成されるプロジェクトは、Analysis Workspace の通常のプロジェクトのように動作しますが、選択できるのは指定したコンポーネントだけです。

## キュレーションされたプロジェクトの共有

共有機能を使用すると、このプロジェクトを組織内の他の Analysis Workspace ユーザーも利用できるようになります。他のユーザーがこのプロジェクトを使用する際には、すでに実行したキュレーションがすべて反映されています。

1. After you curate the components of a report, click **[!UICONTROL Share]** &gt; **[!UICONTROL Share Project]**.

   ![](assets/share_component.png)

1. 受信者を追加します。
1. （オプション）埋め込みプロジェクトコンポーネント（セグメント、計算指標、日付範囲）をすべての受信者と共有できます。共有すると、これらのコンポーネントは受信者のワークスペースのコンポーネントドロップダウンに表示されます。

   >[!IMPORTANT]
   >
   >この設定は保持されません。共有時の単数の操作です。

1. オプションで、このページを受信者のランディングページとして設定できます。

   >[!IMPORTANT]
   >
   >この設定は保持されません。共有時の単数の操作です。

1. 「**[!UICONTROL 共有]**」をクリックします。

<!-- 

<p> <b>Annotate and tag a project</b> </p> 
<p>An alternative way to collaborate on a project is to use the Information panel. This panel will be re-introduced in an upcoming release. </p> 
<p> </p> 
<ul id="ul_EFD045FD9F3B4BF8A70637B00EE0BC9C"> 
 <li id="li_EC6C5EAF9C234E76BDA7FF0226B82083">Tag reports for sharing. </li> 
 <li id="li_CF6A438C55F847F8890F8CB674CAA4F7">Specify the recipient (filter by permission group or user name), the storage folder. In-product notifications let users know that they have a shared report waiting. </li> 
 <li id="li_C8E088DA43024277908705CB0F3A142A">Write messages or report descriptions for recipients. </li> 
 <li id="li_342EB4758C344B859757E23691068FA3"> Select the dimensions, metrics, and segments to recommend to a non-analyst colleague, who can view the report you are curating and sharing. Curating the component gives the recipient access to those components, based on their permission settings. </li> 
 <li id="li_6487500F9315481599B7F3897998879F"> Add suggested items to a previously configured report. These new items exist as recommended selectable options. </li> 
</ul>

 -->

