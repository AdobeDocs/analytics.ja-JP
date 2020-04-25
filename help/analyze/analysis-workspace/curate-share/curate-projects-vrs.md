---
title: VRS およびプロジェクトのキュレーション
description: VRS コンポーネントとプロジェクトのキュレーション方法
translation-type: tm+mt
source-git-commit: db983980a6ec3db4d60bbc8fc3ba57a4e1219287

---


# VRS およびプロジェクトのキュレーション

プロジェクトや仮想レポートスイート（VRS）のキュレーションでは基本的に、コンポーネントを絞り込み、オーディエンスに使用させたいプロジェクト／VRS コンポーネント（ディメンション、指標、セグメント、日付範囲）のみを表示するようにします。

>[!NOTE]
>
>製品プロファイルは、ユーザーに表示されるコンポーネントを管理する主要メカニズムです。これらは、[Admin Console](https://helpx.adobe.com/jp/enterprise/using/manage-products-and-profiles.html#createproductprofiles) から管理されます。キュレーションはセカンダリフィルターです。

キュレーションエクスペリエンスは最近強化されました。Here is an overview of what the **[!UICONTROL Show All]** button reveals, in addition to the curated components already available, in different curated experiences and by permission level:

| キュレーションのタイプ | 管理者 | 非管理者のプロジェクト所有者 | 非管理者 |
|---|---|---|---|
| キュレーションされた VRS | キュレーションされていないすべての VRS コンポーネント | この役割が所有しているか、この役割と共有されているキュレーションされていない VRS コンポーネント | この役割が所有しているか、この役割と共有されているキュレーションされていない VRS コンポーネント |
| キュレーションされたプロジェクト | キュレーションされていないすべてのプロジェクトコンポーネント | キュレーションされていないすべてのプロジェクトコンポーネント | この役割が所有しているか、この役割と共有されているキュレーションされていないプロジェクトコンポーネント |
| キュレーションされた VRS のキュレーションされたプロジェクト | キュレーションされていない、次のすべてのコンポーネント **[!UICONTROL Non-Curated Project Components]** と **[!UICONTROL Non-Curated VRS Components]** | キュレーションされていないすべてのプロジェクトコンポーネントと、この役割が所有する、またはこの役割と共有されている、キュレーションされていない VRS コンポーネント | この役割が所有しているか、この役割と共有されている、キュレーションされていない VRS およびプロジェクトコンポーネント |

>[!IMPORTANT]
>
>VRS キュレーションは常に、プロジェクトのキュレーション前に適用されます。つまり、キュレーションされたプロジェクトに特定のコンポーネントが含まれている場合でも、キュレーションされた VRS に含まれていない場合は除外されます。
