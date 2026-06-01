---
description: Audience Library、Target、Audience Managerでマーケティングアクティビティ用のセグメントを公開する方法について説明します。
title: セグメントを公開
feature: Segmentation
exl-id: 0215f896-d3f8-42cc-ac8d-8a94b009927b
TQID: https://experienceleague.adobe.com/JP5OI6SzaJ1xQpFY8iIgT-DNTVxofdSu93XmWI1vtsU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d2fb5ded5ce49c6e7143897de2ee9d3b6b494bf9
workflow-type: tm+mt
source-wordcount: 1432
ht-degree: 31%

---

# セグメントの公開 {#publish-segments}

>[!CONTEXTUALHELP]
>id="components_segments_publishing"
>title="CX Enterprise の公開"
>abstract="オーディエンスをオーディエンスライブラリに公開し、Target やその他の CX Enterprise ソリューションのマーケティングアクティビティに使用できます。"

>[!CONTEXTUALHELP]
>id="components_segments_audiencelibrary"
>title="オーディエンスライブラリ"
>abstract="オーディエンスライブラリで作成されたセグメントは即座に利用でき、Analytics の更新には依存しません。"


Adobe AnalyticsセグメントをCX Enterpriseに公開できます。 そのため、Audience Managerや、Advertising、Target、Campaignなどの他のアクティベーションチャネルで、マーケティングアクティビティにセグメントを使用できます。

