---
description: Analysis Workspace でプロジェクトを操作する方法について説明します。プロジェクトマネージャーを使用して、プロジェクトの管理（作成、削除、移動、共有、承認、ピン留め、コピー、タグ付け）を行います。
keywords: Analysis Workspace
title: プロジェクトの概要
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '1680'
ht-degree: 91%

---

# プロジェクトの概要

Workspace プロジェクトでは、パネル、ビジュアライゼーション、コンポーネントを組み合わせて、分析を作成し、組織内の任意のユーザーと共有できます。最初のプロジェクトを開始する前に、プロジェクトへのアクセス方法、プロジェクト間の移動方法、およびプロジェクトの管理方法について説明します。

Adobe Analyticsのプロジェクトにアクセスするには、「**[!UICONTROL Workspace]**」を選択します。  **[!UICONTROL プロジェクト]**&#x200B;マネージャーには、自分が所有するすべてのプロジェクトまたは共有されているプロジェクトが一覧表示されます。環境設定で特に指定しない限り、プロジェクトリストを持つプロジェクトマネージャーもAdobe Analyticsのデフォルトのランディングページになります。

![プロジェクトリストを表示するプロジェクトランディングページ](assets/projects.png)


## タイトル領域

タイトル領域内 ➊ から、プロジェクトの作成、フォルダーの作成、環境設定の編集、追加タイルなどのパネルの表示／非表示を行うことができます。

