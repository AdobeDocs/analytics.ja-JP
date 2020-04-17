---
description: セグメントをオーディエンスライブラリ、Target および Audience Manager のマーケティングアクティビティで使用できます。
title: Experience Cloud へのセグメントの公開
topic: Segments
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: 3b7e79cf26c8dccd9c8090df48a556419995ebd7

---


# Experience Cloud へのセグメントの公開

Adobe AnalyticsセグメントをExperience Cloudに公開すると、そのセグメントを、およびアドビのなどの他のアクティベーション [!DNL Audience Manager] チャネルでマーケティングアクティビティに使 [!DNL Advertising Cloud]用でき [!DNL Target] ます [!DNL Campaign]。 最近の更新で、公開ワークフローが大幅に最適化されました。Analyticsセグメントを8時間以内にExperience Cloudに公開できるようになりました。 これらのセグメントを使用して、すべてのダウンストリームオーディエンスに対してオーディエンスマネージャーの宛先をアクティブにします。

また、公開可能なAdobe Analyticsセグメントの最大数を20から75に増やしました。 で公開したセグメントを表示できま [!UICONTROL Analytics > Components > Segments]す。

>[!NOTE] Adobe Campaign（Classic と Standard）の動作は、8 時間の遅延に加えて 24 時間の遅延が発生する点が異なります。


## 前提条件