Adobe Analyticsのセグメントは、8時間以内にCX Enterpriseに公開できます。 これらのセグメントを使用して、Audience Manager 内のオーディエンスを、すべてのダウンストリームの宛先でアクティブ化します。


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [&#x200B; セグメントを公開](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/integrations/experience-cloud/improved-experience-cloud-audience-publishing){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


>[!NOTE]
>
>Adobe Campaign（Classic と Standard）の動作は、8 時間の遅延に加えて 24 時間の遅延が発生する点が異なります。

## 前提条件

* このセグメントを保存するレポートスイートが、CX Enterprise[&#128279;](/help/components/segmentation/segmentation-workflow/seg-publish.md)に対して有効になっていることを確認してください。 それ以外の場合は、CX Enterpriseに公開できません。
* 組織が Experience Cloud ID を使用していることを確認します。
* セグメントを公開する前に、管理者は [Admin Console](https://experienceleague.adobe.com/ja/docs/core-services/interface/administration/admin-tool-experience-cloud) で製品プロファイルに[!UICONTROL セグメントの公開]権限を割り当て、製品プロファイルにユーザーを追加する必要があります。

## 注意点

* **レポートスイートの制限**：レポートスイートごとに最大 75 個のセグメントを公開できます。 この制限は適用されます。 既に 75 個のセグメントが公開されている場合、公開を取り消してセグメント数が 75 個のセグメントしきい値を下回るまで、追加のセグメントを公開することはできません。
* **メンバーシップ制限**: Adobe AnalyticsからCX Enterpriseに共有されるオーディエンスは、2,000万人を超えることはできません。
* **データプライバシー**：オーディエンスは、訪問者の認証状態に基づいてフィルタリングされません。 訪問者は、未認証の状態や認証された状態でサイトを閲覧できる可能性があります。 訪問者が未認証の場合に発生するアクションは、引き続き訪問者をオーディエンスに含めることができます。 [Adobe CX Enterprise privacy](https://www.adobe.com/jp/privacy/experience-cloud.html)を確認して、オーディエンス共有のプライバシーへの影響を完全に理解します。
* [!DNL Adobe Analytics]とAudience Manager **のセグメント間の**&#x200B;相違点については、[AnalyticsとAudience Managerのセグメントの理解](/help/integrate/c-audience-analytics/aam-analytics-segments.md)を参照してください。

## セグメント公開タイムライン

| 利用可能な情報 | 利用可能な場合 | 利用可能な場所 |
|---|---|---|
| メタデータ（セグメントのタイトルと定義） | 公開直後 | Audience Manager、CX Enterprise Audience Library、Target |
| メンバーシップを持つ使用可能なセグメント | 公開後 8 時間以内 | Audience Managerの訪問者プロファイルビューア |
| 特性とメンバーシップの母集団 | 24 ～ 48 時間以内 | Audience Manager |

>[!NOTE]
>週に1回、すべてのデータが完全に同期され、前週に取得されなかった差分や不一致を考慮します。

## [!UICONTROL &#x200B; セグメントビルダー]でのセグメントの公開

1. Adobe Analyticsで、**[!UICONTROL コンポーネント]** > **[!UICONTROL セグメント]**&#x200B;に移動します
1. 「**[!UICONTROL 追加]**」を選択して、新しいセグメントを作成します。
   ![CX Enterpriseを公開](assets/publish-ec.png)
1. セグメントのタイトルと説明を入力します。 セグメントを保存する前に、これらのフィールドが必須です。
1. 「**[!UICONTROL Experience Cloud公開]**」セクションで、「**[!UICONTROL このセグメントをExperience Cloudに公開する」（*レポートスイート*の場合）]** オプションを選択します。

   >[!IMPORTANT]
   >
   >Adobe Analyticsの数値とAudience Managerの数値を比較する場合は、**[!UICONTROL 一意の訪問者]**&#x200B;ではなく、**[!UICONTROL データプレビュー]**&#x200B;で&#x200B;**[!UICONTROL Experience Cloud IDを持つ訪問者を必ず監視してください。]**
   >

| 要素 | 説明 |
|---|---|
| **[!UICONTROL このセグメントをExperience Cloudに公開します（*レポートスイート*の場合）]** | このオプションを有効にすると、セグメントのタイトルと定義がCX Enterpriseと瞬時に共有され、セグメントのメンバーシップが4時間ごとに評価され、共有されます。<br> 例えば、[!DNL Analytics]は、そのオーディエンスがTargetのアクティビティに関連付けられている場合、そのCX EnterpriseおよびTarget オーディエンスに適格な訪問者のIDの送信を開始します。 この時点で、CX Enterpriseの[!DNL Audience Library] ページにオーディエンス名と対応するデータが表示され始めます。</br> |
| **[!UICONTROL オーディエンス作成期間]** | 選択した時間枠は、ローリングカレンダー単位でオーディエンスを作成するために使用されます。 例えば、**[!UICONTROL 過去30日間]** （デフォルト）には、今日の日付から過去30日間にオーディエンスに選定された訪問者が含まれます（セグメントが作成された当初の日付からではありません）。 |
| **[!UICONTROL オーディエンスライブラリに作成]** | 作成して公開するセグメントは、CX Enterpriseの[!DNL Audience Library] ページで遅延なく利用できます。 Analytics の更新には依存しません。 これらのセグメントは、公開済みの 75 個のセグメントの制限に対してはカウントされません。 |
| **[!UICONTROL x / 75 個公開済み]** | CX Enterpriseに公開したセグメントの数。 リンクをクリックすると、公開済みのセグメントと、関連するレポートスイートおよび所有者のリストが表示されます。 |
| **[!UICONTROL 保存]** | このセグメントを保存します。 |

## セグメントの非公開または削除

>[!CAUTION]
>
>CX Enterpriseに公開されているセグメントを削除するには、最初にセグメントを非公開にする必要があります。 セグメントを非公開にするには、「**[!UICONTROL このセグメントをExperience Cloudに公開する」（*レポートスイート*の場合）]**&#x200B;を選択解除するだけです。


>[!NOTE]
>
>Analytics （Audience Analytics内）、Campaign、Advertising（Core ServiceおよびAudience Managerのお客様向け）、およびその他のすべての外部パートナー（Audience Managerのお客様向け）のいずれのAdobe ソリューションで現在使用されているセグメントを&#x200B;**非公開にすることはできません**。 Targetで使用されているセグメントを&#x200B;**で**&#x200B;非公開にできます。

## セグメントの公開ステータスの表示

公開可能なAdobe Analytics セグメントの最大数は75です。

公開したセグメントを表示するには：

1. Adobe Analyticsで、**[!UICONTROL コンポーネント]** > **[!UICONTROL セグメント]**&#x200B;に移動します。

1. **[!UICONTROL 公開済み]**&#x200B;列を表示します。 この列の&#x200B;**[!UICONTROL Yes]**&#x200B;は、セグメントがCX Enterpriseに公開されていることを示します。 **[!UICONTROL No]**&#x200B;は、セグメントが公開されていないことを示します。

## Audience Manager UUIDの取得

現在ブラウザーに関連付けられているAdobe Audience Manager UUIDをキャプチャするには、次の2つの方法があります。

* Adobe CX Enterprise Debugger
* ブラウザーのネイティブ開発ツール（例：Chrome開発ツール）

次のスクリーンショットは、ブラウザーでAdobe Audience Manager UUIDを取得し、Audience Manager Visitor Profile Viewerで使用して特性とセグメントメンバーシップを検証する方法を示しています。

### 方法1:Adobe CX Enterprise Debuggerを使用する

1. [Adobe CX Enterprise Debugger](/help/implement/validate/debugger.md)をChrome Web ストアにダウンロードしてインストールします。
1. ページの読み込み時にデバッガーを起動します。
1. Audience Manager セクションまでスクロールし、現在のブラウザーページで設定されているAdobe Audience Manager UUIDを見つけます
（以下の例の`35721780439475290181087231320657663953`）

   ![デバッガー](assets/aepdebugger.png)

### 方法 2：Chrome Developer Tools（または他のブラウザー開発者ツール）を使用する

1. ページを読み込む前に Chrome Developer Tools を起動します。
1. ページを読み込み、アプリケーション／Cookie を確認します。 Adobe Audience ManagerのUUIDは、サードパーティの
Demdex cookie （[adobe.demdex.net](https://experienceleague.adobe.com/ja/docs/audience-manager/user-guide/reference/demdex-calls)以下の例）。 フィールドのdemdexはAdobe Audience Manager UUID セットです
ブラウザー（`35721780439475290181087231320657663953`以下の例）。

   ![Chrome Developer Tools](assets/devtools.png)

## Audience Manager [!UICONTROL 訪問者プロファイルビューアを使用する]

[!UICONTROL 訪問者プロファイルビューア &#x200B;]が読み込まれると、ブラウザーのAdobe Audience Manager UUIDはデフォルトで使用されます。 他のユーザーの特性の実現を検証する場合は、UUID フィールドにUUIDを入力し、[!UICONTROL 更新]をクリックします。 詳しくは、 [訪問者プロファイルビューア](https://experienceleague.adobe.com/ja/docs/audience-manager/user-guide/features/visitor-profile-viewer) を参照してください。

## Adobe Audience Managerのセグメント特性を見る

Adobe Audience Managerでは、AnalyticsがCX Enterpriseとセグメントを共有する間に、特定のセグメントのECIDを持つ訪問者のリストが評価されます。

1. Audience Managerで、**[!UICONTROL Audience Data]** > **[!UICONTROL 特性]** > **[!UICONTROL Analytics特性]**&#x200B;に移動します。 CX Enterprise組織にマッピングされた各Analytics レポートスイートのフォルダーが表示されます。 これらのフォルダー（特性、セグメントおよびデータソースの場合）は、プロファイルおよびオーディエンス／人物コアサービスが開始またはプロビジョニングされると作成されます。
1. Audience Managerと共有するセグメントを以前に作成したレポートスイートのフォルダーを選択します。 作成したセグメント/オーディエンスが表示されます。 セグメントを共有すると、Audience Managerで2つのことが起こります。
   * データが入っていない特性が作成されます。 セグメントが セグメントが[!DNL Analytics]で公開されてから8時間後、ECIDのリストがオンボーディングされ、Audience Managerおよびその他のCX Enterprise ソリューションと共有されます。

     ![Audience Manager の特性](assets/aam-traits.png)

   * 1 つの特性セグメントが作成されます。 セグメントを公開したレポートスイートに関連付けられているデータソースを使用します。
   * 特性の有効期限が 16 日に設定されました（以前は 2 日でした）。

## セグメントを [!DNL Adobe Target] で表示する

**[!UICONTROL このセグメントをExperience Cloud]**&#x200B;に公開すると、セグメントをAdobe Targetのカスタムオーディエンスライブラリ内で利用できるようになります。 Analytics または Audience Manager で作成されたセグメントは、Target のアクティビティで使用できます。 例えば、Analytics コンバージョン指標および Analytics で作成されたオーディエンスセグメントに基づいてキャンペーンアクティビティを作成できます。

Adobe Targetで：

1. **[!UICONTROL オーディエンス]**&#x200B;を選択します。
1. **[!UICONTROL Audiences]** ページで、CX Enterpriseから取得したオーディエンスを探します。 これらのオーディエンスは、Target アクティビティで使用できます。

   ![&#x200B; ターゲットオーディエンス &#x200B;](assets/target-audiences.png)