* 左側のパネルの表示／非表示を切り替えて、**[!UICONTROL プロジェクト]**&#x200B;と&#x200B;**[!UICONTROL 学習]**&#x200B;から選択できるようにするには、「![パネル](/help/assets/icons/Rail.svg)」を選択します。
* タイトルにはプロジェクトが表示され、オプションで選択したフォルダーへのパスが追加されます。[!UICONTROL プロジェクト]／**[!UICONTROL 会社フォルダー]**&#x200B;などです。個々のサブフォルダー部分を選択すると、特定のフォルダーに直接移動することができます。
* [**[!UICONTROL &#x200B; 空のプロジェクト &#x200B;]**](create-projects.md)、[**[!UICONTROL &#x200B; 空のモバイルスコアカード &#x200B;]**](/help/analyze/mobile-app/create-scorecard.md)、**[!UICONTROL ドキュメントを開く]** および **[!UICONTROL リリースノートを開く]** のタイルを表示するには、![&#x200B; 山形ダウン &#x200B;](/help/assets/icons/ChevronDown.svg)**[!UICONTROL さらに表示]** を選択します。 タイルで領域を非表示にするには、![ChevronDown](/help/assets/icons/ChevronDown.svg)、**[!UICONTROL 表示を減らす]**&#x200B;の順に選択します。
* 表示する内容に応じて、[表示セレクター](#show-selector)を使用して、環境設定を編集し、**[!UICONTROL プロジェクト]**&#x200B;に表示されている現在のフォルダーに対するアクションを実行できます。

  | アクション | 説明 |
  |---|---|
  | **[!UICONTROL プロジェクトの作成]** | [新しいプロジェクトを作成](create-projects.md)する場合に選択します。 |
  | **[!UICONTROL フォルダーを作成]** | [新しいフォルダーを作成](workspace-folders/create-folders.md)する場合に選択します。 |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg)、**[!UICONTROL 環境設定を編集]** | すべてのプロジェクトの[環境設定を編集](/help/analyze/analysis-workspace/user-preferences.md)します。パンくずリストのスペースが制限される場合、このアクションは![その他](/help/assets/icons/More.svg)サブメニューの一部になります。 |
  | **[!UICONTROL プロジェクトを追加]** | 現在のフォルダーに[プロジェクトを追加](workspace-folders/add-projects.md)する場合に選択します。パンくずリストのスペースが制限される場合、このアクションは![その他](/help/assets/icons/More.svg)サブメニューの一部になります。 |
  | **[!UICONTROL フォルダーの名前を変更]** | 現在のフォルダーの[名前を変更](workspace-folders/manage-folders.md#rename-folders)します。 |
  | **[!UICONTROL フォルダーを移動]** | 現在のフォルダーを[移動](workspace-folders/manage-folders.md#move-folders)します。 |
  | **[!UICONTROL フォルダーを削除]** | 現在のフォルダーを[削除](workspace-folders/manage-folders.md#delete-folders)します。 |




## プロジェクトリスト


プロジェクトリスト ➋ には、自分が所有しているすべてのプロジェクトと、共有されているプロジェクトが表示されます。リストには、次の列があります。

| 列 | 説明 |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 1 つ以上のプロジェクトを選択すると、プロジェクトインターフェイスの下部に青いアクションバーが表示されます。詳しくは、[アクション](#actions)を参照してください。 |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | プロジェクト「![星](/help/assets/icons/Star.svg)」を優先するか、「![StarOutline](/help/assets/icons/StarOutline.svg)」を優先しないかを選択します。 |
| **[!UICONTROL タイトルと説明]** | プロジェクトを編集するには、タイトルリンクを選択して、[Workspace プロジェクト](/help/analyze/analysis-workspace/home.md)を開きます。共有されているプロジェクトには、![共有](/help/assets/icons/ShareAlt.svg)と表示されます。![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、プロジェクトの詳細を含むポップアップメニューが表示されます。![その他](/help/assets/icons/More.svg) を選択すると、アクションを含むコンテキストメニューが開きます。詳しくは、[アクション](#actions)を参照してください。 |
| **[!UICONTROL タイプ]** | Workspace プロジェクト、![FolderUser](/help/assets/icons/FolderUser.svg) フォルダーまたは[モバイルスコアカード](/help/analyze/mobile-app/home.md)。 |
| **[!UICONTROL タグ]** | プロジェクトに適用されたタグ。 |
| **[!UICONTROL スケジュール済み]** | プロジェクトが受信者にメールで送信されるようにスケジュールされているかどうか。 オプションは、![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL オン]**&#x200B;または ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL オフ]**&#x200B;です。 [他のユーザーへのプロジェクトデータの送信](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md)を参照してください。 |
| **[!UICONTROL 共有リンク（任意のユーザー）]** | Analysis Workspace へのアクセス権を持たない人物を含め、プロジェクトを任意のユーザーと共有するかどうか。オプションは、![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL アクティブ]**&#x200B;または ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 非アクティブ]**&#x200B;です。詳しくは、[プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)の[任意のユーザーとのプロジェクトの共有（ログイン不要）](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)を参照してください。 |
| **[!UICONTROL プロジェクトの役割]** | プロジェクトでの自分の役割。オプションは、編集、複製、表示です。詳しくは、[プロジェクトの役割](/help/analyze/analysis-workspace/curate-share/curate.md)を参照してください。 |
| **[!UICONTROL レポートスイート]** | プロジェクトが関連付けられているレポートスイート。 |
| **[!UICONTROL 所有者]** | このプロジェクトを作成したユーザー（ユーザー自身、またはユーザー自身とそのプロジェクトを共有した他のユーザー）。 |
| **[!UICONTROL 共有先]** | プロジェクトが共有されているユーザー。 |
| **[!UICONTROL 最終変更日時]** | プロジェクトが最後に変更された日付。 |
| **[!UICONTROL 前回開いた日時]** | プロジェクトが最後に開かれた日時。 |
| **[!UICONTROL コンポーネント ID]** | コンポーネントの ID。 |
| **[!UICONTROL 最長の日付範囲]** | プロジェクト内の任意のパネルまたはビジュアライゼーションの最長の日付範囲。 |
| **[!UICONTROL クエリ数]** | プロジェクトに含まれるクエリの合計数。 |
| **[!UICONTROL 場所]** | プロジェクトが存在するフォルダー。 |

任意の列ヘッダーにポインタを合わせて ![ChevronDown](/help/assets/icons/ChevronDown.svg) を表示し、コンテキストメニューから次の項目を選択します。

* **[!UICONTROL 昇順で並べ替え]**
* **[!UICONTROL 降順で並べ替え]**
* **[!UICONTROL 列をサイズ変更]**。列をサイズ変更するのに役立つ青色の線が表示されます。

### アクション

コンテキストメニューの ![その他](/help/assets/icons/More.svg) または青色のアクションバーを使用して、1 つ以上のプロジェクトに対してアクションを実行できます。

| アイコン | アクション | 説明 |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *個を選択済み]** | 選択したプロジェクトとフォルダーを選択解除し、青色のアクションバーを削除します。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 1 つ以上のプロジェクトまたはフォルダーを削除します。確認メッセージが表示されます。 <p>削除するプロジェクト：</p><ul><li>復元することはできない</li><li>プロジェクトリストから削除される</li><li>URL でアクセスできなくなりました</li><li>スケジュールされた配信に含まれなくなりました（以前にスケジュールされた配信用に設定されていた場合）<br/>スケジュールされた配信について詳しくは、[スケジュールされたプロジェクト](/help/components/scheduled-projects-manager.md)を参照してください。  </p> |
| ![共有](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共有]** | プロジェクトを共有します。詳しくは、[プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)を参照してください。 |
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 名前変更]** | プロジェクトの名前を変更します。**[!UICONTROL 名前変更：*プロジェクト名ダイアログ&#x200B;*]**&#x200B;を開きます。新しい名前を入力し、「**[!UICONTROL 保存&#x200B;]**」を選択します。 |
| ![コピー](/help/assets/icons/Copy.svg) | **[!UICONTROL コピー]** | 1 つ以上のプロジェクトをコピーします。プロジェクトには同じ名前とサフィックスの `(Copy)` が付けられます。 |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL ピン留め]**&#x200B;または&#x200B;**[!UICONTROL ピン留め解除]** | 1 つ以上のプロジェクトまたはフォルダーをピン留めまたはピン留め解除します。ピン留めしたプロジェクトとフォルダーはリストの上部に表示され、指定した並べ替え順序は無視されます。 |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL 上へ移動]** | ピン留めしたプロジェクトまたはフォルダーをプロジェクトリスト内で上に移動します。 |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL 下へ移動]** | ピン留めしたプロジェクトまたはフォルダーをプロジェクトリスト内で下に移動します。 |
| ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL タグ]** | 1 つ以上のプロジェクトまたはフォルダーにタグを付けます。1 つ以上のタグを選択するための&#x200B;**[!UICONTROL タグコンポーネント]**&#x200B;ダイアログが表示されます。「**[!UICONTROL 保存]**」を選択して、選択したプロジェクトまたはフォルダーのタグを保存します。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 承認]**&#x200B;または&#x200B;**[!UICONTROL 未承認]** | プロジェクトを承認または未承認にします。管理者のみがプロジェクトを承認できます。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV を書き出し]** | 選択したプロジェクトを `Project List.csv` という名前の CSV ファイルに書き出します。 |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL プロジェクトを追加]** | 選択したフォルダーに 1 つ以上のプロジェクトを追加します。**[!UICONTROL プロジェクトを追加]**&#x200B;で、1 つ以上のプロジェクトを選択できます。「**[!UICONTROL 追加]**」を選択して、プロジェクトをフォルダーに追加します。詳しくは、[フォルダーへのプロジェクトの追加](workspace-folders/add-projects.md#from-inside-a-folder)を参照してください。 |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL 移動先]** | 選択した 1 つ以上のプロジェクトをフォルダーに移動します。**[!UICONTROL フォルダーを選択]**&#x200B;で、選択したプロジェクトを移動するフォルダーを選択し、「**[!UICONTROL 移動]**」を選択します。詳しくは、[フォルダーへのプロジェクトの追加](workspace-folders/add-projects.md#from-the-project-list)を参照してください。 |



## 表示セレクター

**[!UICONTROL 表示]**&#x200B;セレクター➌を使用して、プロジェクトインターフェイスのルックアンドフィールを切り替えることができます。**[!UICONTROL 表示]**&#x200B;セレクターでは、[タイトル領域](#title-area)で使用できるオプションと、[プロジェクトリスト](#project-list)に表示される列を定義します。

* [タイトル領域](#title-area)で使用可能なオプションを変更するには、「**[!UICONTROL すべてのプロジェクトを]**&#x200B;**[!UICONTROL 表示]**」または「**[!UICONTROL フォルダーとプロジェクトを]**&#x200B;**[!UICONTROL 表示]**」を選択します。

* [プロジェクトリスト](#project-list)に表示する列を定義するには、![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を選択し、**[!UICONTROL テーブルをカスタマイズ]**&#x200B;ダイアログから列を選択または選択解除します。 「**[!UICONTROL 適用]**」を選択して、カスタマイズを適用します。列について詳しくは、[プロジェクトリスト](#project-list)を参照してください。

## フィルターパネル

フィルターパネル ➍ を使用して、[プロジェクトリスト](#project-list)のプロジェクトとフォルダーをフィルタリングできます。フィルターパネルを表示または非表示にするには、![フィルター](/help/assets/icons/Filter.svg) を使用します。

フィルターパネルは、次のセクションで構成されています。

### タグ

| タグ | 説明 |
|---|---|
| ![タグ](assets/projects-filters-tags.png){width="300"} | 「**[!UICONTROL タグ]**」セクションでは、タグでフィルタリングできます。 <ul><li>フィルタリングに使用するタグを検索するには、![検索](/help/assets/icons/Search.svg) *タグを検索*&#x200B;を使用します。</li><li>複数のタグを選択できます。使用できるタグは、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>**2︎⃣**：現在のフィルターによって生成されたプロジェクトに使用できるタグ数。</li><li>7︎⃣：特定のタグに関連付けられているプロジェクト数。</li></ul></li></ul> |


### レポートスイート

| レポートスイート | 説明 |
|---|---|
| ![レポートスイート](assets/projects-filters-reportsuites.png){width="300"} | 「**[!UICONTROL レポートスイート]**」セクションでは、レポートスイートをフィルタリングできます。 <ul><li>![&#x200B; 検索 &#x200B;](/help/assets/icons/Search.svg)*レポートスイートを検索* を使用して、フィルタリングに使用するレポートスイートを検索します。</li><li>複数のレポートスイートを選択できます。 使用可能なレポートスイートは、フィルターパネルの他のセクションでの選択内容によって異なります。</li><li>数値は次の内容を示します。<ul><li>**3︎⃣**：現在のフィルターによって生成されたプロジェクトで使用できるレポートスイートの数。</li><li>4︎⃣：特定のレポートスイートに関連付けられているプロジェクトの数。</li></ul></li></ul> |


### 所有者

| 所有者 | 説明 |
|---|---|
| ![所有者](assets/projects-filters-owners.png){width="300"} | 「**[!UICONTROL 所有者]**」セクションでは、所有者でフィルタリングできます。 <ul><li>フィルタリングに使用する所有者を検索するには、![検索](/help/assets/icons/Search.svg) *所有者を検索*&#x200B;を使用します。</li><li>複数の所有者を選択できます。使用できる所有者は、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>**3︎⃣**：現在のフィルターによって生成されたプロジェクトに使用できる所有者数。</li><li>4︎⃣：特定の所有者に関連付けられているプロジェクト数。</li></ul></li></ul> |


### タイプ

| タイプ | 説明 |
|---|---|
| ![タイプ](assets/projects-filters-type.png){width="300"} | 「**[!UICONTROL タイプ]**」セクションでは、プロジェクトやフォルダーのタイプでフィルタリングできます。<ul><li>次のオプションから 1 つ以上を選択できます。<ul><li> **[!UICONTROL フォルダー]**</li><li>**[!UICONTROL ワークスペースプロジェクト]**</li><li>**[!UICONTROL モバイルスコアカード]**</li></ul> <li>複数のフィルターを選択できます。使用できるその他のフィルターは、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>**5︎⃣**：現在のフィルターによって生成されたプロジェクトに使用できるその他のフィルター数。</li><li>4︎⃣：特定のその他のフィルターに関連付けられているプロジェクト数。</li></ul></li></ul> |


### その他のフィルター

| その他のフィルター | 説明 |
|---|---|
| ![その他のフィルター](assets/projects-filters-others.png){width="300"} | 「**[!UICONTROL その他のフィルター]**」セクションでは、他の定義済みフィルターでフィルタリングできます。<ul><li>次のオプションから 1 つ以上を選択できます。<ul><li> **[!UICONTROL すべてを表示]**</li><li>**[!UICONTROL 自分と共有済み]**</li><li>**[!UICONTROL 自分が所有]**</li><li>**[!UICONTROL 承認済み]**</li><li>**[!UICONTROL お気に入り]**</li></ul> 選択できる内容は、役割と権限によって異なります。</li><li>複数のフィルターを選択できます。使用できるその他のフィルターは、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>**5︎⃣**：現在のフィルターによって生成されたプロジェクトに使用できるその他のフィルター数。</li><li>4︎⃣：特定のその他のフィルターに関連付けられているプロジェクト数。</li></ul></li></ul> |

## 検索

「![検索](/help/assets/icons/Search.svg)」フィールドを使用してプロジェクトとフォルダーを検索するには、検索領域 ➎ を使用します。入力を開始すると、[プロジェクトリスト](#project-list)が検索入力に基づいて自動的にフィルタリングされます。

また、検索領域には、フィルターパネルから適用されたフィルターも表示されます。

* フィルターを削除するには、フィルターで ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択します。
* すべてのフィルターを削除するには、「すべてクリア」を選択します。

個々のフィルターを表示するスペースが制限されている場合は、「**[!UICONTROL *x* 個のフィルターでセグメント化]**」と表示されます。

* フィルターを削除するには：

   1. **[!UICONTROL *x *個のフィルター]**![ChevronDown](/help/assets/icons/ChevronDown.svg) を使用して、フィルターのタイプと個々のフィルターを一覧表示するコンテキストメニューを開きます。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用して、タグを削除します。

