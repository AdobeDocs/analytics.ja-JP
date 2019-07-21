---
description: 'null'
seo-description: 'null'
seo-title: Adobe Analytics GGPRワークフロー
title: Adobe Analytics GGPRワークフロー
uuid: f24e8be3-8b5c-409b- ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Adobe Analytics GGPRワークフロー

ここでは、Adobe Analytics で GDPR 対応の準備を進める方法について説明します。このワークフローでは、GDPR におけるデータ主体のアクセスおよび削除の権利に対応できるよう Adobe Analytics を設定する手順を解説します。

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> タスクの説明 </th> 
   <th colname="col3" class="entry"> 手順と詳細情報のリンク </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" />GDPR 関連のデータを含む可能性があるレポートスイートをすべて、Experience Cloud（または IMS）組織にマッピングします。 </p> <p>GDPR 要求は Experience Cloud 組織を使用して送信され、その組織が要求するすべてのレポートスイートに適用されます。要求は、その組織にマッピングされていないレポートスイートには適用されません。ログイン会社のレポートスイートだったとしてもそれは同様です。 </p> </td> 
   <td colname="col3"> <p><a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">組織へのレポートスイートのマッピング</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/>データ保持ポリシーを設定します。 </p> </td> 
   <td colname="col3"> <p>アドビが GDPR のアクセス要求および削除要求に対応できるよう、データ保持ポリシーを設定する必要があります。 </p> <p>詳しくは、この<a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Analytics データ保持の FAQ</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" />DULE／GDPR ラベル、Adobe Analytics ID、名前空間および ID 拡張について確認します。 </p> </td> 
   <td colname="col3"> <p> このドキュメントの以下のトピックを参照してください。 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Analytics 変数用の GDPR ラベル</a> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">リスト項目 </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> ラベル設定に関するベストプラクティス</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" />レポートスイート内の各変数に、識別、機密性、データガバナンスのラベルを割り当てます。 </p> <p>注意：ラベル設定は、新しいレポートスイートが作成されるたびに、または既存のレポートスイート内で新しい変数を有効にする際に、確認する必要があります。また、新しいソリューション統合が有効になると、ラベル設定が必要になる可能性のある新しい変数を公開できるので、ラベル設定を確認する必要があります。モバイルアプリまたは Web サイトを再実装すると、既存の変数の使用方法が変わる可能性があり、これにより、ラベルを更新する必要が生じる可能性があります。 </p> </td> 
   <td colname="col3"> <p> Follow the instructions in <a href="../../admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" />Adobe GDPR API に接続し、アクセス要求および削除要求を送信します。 </p> </td> 
   <td colname="col3"> <p>Adobe Analytics をご利用のお客様は、<a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external">Adobe Experience Cloud GDPR API</a> を呼び出すことで、顧客データに対する GDPR のアクセス要求および削除要求を個別に送信できます。 </p> <p><a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local">ラベル設定に関するベストプラクティス</a>の説明に沿って、要求時に Analytics 識別子と対応する名前空間 ID（データソース ID）を送信できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" />レポートスイートの GDPR 設定を表示、管理します。 </p> </td> 
   <td colname="col3"> <p>Follow the instructions in <a href="../../admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
