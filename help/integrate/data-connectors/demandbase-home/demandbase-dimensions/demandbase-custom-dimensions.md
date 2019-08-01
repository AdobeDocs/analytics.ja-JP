---
description: Adobe統合ウィザードの手順4で指定できるオプションのディメンション識別子を示します。
seo-description: Adobe統合ウィザードの手順4で指定できるオプションのディメンション識別子を示します。
seo-title: Demandbaseカスタムディメンション
title: Demandbaseカスタムディメンション
uuid: d1621046-3aa2-46b9- a536-4a8fb792b69f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Demandbase Custom Dimensions{#demandbase-custom-dimensions}

Adobe統合ウィザードの手順4で指定できるオプションのディメンション識別子を示します。

ウィザードに入力するためのAPI IDが不明な場合は、Demandbase担当者にお問い合わせください。

>[!IMPORTANT]
>
>IPアドレスをカスタムディメンションとして含めないことを強くお勧めします。非常に多くの一意の値を使用すると、レポートに関するパフォーマンスの問題が発生する可能性があります。さらに、IPアドレスは、Adobe Data Warehouseレポートを介してレポートオプションとして提供されています。

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディメンション </th> 
   <th colname="col2" class="entry"> API ID </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISP </td> 
   <td colname="col2"> ISP </td> 
   <td colname="col3"> 識別された組織がISPとして分類されるかどうかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> マーケティングエイリアス </td> 
   <td colname="col2"> marketing_ alias </td> 
   <td colname="col3"> 広告、メッセージまたはマーケティングコピーで使用する、整理された組織名（32文字以下）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アカウント監視タグ </td> 
   <td colname="col2"> watch_ list（カスタム） </td> 
   <td colname="col3">API応答データに追加できるクライアントによって定義された、無制限のタグセット（組織別）。 <p><b></b>例:"Q4Target"という名前の監視タグがある場合、APIフィールドは </p> <code> watch_ list_ q4_ target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hover1000 </td> 
   <td colname="col2"> history_1000 </td> 
   <td colname="col3"> 組織が「フォーチュン1000"リストにあるかどうかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes2000 </td> 
   <td colname="col2"> forbs_2000 </td> 
   <td colname="col3"> 組織がForbes2000リストにあるかどうかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 従業員数 </td> 
   <td colname="col2"> employee_ count </td> 
   <td colname="col3"> 組織で使用されている人数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 年間販売 </td> 
   <td colname="col2"> monthary_ sales </td> 
   <td colname="col3"> 公共エンティティの場合、年間収益は、すべての場所におけるグローバルHQの会社報告公開レコードに基づきます。非公開の組織では、年間販売売上高の予測予測に基づいています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 電話番号 </td> 
   <td colname="col2"> 電話番号 </td> 
   <td colname="col3"> 特定された組織の電話番号。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 住所 </td> 
   <td colname="col2"> sportet_ address </td> 
   <td colname="col3"> 特定された組織の住所。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 市区町村 </td> 
   <td colname="col2"> 市町村 </td> 
   <td colname="col3"> 特定された組織の市区町村。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 都道府県 </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> 特定された組織の状態。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国コード </td> 
   <td colname="col2"> country_ code </td> 
   <td colname="col3"> 特定された組織のISO2文字の国コード。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国名 </td> 
   <td colname="col2"> country_ name </td> 
   <td colname="col3"> 特定された組織の国名の国名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 郵便番号 </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> 特定された組織の国/州の郵便番号。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Web サイト </td> 
   <td colname="col2"> web_ site </td> 
   <td colname="col3"> 組織が識別するURL。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stock Ticker </td> 
   <td colname="col2"> stock_ ticker </td> 
   <td colname="col3"> 特定の組織が正式に取引されている場合の株価。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プライマリSICコード </td> 
   <td colname="col2"> primary_ signed </td> 
   <td colname="col3"> 特定された組織用に割り当てられたコンセンサスのSSIコード。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 緯度 </td> 
   <td colname="col2"> Latitude </td> 
   <td colname="col3"> 特定された組織の場所の緯度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 経度 </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> 特定の組織の位置の経度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トラフィック </td> 
   <td colname="col2"> トラフィック </td> 
   <td colname="col3"> Webサイトトラフィックの量（低、中、高、高）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> 特定の会社が主に他の企業に販売することを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> 特定の会社が主に消費者または個人に販売することを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 技術インサイト </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> 広告、メッセージ、またはマーケティングコピーを使用して、顧客によって顧客によって定義される75個までのテクノロジーカテゴリ、広告、メッセージ、またはマーケティングコピーを使用して定義されます。 </td> 
  </tr> 
 </tbody> 
</table>

