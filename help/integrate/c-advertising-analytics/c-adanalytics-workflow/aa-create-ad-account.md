---
title: 広告アカウントの設定
uuid: 4e37caa3-e4a5-43ad-97c0-12db62ad5283
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 広告アカウントの設定

Adobe Analytics管理者は、新しい広告アカウントを作成し、複数のアカウントを複数のレポートスイート(1:1、1:Many、Many:Many)にマッピングできます。

管理者は、広告ア [カウントを設定するために](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) 、管理者以外の人にアクセス権を付与できます。

![](assets/aa_accounts.png)

1. Adobe Analyticsで、/に移動し **[!UICONTROL Admin]** ます **[!UICONTROL Advertising Accounts]**。
1. （初回の使用のみ）エンドユーザー使用許諾契約の条項に同意します。
1. クリック **[!UICONTROL + Add]**.
1. ダイアログ [!UICONTROL New Search Engine Account] が表示されます。

   ![](assets/aa_new_se_account.png)

1. 次のガイドラインに **[!UICONTROL Search Engine Settings]** 従ってください。

   <table id="table_B3BE66B7D4C54766B8FFD2C6DCD657AF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 設定 </th> 
      <th colname="col2" class="entry"> 説明 </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>タイプ </p> </td> 
      <td colname="col2"> <p>Google AdWords と Microsoft Bing　Ads の 2 つのオプションがあります。 </p> <p>注意：Yahoo Gemini は、2019 年 3 月 31 日に Microsoft Bing に吸収されました。その結果、Yahoo Gemini 広告アカウントオプションは使用できなくなりました。  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>アカウント名 </p> </td> 
      <td colname="col2"> <p>このアカウント名は、任意の名前に設定できます。 これは、UIに表示されるアカウントのわかりやすい名前です。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>OAuthトークン </p> </td> 
      <td colname="col2"> <p>注意：OAuth はアクセス委任のオープン標準です。Web サイトまたはアプリケーションに他の Web サイト上にある関連情報へのアクセス権限を付与しても、パスワードを渡さないようにする方法として一般的に使用されます。 </p> <p>注意：サードパーティの URL（efrontier.com）への誘導を示すメッセージが表示されます。アドビは efrontier を使用して 3 つのすべての検索エンジンに対して OAuth 認証プロセスを強化しています。 </p> <p>注意：Internet Explorer 11（または以前のバージョン）を使用している場合、3 つのどの検索エンジンでも OAuth のトークンを正しく取得できません。代わりに、他のWebブラウザーを使用します。 </p> <p>「Retrieve<span class="uicontrol"> Token</span> 」をクリックすると、OAuth2認証プロセスが起動します。 つまり、資格情報を使用してGoogle/Bing検索アカウントにサインインするように求められます。 選択した検索エンジンに応じて、プロセスが少し異なります。 </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google Adwords:GoogleアカウントIDを入力します。 </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing:BingアカウントIDとBing顧客IDを指定します。 </li> 
        </ul> <p>Refer to <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md"  > Locate your Account ID</a> for information on these IDs. </p> <p>正しくログインすると、「OAuth のトークン」フィールドに「 
        <systemoutput>
          取得済み
        </systemoutput>」と表示されます。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. In the **[!UICONTROL Tracking]** section, you provide information on how the Search Engine data is tracked by your Adobe Analytics implementation. これは、検索エンジンのデータで Adobe Analytics のデータを適切に拡張するために必要な手順です。次のガイドラインに **[!UICONTROL Tracking Settings]** 従ってください。

   <table id="table_1AB4E31456E84ABF8209B02058259C4D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 設定 </th> 
      <th colname="col2" class="entry"> 説明 </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>タイプ </p> </td> 
      <td colname="col2"> 
        <ul id="ul_1C5A0502A4984E57A08417A91CCD6FFE"> 
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol">自動</span>：Advertising Cloud Engine によって、トラッキングパラメーターを検索エンジンのトラッキングテンプレート／リンク先 URL に追加する方法が決定されます。これはもっともシンプルな方法ですが、統合されたデータセットの品質が最良ではなくなる可能性があります。 <p>重要：「自動モード」で検索エンジンのアカウントを設定するには、以下の作業を行う責任があります。 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">「s_kwcid」パラメーターと値が、追加するアカウント内のアカウント追跡ランディングページまたはテンプレートURLに追加されます。 URLの末尾に挿入されます。 その結果、WebサーバーでURLの末尾に特定のkey=valueペアが必要な場合や、URL内の新しいkey=valueペアをサポートするための更新が必要な場合は、追加のアクションが必要になる場合があります。 </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">また、キーワードは「s_kwcid」値の一部としてランディングURLに挿入できます。特殊文字や記号が含まれている場合は、Webサーバーでそれらの文字がサポートされることを確認してください（一般的な特殊文字は「+」で、「部分一致変更済み」キーワードで使用されます）。 </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol">手動</span>：トラッキングパラメーターを検索エンジンのトラッキングテンプレート／リンク先 URL に追加する方法を管理できます。<a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md"  >各検索エンジンについては手動トラッキングの例を参照してください</a>。 </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. このセクシ **[!UICONTROL Mapping]** ョンで、この検索エンジンアカウントにリンクするレポートスイートを選択します。 広告アカウントを保存する前に、少なくとも1つのレポートスイートを指定する必要があります。 複数のアカウントを複数のレポートスイート(1:1、1:Many、Many:Many)にマップできます。 AMOが検索エンジンから取り込むデータは、単にマップされた任意のレポートスイートにコピーされるので、データの分割は行われません。

   >[!IMPORTANT]
   >
   >[Experience Cloud 組織にマッピング](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html)されたレポートスイートのみが選択できます。使用するレポートスイートが表示されない場合は、[Advertising Analytics のトラブルシューティング](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md)を参照してください。

   次のガイドラ **[!UICONTROL Mapping Settings]** インを参照してください。

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 設定 </th> 
      <th colname="col2" class="entry"> 説明 </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>レポートスイートマッピング </p> </td> 
      <td colname="col2"> <p>レポートスイートのマッピングによって、この検索エンジンアカウントにリンクされるレポートスイートが決まります。 つまり、検索エンジンのデータをどのレポートスイートに送信するかを決定します。 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html"  >使用するレポートスイートが表示されない場合、このツールを使用してレポートスイートを Experience Cloud</a> 組織にマッピングできます。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. クリック **[!UICONTROL Save]**.
1. 保存すると、免責条項に警告のリストが表示されます。 お読みになり、本契約を理解していることを確認するメッセージが表示されます。 Click the checkbox, then click **[!UICONTROL OK]**.

   これで、広告アカウントの管理UIに移動し [、新しく作成した](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md)アカウントが表示されます。

>[!NOTE] 検索エンジンのデータが Analytics レポートに入力され始めるまでに 24 時間以上かかることを想定する必要があります。

