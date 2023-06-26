---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ要素の概要
feature: Components
role: User, Admin
exl-id: ecc62287-dc20-41b3-9430-f14ea9fc05e6
source-git-commit: 8b10464e8950a9afd647f6d8e08dd75ebdecb46e
workflow-type: ht
source-wordcount: '532'
ht-degree: 100%

---

# データ要素の概要

Analysis Workspace のデータ要素は、ユーザーと管理者の両方が Analytics 環境のコンポーネントを追跡し、よりよく理解するのに役立ちます。

Analytics 管理者は、データ要素の各コンポーネントに関する情報を調整して、ユーザーが利用できるようにする責任があります。

>[!VIDEO](https://video.tv.adobe.com/v/3418028/?quality=12&learn=on)

## ユーザーにとってのメリット

データ要素は、ユーザーが使用可能な各コンポーネントをよりよく理解するのに役立ちます。

データ要素には、次の情報が含まれます。

* コンポーネントの機能と使用目的

* 表示しているコンポーネントで通常使用されるコンポーネント

* 表示しているコンポーネントに類似するコンポーネント

* コンポーネントがシステム管理者によって承認済みであるかどうか

データ要素へのアクセス方法と、データ要素に含まれる情報について詳しくは、[データ要素でのコンポーネント情報の表示](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md)を参照してください。

## 管理者にとってのメリット

データ要素は、システム管理者が Analytics 環境内のコンポーネントを追跡し、キュレートするのに役立ちます。

Analytics 管理者がデータ要素を使用する方法の一部を以下に示します。

* 統合が必要な重複コンポーネントを識別します。

* データを収集していないコンポーネントを識別して、更新または削除できるようにします。

* まだ承認されていないコンポーネントを識別します。

* コンポーネントの説明を Analysis Workspace で直接更新します。データ要素のコンポーネントの説明に対して行われた更新は、レポートスイートに反映されます。

  同様に、レポートスイートのコンポーネントの説明に対して行われた更新は、Analysis Workspace に反映されます。

  コンポーネントの説明を Analysis Workspace またはレポートスイートに追加する方法について詳しくは、[コンポーネントの説明の追加](/help/analyze/analysis-workspace/components/add-component-descriptions.md)を参照してください。

## データ要素へのアクセス

Analysis Workspace 内で、次のいずれかの方法でデータ要素にアクセスできます。

* 左側のパネルの「**データ要素**」アイコンから。

  ![左側のパネルの「データ要素」アイコン](assets/data-dictionary-access-icon.png)

* コンポーネントの情報ポップオーバー内の「**データ要素**」アイコンから。

  ![情報ポップオーバー内の「データ要素」アイコン](assets/data-dictionary-access-infopopover.png)
  <!--update screenshot; this was taken from a mock-->

* [!UICONTROL **ヘルプ**]／[!UICONTROL **データ要素**]&#x200B;メニューから。

データ要素で使用できる様々なオプションについて詳しくは、[データ要素でのコンポーネント情報の表示](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md)を参照してください。

## データ要素の更新とキュレーション

Analytics 管理者は、[データ要素の正常性の監視](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md)で説明しているように、組織のデータ要素を正常に保持する責任があります。

このプロセスの一環として、Analytics 管理者は、[データ要素でのコンポーネントエントリの編集](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)で説明しているように、データ要素内の各コンポーネントに関する情報を編集できます。

## データ要素を移動、最小化または閉じる

データ要素を開くと（[データ要素へのアクセス](#access-the-data-dictionary)で説明しているように）、Analysis Workspace の上にウィンドウとして表示されます。

データ要素ウィンドウは、次のいずれかの方法で操作できます。

* Analysis Workspace 内の任意の領域にドラッグ

  Analysis Workspace を閉じて再度開いた場合、データ要素ウィンドウは最後に移動した場所に残ります。<!--True?-->

* 最小化

  最小化すると、データ要素は、Analysis Workspace の右下隅に青いタブとして表示されます。

  青いタブを選択すると、データ要素が開き、最後に表示していたコンポーネントが表示されます。

* 閉じる
