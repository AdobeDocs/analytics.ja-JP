---
description: 3 段階のデプロイメントプロセスについて説明します。
title: 統合のデプロイ
uuid: a3c0ef21-ed9a-44d7-bdce-19b3bd5b8b80
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 統合のデプロイ {#deploying-the-integration}

3 段階のデプロイメントプロセスについて説明します。

この統合のデプロイは、以下の操作を必要とする簡単なプロセスです。

## 統合ウィザードの完了 {#completing-the-integration-wizard}

統合ウィザードを使用する手順です。

統合をアクティブ化するには、Data Connectors インターフェイス内で Lyris 統合ウィザードを完了する必要があります。

1. Adobe Experience Cloud 内の Data Connectors（旧称 Genesis）領域に移動します。

   ![](assets/data_connectors.png)

1. 「Lyris HQ」 **[!UICONTROL Add Integration]**&#x200B;の下のをクリックしま **[!UICONTROL Activate]**&#x200B;す。

   ![](assets/add_integration.png)

1. Under **[!UICONTROL General Settings]**, choose the desired Report Suite and provide a name for the integration.
1. Fill in all your Lyris account-related information under **[!UICONTROL Custom Values]**.

   ![](assets/general_settings.png)

1. ドロップダウンメニューから適切な予約済み eVar およびイベントを選択します。

   ![](assets/variable_mapping.png)

1. You may choose your own segments under **[!UICONTROL Your Segments]** - apart from the 3 automated Partner segments.
1. この統合では、いくつかのデータポイントを Lyris アカウントにダウンロードする必要が出る場合があります。You may choose to give access for this under **[!UICONTROL Access Request]**.
1. Under **[!UICONTROL Data Collection]**, you can choose to have an automated or a manual solution (JavaScript Plug-in) to collect query string parameters from the landing page URL. 自動ソリューションを選択する場合は、「メッセージ ID」と「受信者 ID」にクエリー文字列パラメーターを入力します。JavaScript プラグインについては、アドビコンサルタントにお問い合わせください。

   ![](assets/data_collection.png)

1. Lyris ダッシュボードとブックマークを自動的に生成することもできます。

   ![](assets/dashboard_generation.png)

1. Review the integration summary and click **[!UICONTROL Activate]**.

## Lyris EmailLabs 内の設定 {#configuration-within-the-lyris-emaillabs}

ウィザードの完了後に Lyris 内で設定する内容を説明する手順。

1. 統合ウィザードを完了したら、Lyris Professional チームと協力して Lyris HQ アカウントとの統合を完了し、テストを容易に行う必要があります。
1. URL クエリー文字列パラメーターの追加：ユーザーインターフェイスの「組織設定」領域に、URL 付加文字列が正しく入力されていることを確認します。キャンペーンレベル ID（hq_m）と受信者レベル ID（hq_v）を含める必要があります。

   文字列 ID の例：

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >Lyris のネイティブ分析ツールを適用する場合は、「*トラックをクリック*」をクリックして、追加する必要な変数すべてにタグ付けします。

## 統合の確認 {#verifying-the-integration}

Lyris／Adobe Analytics の統合が成功したことを確認する手順です。

すべてのデプロイメント手順が完了したら、統合によってデータが正常に転送されていることを検証できます。

>[!NOTE]データ交換が始まるまでに数日かかります。統合をアクティブ化した後で、Lyris に連絡するようにしてください。

1. Data Connectors 内で Lyris 統合に移動します。タブ>の下に、次のよ **[!UICONTROL Support]** うなイベントが表示され **[!UICONTROL Integration Activity Log]**&#x200B;ているはずです **[!UICONTROL Metric data imported successfully]****[!UICONTROL Classification data imported successfully]**。

   ![](assets/integration_info.png)

1. 適切な指標を使用して、Lyris メッセージレポートを表示します。In the Adobe Experience Cloud, select **[!UICONTROL Reports & Analytics]**.
1. 適切なレポートスイートを選択します。
1. の下 **[!UICONTROL Custom Conversions]**&#x200B;でを選択し、を **[!UICONTROL Message ID Reports]** 選択しま **[!UICONTROL Message ID/Message Name]**&#x200B;す。

## クエリー文字列パラメータープラグインコード {#query-string-param-plug-in-code}

Adobe Analytics で使用する Lyris プラグインコードを表示します。

>[!NOTE]以下のコードを操作する前に、必要な eVar を Adobe Analytics の管理ツールで予約するようにしてください。予約した eVar を特定したら、eVarN を関連する eVar に置き換えます。例：eVar10

```
/* 
  * Plugin: getQueryParam 2.3 
  */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/*in the s_doPlugins function - Replace N with actual eVar number*/ 
s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Message ID in eVarN variable s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Recepient ID in eVarN variable 
```
