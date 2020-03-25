---
description: 3 段階のデプロイメントプロセスについて説明します。
title: 統合のデプロイ
uuid: a3c0ef21-ed9a-44d7-bdce-19b3bd5b8b80
translation-type: ht
source-git-commit: a3aa8feb937e2a1f40c498aa4e143de21cf26b86

---


# 統合のデプロイ {#deploying-the-integration}

3 段階のデプロイメントプロセスについて説明します。

この統合のデプロイは、以下の操作を必要とする簡単なプロセスです。

## 統合ウィザードの完了 {#completing-the-integration-wizard}

統合ウィザードを使用する手順です。

統合をアクティブ化するには、Data Connectors インターフェイス内で Lyris 統合ウィザードを完了する必要があります。

1. Adobe Experience Cloud 内の Data Connectors（旧称 Genesis）領域に移動します。

   ![](assets/data_connectors.png)

1. 「**[!UICONTROL 統合を追加]**」の「Lyris HQ」で、「**[!UICONTROL アクティブ化]**」をクリックします。

   ![](assets/add_integration.png)

1. 「**[!UICONTROL 一般設定]**」で目的のレポートスイートを選択し、統合の名前を指定します。
1. 「**[!UICONTROL カスタム値]**」で、Lyris アカウント関連の情報をすべて入力します。

   ![](assets/general_settings.png)

1. ドロップダウンメニューから適切な予約済み eVar およびイベントを選択します。

   ![](assets/variable_mapping.png)

1. 自動化された 3 つの Partner セグメントの他に「**[!UICONTROL セグメント]**」で自分のセグメントを選択することもできます。
1. この統合では、いくつかのデータポイントを Lyris アカウントにダウンロードする必要が出る場合があります。「**[!UICONTROL アクセス要求]**」で、このアクセス権を付与することもできます。
1. 「**[!UICONTROL データ収集]**」で、自動または手動のソリューション（JavaScript プラグイン）を選択し、ランディングページの URL からクエリー文字列パラメーターを収集します。自動ソリューションを選択する場合は、「メッセージ ID」と「受信者 ID」にクエリー文字列パラメーターを入力します。JavaScript プラグインについては、アドビコンサルタントにお問い合わせください。

   ![](assets/data_collection.png)

1. Lyris ダッシュボードとブックマークを自動的に生成することもできます。

   ![](assets/dashboard_generation.png)

1. 統合の概要を確認し、「**[!UICONTROL アクティブ化]**」をクリックします。

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

> [!NOTE]データ交換が始まるまでに数日かかります。統合をアクティブ化した後で、Lyris に連絡するようにしてください。

1. Data Connectors 内で Lyris 統合に移動します。「**[!UICONTROL サポート]**」タブ／**[!UICONTROL 統合アクティビティログ]**&#x200B;に、「**[!UICONTROL 指標データは正常にインポートされました]**」や「**[!UICONTROL 分類データは正常にインポートされました]**」などのイベントが表示されます。

   ![](assets/integration_info.png)

1. 適切な指標を使用して、Lyris メッセージレポートを表示します。Adobe Experience Cloud で、「**[!UICONTROL Reports &amp; Analytics]**」を選択します。
1. 適切なレポートスイートを選択します。
1. 「**[!UICONTROL カスタムコンバージョン]**」で、「**[!UICONTROL メッセージ ID レポート]**」、「**[!UICONTROL メッセージ ID / メッセージ名]**」の順に選択します。

## クエリー文字列パラメータープラグインコード {#query-string-param-plug-in-code}

Adobe Analytics で使用する Lyris プラグインコードを表示します。

> [!NOTE]以下のコードを操作する前に、必要な eVar を Adobe Analytics の管理ツールで予約するようにしてください。予約した eVar を特定したら、eVarN を関連する eVar に置き換えます。例：eVar10

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
