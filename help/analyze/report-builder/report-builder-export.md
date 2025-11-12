---
title: Report Builderからのレポートの書き出し
description: Report Builderから安全な宛先にデータを書き出す方法を説明します
role: User, Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 5829482b-3a5e-416b-9c82-404face30b29
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 30%

---

# クラウドの宛先に書き出してワークブックをスケジュールする

Report BuilderからGoogle、Azure、AmazonなどのクラウドプロバイダーにAdobe Analytics ワークブックを書き出すことができます。

または、[&#x200B; メールで共有するワークブックのスケジュール &#x200B;](/help/analyze/report-builder/schedule-reportbuilder.md) で説明しているように、メールを使用してワークブックを他のユーザーと共有できます。

[Report Builder からクラウドにレポートを書き出す利点 &#x200B;](#advantages-of-exporting-to-the-cloud) には、サードパーティのツールでレポートを使用する機能や、外部データと組み合わせる機能などがあります。

Report Builderからクラウド上の宛先にワークブックを書き出す前に、データブロック、環境および権限が [&#x200B; 書き出し要件 &#x200B;](#export-requirements) を満たしていることを確認してください。

## 書き出しプロセスについて

Report Builderからクラウドにワークブックを書き出す場合は、次の手順を使用します。

1. [クラウドアカウントを設定](/help/components/locations/configure-import-accounts.md)

1. [アカウントの場所を設定](/help/components/locations/configure-import-locations.md)

1. [Report Builderからのレポートのエクスポート](#export-a-report-from-report-builder)

## Report Builderからのレポートのエクスポート

>[!NOTE]
>
>この節の説明に従ってデータを書き出す前に、上記の節で [&#x200B; 書き出しプロセス &#x200B;](#understand-the-export-process) について詳しく説明します。

Report Builderからレポートを書き出すには：

1. まだ行っていない場合は、[クラウドの書き出しアカウントの設定](/help/components/locations/configure-import-accounts.md)の説明に従って、書き出しのアカウントと場所を設定します。

1. 書き出すデータを含む Excel スプレッドシートで、右側の **[!UICONTROL 0&rbrace;Adobe Report Builder&rbrace; パネルを開きます。]**

1. [!UICONTROL **スケジュール**] を選択します。

<!-- add screenshot -->

1. 「**[!UICONTROL ワークブック]**」タブで、プラスアイコンを選択して新しいスケジュールを作成します

   ![&#x200B; 「Report Builder スケジュール」タブ &#x200B;](assets/report-builder-schedule-cloud.png)

   または

   作成済みのスケジュールでワークブックを書き出すには、スケジュールのリストからスケジュールを選択し、「**[!UICONTROL スケジュールに従って送信]**」を選択します。

1. 新しいスケジュールの作成を続行するには、[!UICONTROL **Adobe Report Builder**] 右側のパネルで次の情報を指定します。

   | フィールド名 | 関数 |
   |---------|----------|
   | **[!UICONTROL ファイル]** | 書き出し用に現在選択されているワークブックファイルを表示します。 現在のワークブックがまだ選択されていない場合は、ファイル名の横にあるワークブックアイコン ![TableSelect](/help/assets/icons/TableSelect.svg) を選択して、そのワークブックを選択します。 |
   | **[!UICONTROL ファイル名]** <!--should be File name --> | ワークブックを書き出す前にファイル名を変更できます。<p>ワークブックのファイル名のデフォルト値はワークブックの名前です</p> |
   | **[!UICONTROL ファイルタイプ]** | 書き出すファイルのファイルタイプを選択します。 Excel、PDFまたは CSV を選択できます。<p>**[!UICONTROL CSV]** を選択する場合、スケジュールされたワークブックは ZIP 添付ファイルとして送信されることに注意してください。 一部の企業のメール管理では、ZIP 添付ファイルを含んだメールがブロックされる場合があります。 それに応じて警告が表示されます。</p> |
   | **[!UICONTROL ファイル名にタイムスタンプを追加する]** | このオプションを選択して、書き出されたファイル名に書き出しのタイムスタンプを含めます。 |
   | **[!UICONTROL ファイル名のプレビュー]** <!--should be File name preview --> | 書き出し後のファイル名の表示方法のプレビューを表示します。 |
   | **[!UICONTROL ワークブックをパスワードで保護]** | 書き出されたファイルを保護するパスワードを指定して、パスワードを持つユーザーのみがファイルにアクセスできるようにします。 <p>パスワードは 8 文字以上とし、数字と特殊文字（`!`、`@`、`#`、`$` など）を 1 文字以上含める必要があります。</p> |
   | **[!UICONTROL 電子メール]** | このオプションを選択すると、特定のメールアドレスにファイルが送信されます。 このオプションの詳細については、「[&#x200B; メールで共有してワークブックをスケジュールする &#x200B;](/help/analyze/report-builder/schedule-reportbuilder.md)」を参照してください。 |
   | **[!UICONTROL その他の配信]** | このオプションを選択してファイルをクラウドアカウントに送信し、以下に説明する **[!UICONTROL アカウント]** および **[!UICONTROL 場所]** ドロップダウンメニューを使用して、アカウントと場所を選択します。 |
   | **[!UICONTROL アカウント]** | データを送信するクラウド書き出しアカウントを選択します。 <p>または、使用するクラウドアカウントをまだ設定していない場合は、新しいアカウントを設定できます。<ol><li>「[!UICONTROL **アカウントを追加**]」を選択し、次の情報を指定します。<ul><li>[!UICONTROL **場所アカウント名**]：場所アカウントの名前を指定します。この名前は、場所を作成する際に表示されます。 </li><li>[!UICONTROL **場所アカウントの説明**]：同じアカウントタイプの他のアカウントと区別できるように、アカウントの簡単な説明を入力します。</li><li>**[!UICONTROL 組織内のすべてのユーザーがアカウントを使用できるようにする]**：組織内の他のユーザーがアカウントを使用できるようにするには、このオプションを選択します。 アカウントを共有する際は、次の点に注意してください。<ul><li>共有しているアカウントの共有を解除することはできません。</li><li>共有アカウントは、そのアカウントの所有者のみが編集できます。</li><li>共有アカウントの場所は誰でも作成できます。</li></ul></li><li>[!UICONTROL **アカウントタイプ**]：書き出し先のクラウドアカウントのタイプを選択します。 使用可能なアカウントタイプは、Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC です。</li></ul><li>アカウントの設定を完了するには、[&#x200B; クラウドのアカウントのインポートとエクスポートの設定 &#x200B;](/help/components/locations/configure-import-accounts.md) の手順 6 に進み、選択した [!UICONTROL **アカウントタイプ**] に対応するセクションを展開します。 <p>次のアカウントタイプを使用できます。</p><ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul></ol> |
   | **[!UICONTROL 場所]** | 書き出しデータを送信するアカウント上の場所を選択します。<p>または、選択したアカウントで使用する場所をまだ設定していない場合は、新しい場所を設定できます。<ol><li>「[!UICONTROL **場所を追加**]」を選択し、次の情報を指定します。 <ul><li>[!UICONTROL **名前**]：場所の名前。</li><li>[!UICONTROL **説明**]：アカウント上の他の場所と区別できるように、場所の簡単な説明を入力します。</li><li>**[!UICONTROL 組織内のすべてのユーザーが場所を使用できるようにする]**：組織内の他のユーザーが場所を使用できるようにするには、このオプションを選択します。 アカウントを共有する際は、次の点に注意してください。<ul><li>共有する場所の共有を解除することはできません。</li><li>共有場所は、アカウントの所有者のみが編集できます。</li><li>場所を共有できるのは、その場所が関連付けられているアカウントも共有されている場合のみです。</li></ul></li><li>[!UICONTROL **場所アカウント**]：場所を作成するアカウントを選択します。</li></ul><li>場所の設定を完了するには、「[!UICONTROL **場所アカウント**]」フィールドで選択したアカウントタイプに対応する以下のリンクに進みます。<ul><li>[Amazon S3 Role ARN](/help/components/locations/configure-import-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/locations/configure-import-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/locations/configure-import-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/locations/configure-import-locations.md#azure-rbac)</li></ul> |
   | **[!UICONTROL スケジュールオプションを表示]** | 書き出しをスケジュールするための追加オプションを表示するには、このオプションを選択します。 書き出しを 1 回だけ送信する場合は、このオプションを選択しないままにします。 このオプションを選択しない場合、書き出しは直ちに開始されます。 |
   | **[!UICONTROL 開始日]** | スケジュールされた書き出しを開始する日時。 <p>このオプションは、スケジュールされた書き出し頻度を選択する場合にのみ使用できます。</p> |
   | **[!UICONTROL 終了日]** | スケジュールされた書き出しが期限切れになる日時。スケジュールされた書き出しは、設定した日時以降は実行されなくなります。 <p>このオプションは、スケジュールされた書き出し頻度を選択する場合にのみ使用できます。</p> |
   | **[!UICONTROL 頻度]** | 頻度は、1 時間ごと、毎日、毎週、毎月または毎年特定の日に設定できます。例えば、月の第一日曜日の夜にワークブックを送信するスケジュールを設定して、月曜日の朝一番に受信者のインボックスにメールを届けるようにすることができます。 |

   {style="table-layout:auto"}

1. 「[!UICONTROL **スケジュールに従って送信**]」を選択して、ワークブックを書き出します。

   データは、指定した頻度で指定したクラウドアカウントに送信されます。

   Report Builder ハブの下部に確認トーストが表示され、スケジュールされたワークブックが「ワークブック」タブにリストされます。

## クラウドへの書き出しのメリット

Adobe Analytics データを Cloud に書き出すと、次の操作を実行できます。

* Google Cloud Platform、Microsoft Azure、Amazon S3 などの共有の場所に書き出します。

* 大量の履歴データを保存する。

  このタイプのデータを使用すると、ビジネスインテリジェンスを獲得するために長期的なトレンドを検出し、最終的により良いビジネス上の意思決定につながります。

* 書き出されたAdobe Analytics データに計算指標を含めます。

* 連結された値としてデータ出力を構造化する。

* 1 回限りのエクスポート、またはスケジュールに従ったエクスポート。

* ファイルを Excel、PDFまたは CSV 形式で書き出します。

* 複数のディメンションを含むデータブロックを書き出します。

## 書き出し要件 {#export-requirements}

### 最小要件

データブロック、環境および権限が次の要件を満たしていることを確認します。

* **データブロック：** すべてのデータブロックには、列、行、または値に対して少なくとも 1 つのコンポーネントを含める必要があります。

* **環境：** Adobe Analyticsで使用される [IP アドレス &#x200B;](/help/technotes/ip-addresses.md) および [&#x200B; ドメイン &#x200B;](/help/technotes/domains.md) が、組織のファイアウォールを通過できることを確認します。


<!--
## Manage exports

After data is exported from Analysis Workspace, you can edit, re-export, duplicate, tag, or delete existing exports, as described in [Manage exports](/help/components/exports/manage-exports.md). 

-->

## スケジュールされたワークブックの管理

既にスケジュールされたワークブックの管理について詳しくは、「[&#x200B; スケジュールされたワークブックの管理 &#x200B;](/help/analyze/report-builder/manage-schedules-reportbuilder.md)」を参照してください。
