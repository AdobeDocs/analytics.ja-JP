---
description: 'null'
seo-description: 'null'
seo-title: Adobe Analytics データプライバシーワークフロー
title: Adobe Analytics データプライバシーワークフロー
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Adobe Analytics データプライバシーワークフロー

Adobe Analytics およびデータプライバシー対応にようこそ。このワークフローでは、データプライバシーにおけるデータ主体のアクセスおよび削除の権利に対応できるよう Adobe Analytics を設定する手順を解説します。

<!--
<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Task Description </th> 
   <th colname="col3" class="entry"> Links to Instructions and More Information </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Ensure that any of your report suites that might contain Data Privacy-relevant data are mapped to your Experience Cloud (or IMS) organization. </p> <p>Data Privacy requests are submitted using an Experience Cloud Organization and will be applied to all report suites claimed by that Organization. Requests will not apply to report suites not mapped to that Organization, even if they are part of your login company. </p> </td> 
   <td colname="col3"> <p>Refer to <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html"> Map report suites to an organization</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Set your data retention policy. </p> </td> 
   <td colname="col3"> <p>A data retention policy needs to be in place in order for Adobe to service Data Privacy data access/delete requests. </p> <p>For more information, see this <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html"> Analytics Data Retention FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarize yourself with DULE/Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion. </p> </td> 
   <td colname="col3"> <p> Read these topics in this documentation set: 
     <ul> 
      <li><a href="/help/admin/c-data-governance/gdpr-labels.md"> Data Privacy Labels for Analytics Variables</a> </li> 
      <li><a href="/help/admin/c-data-governance/gdpr-analytics-ids.md"> Labeling Best Practices</a>--> </li>
    &lt;/ul&gt; &lt;/p&gt; &lt;/td&gt;
</tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" />レポートスイート内の各変数に、識別、機密性、データガバナンスのラベルを割り当てます。 </p> <p>注意：ラベル設定は、新しいレポートスイートが作成されるたびに、または既存のレポートスイート内で新しい変数を有効にする際に、確認する必要があります。また、新しいソリューション統合が有効になると、ラベル設定が必要になる可能性のある新しい変数を公開できるので、ラベル設定を確認する必要があります。モバイルアプリまたは Web サイトを再実装すると、既存の変数の使用方法が変わる可能性があり、これにより、ラベルを更新する必要が生じる可能性があります。 </p> </td> 
   <td colname="col3"> <p> 「<a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md">レポートスイートデータのラベル付け</a>」の手順に従います。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" />Adobe データプライバシー API に接続し、アクセス要求および削除要求を送信します。 </p> </td> 
   <td colname="col3"> <p>As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html"> Adobe Experience Cloud Data Privacy API</a>. </p> <p><a href="/help/admin/c-data-governance/gdpr-analytics-ids.md">ラベル設定に関するベストプラクティス</a>の説明に沿って、要求時に Analytics 識別子と対応する名前空間 ID（データソース ID）を送信できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" />レポートスイートのデータプライバシー設定を表示、管理します。 </p> </td> 
   <td colname="col3"> <p>「<a href="/help/admin/c-data-governance/gdpr-view-settings.md">レポートスイートのデータガバナンス設定の表示</a>」の手順に従います。 </p> </td> 
  </tr> 
 </tbody> 
</table>
--&gt;

| タスクの説明 | 手順と詳細情報のリンク |
|--- |--- |
| **手順 1**：データプライバシー関連のデータを含む可能性があるレポートスイートをすべて、Experience Cloud（または IMS）組織にマッピングします。データプライバシー要求は Experience Cloud 組織を使用して送信され、その組織が要求するすべてのレポートスイートに適用されます。要求は、その組織にマッピングされていないレポートスイートには適用されません。ログイン会社のレポートスイートだったとしてもそれは同様です。 | [組織へのレポートスイートのマッピング](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)を参照してください。 |
| **手順2**:データ保持ポリシーを設定します。 | アドビがデータプライバシーのデータのアクセス要求および削除要求に対応できるよう、データ保持ポリシーを設定する必要があります。詳しくは、この[Analytics データ保持の FAQ](/help/technotes/data-retention.md) を参照してください。 |
| **手順 3：** DULE／データプライバシーラベル、Adobe Analytics ID、名前空間および ID 拡張について確認します。 | このドキュメントの以下のトピックを参照してください。<ul><li>[Analytics 変数のデータプライバシーラベル](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[ラベル設定に関するベストプラクティス](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **手順 4**：レポートスイート内の各変数に、識別、機密性、データガバナンスのラベルを割り当てます。注意：ラベル設定は、新しいレポートスイートが作成されるたびに、または既存のレポートスイート内で新しい変数を有効にする際に、確認する必要があります。また、新しいソリューション統合が有効になると、ラベル設定が必要になる可能性のある新しい変数を公開できるので、ラベル設定を確認する必要があります。モバイルアプリまたは Web サイトを再実装すると、既存の変数の使用方法が変わる可能性があり、これにより、ラベルを更新する必要が生じる可能性があります。 | 「[レポートスイートデータのラベル付け](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)」の手順に従います。 |
| **手順 5**：Adobe データプライバシー API に接続し、アクセス要求および削除要求を送信します。 | Adobe Analytics をご利用のお客様は、[Adobe Experience Cloud データプライバシー API](https://www.adobe.io/apis/experienceplatform/gdpr.html)を呼び出すことで、顧客データに対するデータプライバシーのアクセス要求および削除要求を個別に送信できます。[ラベル設定に関するベストプラクティス](/help/admin/c-data-governance/gdpr-analytics-ids.md)の説明に沿って、要求時に Analytics 識別子と対応する名前空間 ID（データソース ID）を送信できます。 |
| **手順 6**：レポートスイートのデータプライバシー設定を表示、管理します。 | 「[レポートスイートのデータガバナンス設定の表示](/help/admin/c-data-governance/gdpr-view-settings.md)」の手順に従います。 |