* このセグメントの保存先となるレポートスイートが [Experience Cloud に対して有効](https://docs.adobe.com/content/help/ja-JP/core-services/interface/audiences/t-publish-audience-segment.html)になっていることを確認します。そうしないと、Experience Cloud に公開できません。
* [Experience Cloud 組織にマッピングされた](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/report-suite-mapping.html)レポートスイートで作業していることを確認します。
* 組織が Experience Cloud ID を使用していることを確認します。
* Before you can publish segments, your Admin needs to assign the [!UICONTROL Segment Publishing] permission to a product profile in the [Admin Console](https://docs.adobe.com/content/help/ja-JP/core-services/interface/manage-users-and-products/admin-getting-started.html), and add you to the product profile.


## 注意点

* **レポートスイートの制限**：レポートスイートごとに最大 75 個のセグメントを公開できます。この制限は適用されます。既に 75 個のセグメントが公開されている場合、公開を取り消してセグメント数が 75 個のセグメントしきい値を下回るまで、追加のセグメントを公開することはできません。
* **メンバーシップの制限**:Adobe Analyticsからに共有さ [!DNL Experience Cloud] れるオーディエンスは、2,000万人を超える一意のメンバーは使用できません。
* **データプライバシー**：オーディエンスは、訪問者の認証状態に基づいてフィルタリングされません。訪問者が未認証状態および認証状態でサイトを閲覧できる場合、訪問者が未認証のときに生じるアクションによって、訪問者がオーディエンスに含められる可能性があります。オーディエンス共有がプライバシーに与える影響をすべて理解するには、[Adobe Experience Cloud](https://www.adobe.com/jp/privacy/experience-cloud.html) のプライバシーを確認します。
* **[!DNL Adobe Analytics] と [!DNL Audience Manager]** のセグメント間の違いについては、[こちら](https://docs.adobe.com/content/help/ja-JP/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)を参照してください。

## セグメント公開タイムライン

| 利用可能な情報 | 利用可能な場合 | 利用可能な場所 |
|---|---|---|
| メタデータ（セグメントのタイトルと定義） | 公開直後 | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| メンバーシップを持つ使用可能なセグメント | 公開後 8 時間以内 | [!DNL Audience Manager] の訪問者プロファイルビューア |
| 特性とメンバーシップの母集団 | 24 ～ 48 時間以内 | [!DNL Audience Manager] |

>[!NOTE]
>週に1度、すべてのデータは完全に同期され、前の週に収集された差分や不一致が考慮されます。

## セグメントの公開先 [!UICONTROL Segment Builder]

1. > **[!UICONTROL Analytics > Workspace > Components > Segments]+に移動&#x200B;**
1. でセグメントを作成しま [!UICONTROL Segment Builder]す。
1. セグメントのタイトルと説明を指定します。指定しない場合は、セグメントを保存できません。
1. レポー **[!UICONTROL Publish this segment to the Experience Cloud (for *トスイート&#x200B;*)]**。

![](assets/publish-ec.png)

>[!IMPORTANT]
>Adobe Analytics の数値と Audience Manager の数値を比較する際には、Analytics でセグメントプレビューを確認する際に、「個別訪問者数」の合計ではなく、「Experience Cloud ID を持つ訪問者」を使用してください。
>
>![](assets/seg-vis-ecid.png)

| 要素 | 説明 |
|---|---|
| **[!UICONTROL Publish this segment to the Experience Cloud (for *<report suite>*）]** | このオプションを有効にすると、セグメントのタイトルと定義（例：広告プラットフォームで頻繁に使用されるシェルオーディエンス）が瞬時に Experience Cloud で共有され、セグメントのメンバーシップが 4 時間ごとに評価および共有されます。<br>そのオーディエンスが [!DNL Target] のアクティビティと関連付けられている場合、[!DNL Analytics] は、その Experience Cloud および [!DNL Target] オーディエンスの対象となる訪問者の ID の送信を開始します。その時点で、オーディエンス名と対応するデータが Experience Cloud オーディエンスページに表示され始めます。</br> |
| **[!UICONTROL Audience Creation Window]** | 選択した時間枠を使用して、周期的なカレンダーベースでオーディエンスが作成されます。例えば、「過去 30 日間」（デフォルト）には、今日の日付（セグメントが作成された元の日付からではない）から過去 30 日間にオーディエンス資格を持っていた訪問者が含まれます。 |
| **[!UICONTROL Create in Audience Library]** | 作成および公開したセグメントは、Experience Cloud オーディエンスライブラリで待ち時間なく使用できます。Analytics の更新には依存しません。これらのセグメントは、公開済みの 75 個のセグメントの制限に対してはカウントされません。 |
| **[!UICONTROL x of 75 Published]** | Experience Cloud に公開したセグメントの数を表示します。リンクをクリックすると、公開済みのセグメントと、関連するレポートスイートおよび所有者のリストが表示されます。 |
| **[!UICONTROL Save]** | このセグメントを保存します。 |

## セグメントの非公開または削除

Experience Cloud に公開されているセグメントを削除するには、まず非公開にする必要があります。セグメントを非公開にするには、公開するために使用したチェックボックスの&#x200B;**チェックを解除**&#x200B;します。

>[!NOTE]次のいずれかのアドビソリューションで現在使用中のセグメントの公開を取り消すことは&#x200B;**できません**：[!DNL Analytics]（[!DNL Audience Analytics]の場合）、[!DNL Campaign]、[!DNL Advertising Cloud]（[!DNL Core Service]および[!DNL Audience Manager] の顧客の場合）、およびその他すべての外部パートナー（[!DNL Audience Manager] の顧客の場合）。[!DNL Target] で使用中のセグメントを非公開にすることが&#x200B;**できます**。

## View segment publishing status in the [!UICONTROL Segment Manager]

1. に移動しま [!UICONTROL Analytics > Components > Segments]す。
1. Notice the new [!UICONTROL Published] column. はい／いいえは、セグメントが Experience Cloud に公開されたかどうかを示します。

![](assets/publish-status.png)

## [!DNL Audience Manager] UUID の取得

ブラウザーに現在関連付けられている AAM UUID を取得するには、次の 2 つの方法があります。

* Adobe Experience Cloud デバッガー
* ブラウザーのネイティブ開発者ツール（Chrome Developer Tools など）

次のスクリーンショットは、ブラウザーで AAM UUID を取得し、Audience Manager 訪問者プロファイルビューアで AAM UUID を使用して特性とセグメントのメンバーシップを検証する方法を示しています。

**方法 1：Adobe Experience Cloud デバッガーの使用**

1. Chrome Web Store で [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/testing-and-validation/debugger.html) をダウンロードしてインストールします。
1. ページの読み込み時にデバッガーを起動します。
1. 「Audience Manager」セクションまでスクロールし、現在のブラウザーページで設定されている AAM UUID を見つけます（以下の例の `50814298273775797762943354787774730612` を参照）。

![](assets/debugger.jpg)

**方法 2：Chrome Developer Tools（または他のブラウザー開発者ツール）を使用する**

1. ページを読み込む前に Chrome Developer Tools を起動します。
1. ページを読み込み、アプリケーション／Cookie を確認します。AAM UUID は、サードパーティ Demdex cookie（下の例では [adobe.demdex.net](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/reference/demdex-calls.translate.html) に設定する必要があります）。demdex フィールドは、ブラウザー上の AAM UUID 設定です（以下の例は `50814298273775797762943354787774730612`）。

![Chrome Developer Tools](assets/ggogle-uuid.png)

## オーディエンスマネージャ [!UICONTROL Visitor Profile Viewer]

The AAM UUID on the browser will be used by default when [!UICONTROL Visitor Profile Viewer] is loaded. If verifying trait realizations for other users, input a UUID in the UUID field and click [!UICONTROL Refresh]. 詳しくは、[訪問者プロファイルビューア](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html)を参照してください。

![](assets/aam-vpv.png)

## [!DNL Audience Manager] でセグメント特性を表示する

AAMでは、Analytics が Experience Cloud とセグメントを共有するので、特定のセグメントの ECID を持つ訪問者のリストがストリーミング方式で評価されます。

1. で、 [!DNL Audience Manager]に進みます [!UICONTROL Audience Data > Traits > Analytics Traits]。 Experience Cloud 組織にマップされている各 Analytics レポートスイートのフォルダーが表示されます。これらのフォルダー（特性、セグメントおよびデータソースの場合）は、プロファイルおよび Audiences／People コアサービスが開始またはプロビジョニングされると作成されます。
1. [!DNL Audience Manager] と共有する、過去にセグメントを作成したレポートスイートのフォルダーを選択します。作成したセグメント／オーディエンスが表示されます。セグメントを共有すると、[!DNL Audience Manager] で次の 2 つがおこなわれます。
* データが入っていない特性が作成されます。セグメントが[!DNL Analytics] で公開されてから約 8 時間後に、ECID のリストがオンボードされ、[!DNL Audience Manager] および他の Experience Cloud ソリューションと共有されるようになります。

![](assets/aam-traits.png)

* 1 つの特性セグメントが作成されます。セグメントを公開したレポートスイートに関連付けられているデータソースを使用します。
* 特性の有効期限が16日に設定されました（以前は2日でした）。

## セグメントを [!DNL Adobe Target] で表示する

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target&#39;s custom audience library. Analytics または Audience Manager で作成されたセグメントは、Target のアクティビティで使用できます。例えば、Analytics コンバージョン指標および Analytics で作成されたオーディエンスセグメントに基づいてキャンペーンアクティビティを作成できます。], click [!UICONTROL Audiences].
1. [!UICONTROL Audiences] ページで、[!DNL Experience Cloud] からのオーディエンスを探します。これらのオーディエンスは、[!DNL Target] アクティビティで使用できます。

