---
description: Analysis Workspaceでアラートを作成する方法を説明します。
title: アラートの作成
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 24dd47e995523aedba1385ee8882af5e11c7b128
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 69%

---

# アラートの作成 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="時間の精度"
>abstract="時間の精度とは、アラートをチェックする頻度を指します。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>異常値検出を使用したアラート（_インテリジェントアラート_&#x200B;とも呼ばれる）の使用は、Adobe Analytics Prime または Ultimate パッケージを使用している組織でのみ使用できます。

Adobe Analytics のアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受信できます。また、Adobe Analytics パッケージに応じて、異常しきい値に基づいてトリガーされるアラートを使用することもできます。サーバーコールの使用状況アラートは、Analytics 管理者のみが使用できる別の種類のアラートです。これらのアラートは、サーバーコールの消費量とコミットメントデータの超過のリスクや発生件数を通知します。詳しくは、[サーバーコールの使用状況アラート](/help/admin/admin/c-server-call-usage/scu-alerts.md)を参照してください。

アラートの詳細については、「[ アラートの概要 ](intellligent-alerts.md)」を参照してください。

アラートを作成するには：

1. アラートを作成するには、次のいずれかの方法を使用します。:

   * Analysis Workspace でプロジェクトを開き、**[!UICONTROL コンポーネント]**／**[!UICONTROL アラートを作成]**&#x200B;を選択します。
   * Analysis Workspaceでプロジェクトを開き、ショートカットキー ***cmd + shift + a*** （macOS）または ***ctrl + shift + a*** （Windows）を使用します。
   * Analysis Workspace でプロジェクトを開き、フリーフォームテーブルで 1 つ以上の行項目を選択して右クリックし、「**[!UICONTROL 選択からアラートを作成]**」を選択します。このアクションにより、[ アラートビルダー ](alert-builder.md) がすぐに事前設定され、適切な指標およびフィルターでアラートが作成されます。
   * [アラートマネージャーから](/help/components/c-alerts/alert-manager.md#create-alerts)アラートを作成します。

   アラートビルダーが表示されます。このインターフェイスは、Analytics でセグメントや計算指標を作成するためのインターフェイスに精通しています。



## アラートビルダー

Alert Builder インターフェイスは、Customer Journey Analyticsでセグメントや計算指標を作成する際に使用するインターフェイスと似ています。

![ アラートビルダーインターフェイス ](assets/alert-builder.png)

アラートのアラートビルダーで次の詳細を指定します。

| 要素 | 説明 |
|---------|----------|
| **[!UICONTROL タイトル]** | アラート名を指定します。アラート名には、レポート名または指標のしきい値を含めることができます。 |
| **[!UICONTROL 説明（オプション）]** | アラートの説明を指定します。 |
| **[!UICONTROL 時間の精度]** | 指標を確認する頻度を日単位、週単位、または月単位で選択します。<p> |
| **[!UICONTROL 受信者]** | アラートの送信先を指定します。アラートは、Analytics ユーザー、Analytics グループ、生の電子メールアドレスまたは電話番号に送信できます。<p><b> 重要 </b>：電話番号の前には、`+` と [ 国コード ](https://countrycode.org/) が必要です。</p><p>ユーザーが受け取るメールの例を次に示します。</p><p>![アラートメール](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 有効期限]** | アラートの有効期限が切れる日時を設定します。 |
| **[!UICONTROL 遅延]** | データが完了し、Customer Journey Analytics でレポートできるようになるまでに必要な時間は組織によって異なりますが、通常はデータイベント時間から 3～9 時間です。アラートを正確にするには、特定のイベント範囲のイベントデータを完全にする必要があります。つまり、アドビでは指定されたイベント範囲のイベントデータを受信しなくなります。<p>この取り込み時間の遅延を考慮して、アラートを送信する前にデフォルトで 9 時間の遅延が設定されます。</p><p>デフォルトの 9 時間の遅延を 0～24 時間の間で調整できます。ただし、遅延を 9 時間未満に短縮すると、不完全なデータをレポートすることになり、アラート情報が不正確になる場合があります。</p><p>遅延時間を短縮する際は、次の点を考慮します。</p><ul><li>**データの可用性とデータの完全性について**：すべてのバッチデータは、3～9 時間後にのみExperience Platform データセットに取り込まれます。 アラートを正確にするには、データの取り込みが完了し、データセット内のすべてのバッチデータが使用可能になっている必要があります。</li><li>**データが完了してデータセットで使用できるようになるまでにかかる時間を判断**：データの取り込み時間は組織によって異なります。アラート配信に選択する遅延時間は、バッチデータが Platform データセットで使用可能になるまでの時間と同じか、それよりも少ない頻度であることを確認します<!--add link? -->。</li><p>**ヒント：**&#x200B;すべてのバッチデータが完了し、Platform データセットに取り込まれるまでに必要な時間を把握する最も正確な方法は、組織のデータエンジニアに相談することです。</p><p>または、組織内のバッチ配信がExperience Platform データセットで使用できるようになるまでに要する一般的な時間を把握できます。 Analysis Workspaceで次のフリーフォームテーブルを作成します。</p><ol><li>Analysis Workspace のフリーフォームテーブルに、[!UICONTROL **イベント**]&#x200B;指標と&#x200B;[!UICONTROL **日**]&#x200B;ディメンションを追加します。</li><li>[!UICONTROL **時間**]&#x200B;ディメンションを使用して&#x200B;[!UICONTROL **日**]&#x200B;ディメンションを分類します。<p>データのない時間は 0 と表示されます。</p></li></ol><li>**計算のエラーを考慮**: デフォルトの遅延時間を減らした場合、組織でのデータ取り込みの完了にかかる時間よりも少なくとも 1 時間長い遅延を設定します。 例えば、データ取り込みの完了までに 3 時間の遅延がある場合は、遅延を 4 時間に設定する必要があります。</li> |
| **[!UICONTROL 次の場合にアラートを送信]** | [!UICONTROL **これらの指標のいずれかがトリガーとなる場合**]：指標（計算指標を含む）をここにドラッグ＆ドロップして、アラートのトリガーを作成します。<p>アラート内のすべての指標、ディメンション、セグメントが現在選択されているデータビューと互換性がない場合は、**「互換性のないコンポーネント」**&#x200B;というメッセージが表示されます。</p><p>アラートが設定される前に指標が超過している必要があるしきい値を指定します。この値をしきい値に設定し、以下のいずれかの条件にすることができます。</p><ul><li>異常値が存在する</li><li>異常値が予測より上</li><li>異常値が予測より下</li><li>以上</li><li>以下</li><li>変更（％）</li><li>90％、95％、99％、99.75％、99.9％ のしきい値を設定できます。</li></ul><p>[!UICONTROL **これらのフィルターを全て使用する場合**]：セグメントまたはディメンションをドラッグ&amp;ドロップして、アラートにフィルターを追加します。 例えば、「モバイルデバイスのみ *のセグメントを追加すると* ルールトリガーがモバイルデバイスに対してのみ適用されます。 AND ステートメントを使用して、その他のフィルターを追加できます。ギアアイコンをクリックして、AND または OR ルールを追加できます。</p><p>ユースケースの例について詳しくは、[アラート - ユースケース](alerts-use-cases.md)を参照してください。</p> |
| **[!UICONTROL プレビュー]** | インタラクティブなアラートプレビューには、過去のエクスペリエンスに基づいてアラートが起動する頻度が概ね表示されます。<p>例えば、時間の精度を毎日に設定すると、プレビューにより、最近の 30 または 31 日間で、特定の指標に対してアラートが何回トリガーされたかがわかります。</p><p>トリガーされるアラートが多すぎる場合は、[ アラートの管理 ](alert-manager.md) でしきい値を調整できます。</p><p>![](assets/alert-preview.png){width="50%"}</p> |

<!--

   ![](assets/alert-builder.png)

1. Specify the following options to configure the alert:

   | Option | Description | 
   |---------|----------|
   | [!UICONTROL **Title**]  | Specify a name for the alert. The alert name might contain the name of the report or the metrics threshold. | 
   | [!UICONTROL **Description (optional)**] | Specify a description for the alert. | 
   | [!UICONTROL **Time granularity**] | Select how often you want the metric to be checked: Hourly, Daily, Weekly, or Monthly.<p><b>Note:</b> For report suites with a custom calendar, monthly granularity in the Alert Builder is not supported.<!--true?--</p | 
   | [!UICONTROL **Recipients**] | Specify where the alert can be sent. An alert can be sent to an Analytics user, an Analytics group, a raw email address, or to a phone number.<p><b>Important:</b> The phone number must be preceded by `+` and a [country code](https://countrycode.org/).</p><p>The e-mail that a user would receive once an alert has been triggered looks similar to:</p><p>![](assets/alerts-email.PNG)</p> | 
   | [!UICONTROL **Expiration date**] | Set the date and time when you want the alert to expire. | 
   | [!UICONTROL **Send an alert when**] | [!UICONTROL **Any of these metrics trigger**]: Drag and drop metrics (including calculated metrics) here to create triggers for the alert.<p>An **"incompatible components"** message appears if not all the metrics, dimensions, or segments in the alert are compatible with the currently selected data view.</p><p>Determine the threshold that the metric must exceed before an alert is set. You can set this value to a threshold and then to one of the following conditions:</p><ul><li>anomaly exists</li><li>anomaly is above expected</li><li>anomaly is below expected</li><li>is above or equals</li><li>is below or equals</li><li>changes by</li><li>You can set a threshold of 90%, 95%, 99%, 99.75%, and 99.9%.</li></ul><p>[!UICONTROL **With all of these filters**]: Drag and drop segments or dimensions to add filters. For example, adding a *Mobile Devices Only* segment would mean that the rule triggers only for mobile devices. You can add additional filters by using an AND statement. You can add AND or OR rules by clicking the gear icon.</p><p>See [Alerts - use cases](/help/components/c-alerts/alerts-use-cases.md) for example.</p> | 
   | [!UICONTROL **Preview**] | The interactive alert preview shows you how often, approximately, an alert will fire based on past experience.<p>For example, if you set the time granularity to daily, the preview can tell you that the alert would have been triggered for a certain metric x times during the last 30 or 31 days. The preview approximation window is established by the alert frequency setting. For daily alert frequencies, the preview window approximates the previous 30 days. For weekly alert frequencies, the preview window approximates the last 12 weeks. For monthly alert frequencies, the preview window approximates the previous 12 months.</p><p>If you find that too many alerts will be triggered, you can adjust the threshold in the [Alert Manager](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Select [!UICONTROL **Save**].

-->