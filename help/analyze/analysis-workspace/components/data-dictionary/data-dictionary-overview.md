---
description: Analysis Workspaceのデータディクショナリを使用すると、Analysis Workspaceの様々なコンポーネントをカタログ化し、追跡できます。このコンポーネントには、使用目的や承認済みのコンポーネント、重複などが含まれます。
title: データディクショナリの概要
feature: Components
role: User, Admin
source-git-commit: ce95a239d765afffd91cfd6cda5872c1af02909f
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 0%

---

# データディクショナリの概要

{{release-limited-testing}}

Analysis Workspaceのデータディクショナリは、ユーザーと管理者の両方が、Analytics 環境のコンポーネントを追跡し、より深く理解するのに役立ちます。

システム管理者は、データディクショナリ内の各コンポーネントに関するこの情報をキュレーションし、ユーザーが使用できるようにする必要があります。

## ユーザーのメリット

データディクショナリは、ユーザーが使用できる各コンポーネントをより深く理解するのに役立ちます。

データディクショナリには、次の情報が含まれます。

* コンポーネントの機能と意図された使用

* 通常、表示しているコンポーネントと共に使用されるコンポーネント

* 表示しているコンポーネントに類似したコンポーネント

* コンポーネントがシステム管理者によって承認されているかどうか

## 管理者向けのメリット

データディクショナリは、システム管理者が Analytics 環境でコンポーネントを追跡し、キュレーションするのに役立ちます。

Analytics 管理者がデータディクショナリを使用する方法の一部を次に示します。

* 統合が必要な重複コンポーネントを特定します。

* データを収集していないコンポーネントを特定して、更新または削除できるようにします。

* まだ承認されていないコンポーネントを特定します。

* Analysis Workspaceでコンポーネントの説明を直接更新します。 データディクショナリ内のコンポーネントの説明に対しておこなわれた更新は、レポートスイートに反映されます。

   同様に、レポートスイートでコンポーネントの説明に対して行われた更新は、Analysis Workspaceにも反映されます。

   Analysis Workspaceまたはレポートスイートでコンポーネントの説明を追加する方法について詳しくは、 [コンポーネントの説明を追加](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## データディクショナリへのアクセス

データディクショナリには、Analysis Workspace内で次のいずれかの方法でアクセスできます。

* 次の **データ辞書** アイコンをクリックします。

   ![左側のパネルのデータ辞書アイコン](assets/data-dictionary-access-icon.png)

* 次の **データ辞書** アイコンをクリックします。

   ![情報ポップオーバーのデータ辞書アイコン](assets/data-dictionary-access-infopopover.png)
<!--update screenshot; this was taken from a mock-->

* メニューから、次の操作を実行します。 [!UICONTROL **ヘルプ**] > [!UICONTROL **データ辞書**].

   <!--add screenshot-->

## データ辞書を移動、最小化、または閉じる

データディクショナリを開くとき ( [データディクショナリへのアクセス](#access-the-data-dictionary)) の場合は、Analysis Workspaceの上にウィンドウとして表示されます。

データディクショナリウィンドウは、次のいずれかの方法で操作できます。

* Analysis Workspace内の任意の領域にドラッグします。

   Analysis Workspaceを閉じて再度開いても、データディクショナリウィンドウは最後に移動した場所に残ります。 <!--True?-->

* 最小化

   最小化すると、データディクショナリはAnalysis Workspaceの右下隅に青いタブとして表示されます。

   青いタブを選択すると、最近表示したコンポーネントがデータディクショナリに表示されます。

* 閉じる
