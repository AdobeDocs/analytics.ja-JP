---
description: 管理ツールのデータガバナンスダイアログには、Experience Cloud 組織にマッピングされているかどうかや、データ保持ポリシーが設定されているかどうかなど、データガバナンスが設定されているレポートスイートの概要が表示されます。
seo-description: 管理ツールのデータガバナンスダイアログには、Experience Cloud 組織にマッピングされているかどうかや、データ保持ポリシーが設定されているかどうかなど、データガバナンスが設定されているレポートスイートの概要が表示されます。
seo-title: レポートスイートのデータガバナンス設定の表示／管理
title: レポートスイートのデータガバナンス設定の表示／管理
uuid: f3b83e8e-00af-4a60- a5de-29b5c43f6788
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# レポートスイートのデータガバナンス設定の表示／管理

管理ツールのデータガバナンスダイアログには、Experience Cloud 組織にマッピングされているかどうかや、データ保持ポリシーが設定されているかどうかなど、データガバナンスが設定されているレポートスイートの概要が表示されます。

1. Adobe Experience Cloud にログインします。
1. **[!UICONTROL Analytics]** / **[!UICONTROL 管理者]** / **[!UICONTROL データガバナンスに移動]** します。

   ログイン会社のレポートスイートがすべて表示されます。

   ![](assets/gdpr_setup_an.png)

<table id="table_448292730FF0475E9DCB731882F9A29B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>レポートスイート </p> </td> 
   <td colname="col2"> <p>1 行目では、レポートスイートのわかりやすい名前がリストされます。2 行目には、レポートスイートの内部名が含まれます。レポートスイートのラベルを設定することを許可されている場合、最初の行は、ラベル設定ページに移動するクリック可能なリンクになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>組織のマッピング </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EF8F613B0C5E42D19DB60BD0C89C114B"> 
     <li id="li_B35EE88555F547EFBF55ADE9D0C9EC3B"><b>マップ済み</b>：このレポートスイートは、ログインした Analytics ログイン会社として、同じ Experience Cloud 組織に既にマッピングされています。この設定のあるレポートスイートのみ、ラベル設定できます。 </li> 
     <li id="li_4E800BF80CFF477BAA091EF272D9071C"><b>レポートスイートをマップ</b>：このリンクをクリックすると、Experience Cloud 組織に<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">レポートスイートをマップ</a>できます。 <p>これは、レポートスイートを検索して適切な組織に割り当てる必要があるExperience Cloud組織-レポートスイートマッピング管理ページにリダイレクトされることを意味します。それが完了したら、このデータガバナンス画面に戻ります。 </p> </li> 
     <li id="li_FF825A65D089487BBF5FCB0D74D41CD7"><b>別の組織にマップ済み</b>：このレポートスイートは、別の Experience Cloud 組織に既にマッピングされています。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>データ保持ポリシー </p> </td> 
   <td colname="col2"> <p>Analytics の GDPR 実装では、データ保持ポリシーを適用する必要があります。 </p> <p>この設定では、以下の点を確認できます。 </p> 
    <ul id="ul_AC1F0827293B47E39BFEC4B1766A0CAC"> 
     <li id="li_3AAD93EA92B94C6180E5AEBC5E4D10FB">このレポートスイートに対してデータ保持ポリシーが適用されているかどうか。 </li> 
     <li id="li_2E8D71905C734F8BB3245FEEDA953B3E">アドビによってデータが保持される期間（この期間を過ぎると削除されます）。デフォルトのデータ保持期間は 25 ヶ月です。 </li> 
    </ul> <p>注意：データ保持期間が設定されていないと、Adobe Analytics は、GDPR API への要求の処理（お客様のエンドユーザーからのアクセス要求または削除要求の処理）をサポートすることはできません。データ保持期間の設定については、カスタマーサクセスマネージャーまでお問い合わせください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>グループ </p> </td> 
   <td colname="col2"> <p>グループ機能は、現在、実装されていません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>左側のサイドバー </p> </td> 
   <td colname="col2"> <p>ファネルアイコンをクリックして、サイドバーを開いたり閉じたりします。 </p> <p>「組織のマッピング」セクションには、説明された各カテゴリに分類されたレポートスイートの数が表示されます。 </p> <p>「データ保持ポリシー」セクションには、お客様の組織で現在実施されている独自の各データ保持ポリシーと、その保持ポリシーに割り当てられたレポートスイートの数が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CSV にエクスポート </p> </td> 
   <td colname="col2"> <p>1 つまたは複数のレポートスイートの隣のチェックボックスをオンにすると、「<span class="uicontrol">CSV にエクスポート</span>」オプションが表示されます。このオプションを使用すると、選択したすべてのレポートスイートのすべての変数に関する現在のすべてのラベル定義が含まれた CSV ファイルをダウンロードできます。 </p> <p>アドビでは、自社の法務チームにラベル設定の選択を確認することをお勧めしています。このオプションによって、この確認が容易になります。データガバナンス UI にログインしてレビューを実行しなくても、法務チームと .CSV ファイルを共有できます。 </p> <p><img placement="break"  src="assets/export_csv.png" width="300px" id="image_5FE821B2D07B402D8E0F6FE53D6FC52E" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

