---
description: 使用できる測定ライブラリを示します。
keywords: Analyticsの導入;収集、data;collection
seo-description: 使用できる測定ライブラリを示します。
seo-title: 追加ライブラリの概要
solution: Analytics
title: 追加ライブラリの概要
topic: 開発者と導入
uuid: 1ec291f6-073f-49d1- b6ab-044b1069db4e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 追加ライブラリの概要

使用できる測定ライブラリを示します。

以下の表では、使用可能なすべてのプラットフォームで Analytics データの収集に利用できるライブラリの概要を説明しています。詳しくは、[Analytics でのデータ収集](https://marketing.adobe.com/resources/help/en_US/reference/?f=usecase_sending_data_to_sc)を参照してください。

<table id="table_B01E5B7E5DEB42A28AB851E640A6F08E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 場所 </th> 
   <th colname="col2" class="entry"> オプション </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Web ブラウザー </td> 
   <td colname="col2"> <p>Experience Cloud のすべてのお客様は <a href="https://marketing.adobe.com/resources/help/en_US/dtm/" format="https" scope="external">Dynamic Tag Management</a> を利用できます。これは、すべてのソリューションの JavaScript タグと HTML ページタグを Web サイトに導入する方式の標準機能です。 </p> <p>JavaScript と HTML の測定を導入する他の方法については、<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/" format="http" scope="external">Analytics の導入ガイド</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Web サーバー </td> 
   <td colname="col2"> <p>ネイティブの PHP ライブラリや Java ライブラリを Web サーバー側で使用して、Analytics データを送信することができます。 </p> <p>Data Insertion API では HTTP POST および GET を使用して XML データをデータ収集サーバーに直接送信できます。また、データソースを利用して区切り付きテキスト形式のヒットデータを Analytics に直接送信できます。 </p> 
    <ul id="ul_B602F4D6610D46D6BA65F943E5BA296C"> 
     <li id="li_4F0A3CC0E5CD4F5AAEECF60A3D81C737"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/php/oms_sc_appmeasure_php.pdf" format="http" scope="external"> PHP AppMeasurement</a> </li> 
     <li id="li_D2431479035F45F4AB4CE0AF11B4C89C"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/java/oms_sc_appmeasure_java.pdf" format="http" scope="external"> Java AppMeasurement</a> </li> 
     <li id="li_74B5B70A2E7349EE9FB9721442D0C845"> <a href="https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api" format="https" scope="external"> Data Insertion API</a> </li> 
     <li id="li_45F309B87FFC40DF9EF0F263C3FB416A"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/" format="http" scope="external"> データソース</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> モバイル デバイス </td> 
   <td colname="col2"> <p>iOS、Android、Windows Phone 8、Blackberry、Symbian などのネイティブライブラリが用意されています。 </p> 
    <ul id="ul_DB6A44A2FF724B5BB36973FDFB8353A5"> 
     <li id="li_2B97BA81591747638D620A23881411F6"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/" format="http" scope="external">iOS AppMeasurement 4.x</a>（最新バージョン） </li> 
     <li id="li_DDC430E5119542EE8DC42D23EE99C4CC"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/ios/" format="http" scope="external"> iOS AppMeasurement 3.x</a> </li> 
     <li id="li_6323CE2240FD490292B39884BB00559C"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/" format="http" scope="external">Android AppMeasurement 4.x</a>（最新バージョン） </li> 
     <li id="li_AD7A2B3DD96A43FF8DEB003D49A02F5B"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/android/" format="http" scope="external"> Android AppMeasurement 3.x</a> </li> 
     <li id="li_46CB3ED239BC42419C996BFDF33046AE"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/wp8/" format="http" scope="external">Windows Phone 8 AppMeasurement 3.x</a>（最新バージョン） </li> 
     <li id="li_B4B01EDE735B4D6C97AAF468DBB64580"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/dotnet/oms_sc_appmeasure_dotnet.pdf" format="http" scope="external"> Silverlight、.NET、XBOX および Windows Phone 7 の AppMeasurement</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Flash </td> 
   <td colname="col2"> <p>ActionScript を使用した Flash アプリはデスクトップ上と Web 上で測定できます。 </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/oms_sc_appmeasure_flash.pdf" format="http" scope="external"> Flash、Flex および OSMF の AppMeasurement</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> デスクトップ </td> 
   <td colname="col2"> 
    <ul id="ul_44CAE5F5DEA94EAF9743DDB2863E906F"> 
     <li id="li_584B634DF4194FEEA48B8DABFB77454B"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/winrt/" format="http" scope="external">WinRT for Windows 8 AppMeasurement 3.x</a>（最新バージョン） </li> 
     <li id="li_A3613B71AD2E47CD96C8943117D75B0B"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/osx/" format="http" scope="external">OS X AppMeasurement 3.x</a>（最新バージョン） </li> 
     <li id="li_2FBE124EF9C943E092C1C5FDA5CDDEB8"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/java/oms_sc_appmeasure_java.pdf" format="http" scope="external"> Java AppMeasurement</a> </li> 
     <li id="li_ED11FA429E70488A80C27455401887DF"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/dotnet/oms_sc_appmeasure_dotnet.pdf" format="http" scope="external"> Silverlight、.NET、XBOX および Windows Phone 7 の AppMeasurement</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ビデオ </td> 
   <td colname="col2"> <p>すべてのプラットフォームでのビデオの測定については、以下のガイドを参照してください。 </p> 
    <ul id="ul_5C56F82F45264F63ABA184C48B27EE18"> 
     <li id="li_140B692CA3BE476BA024C37E7AE4872F"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/" format="http" scope="external">ハートビートビデオ測定</a>（最新バージョン） </li> 
     <li id="li_021D77CB25A54647A71F4AE7144EE788"> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/" format="http" scope="external"> マイルストーンビデオ測定</a> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<p class="- topic/p head"> <b class="+ topic/ph hi-d/b ">REST および SOAP Web サービス</b>（<a href="https://marketing.adobe.com/developer/" format="https" scope="external">Developer Connection</a>） </p>

* [はじめに](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)
* [API ドキュメントホーム](https://marketing.adobe.com/developer/documentation)

