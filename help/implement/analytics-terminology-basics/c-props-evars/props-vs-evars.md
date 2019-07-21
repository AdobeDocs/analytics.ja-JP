---
description: Experience Cloud では複数のタイプの変数を使用できます。最もよく使用される 2 つのタイプである prop と eVar は、標準装備のレポートで提供されないカスタムディメンションについてのレポートをサイトに提供することを可能にします。
keywords: Analyticsの導入;prop;evar;prop vs evar;命名規則;トラフィック変数、persistence;successイベント;パス
seo-description: Experience Cloud では複数のタイプの変数を使用できます。最もよく使用される 2 つのタイプである prop と eVar は、標準装備のレポートで提供されないカスタムディメンションについてのレポートをサイトに提供することを可能にします。
seo-title: Prop と eVar の比較
solution: Analytics
title: Prop と eVar の比較
topic: 開発者と導入
uuid: 0f02760f- ff69-481c- a817-799f02dafe8e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Prop と eVar の比較

Experience Cloud では複数のタイプの変数を使用できます。最もよく使用される 2 つのタイプである prop と eVar は、標準装備のレポートで提供されないカスタムディメンションについてのレポートをサイトに提供することを可能にします。

割り当てる変数のタイプや場所を判断する際は、prop と eVar の機能性の違いを理解していることが重要です。これらの違いを理解していれば、最適の変数のタイプを判断できます。

**prop と eVar の違い**

prop と eVar の主な違いは以下のとおりです。

* **命名規則**：prop はトラフィック変数とみなされます。つまり、サイトの各種ディメンションの表示頻度についてレポートするために使用されます。eVar はコンバージョン変数とみなされます。成功イベントへの貢献度が高いサイトディメンションを判断するために使用されます。
* **持続性**：prop は呼び出し元のイメージリクエストの完了後は持続しません。prop を同じイメージリクエスト内にない他の変数と関連付けることはできません。一方、eVar は持続性があります。元々呼び出された際の値がバックエンド変数によって保持されるため、後で発生する成功イベントと関連付けることができます。
* **成功イベント**：コンバージョンイベントとも呼ばれる成功イベントは、訪問者が目標に到達した回数を測定する指標です。このイベントには、サイトでの商品購入からニュースレターの購読まで、あらゆるイベントを指定できます。eVar はコンバージョンイベントについてレポートするように設計されており、訪問者の目標到達に与えた影響が特に大きい値を示します。トラフィック変数はこの機能を持っていません。ただし、レポートスイートを正しく構成すればパーティシペーション指標を表示できます。
* **パス**：prop はパスを使用できます。これにより、表示する変数のコンテキスト内でユーザーが通った特定のパスを表示できます。アドビ担当者はリクエストがあった場合にパスを有効にできます。eVar はパスを使用できません。
* **使用可能な指標**：prop と eVar で使用可能な指標は、変数の設定やデータのプラットフォーム／バージョンによって異なります。以下のリストは、有効化可能な指標（デフォルトでは有効化されていない）を示しています。レポートで使用したい特定の指標が表示されない場合は、サポート対象ユーザーがカスタマーケアに連絡してください。

<table id="table_FB963F60857A4AD79562324FB6F4B6A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>指標 </p> </th> 
   <th colname="col2" class="entry"> <p>prop </p> <p>(トラフィック変数) </p> </th> 
   <th colname="col3" class="entry"> <p>eVar </p> <p>(コンバージョン変数) </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>平均ページの深さ </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_165C1BF1574247CEA9190ADCABF79D69" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サイトでの平均 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_9F0F396E11B442959EC3E5D4D508496D" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>バウンス率 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_A268EAF747EA45F8A6A93A1B66667A06" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_09D486144CEA4293A505DCA3F90B82EC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>バウンス </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_471A02B78FD842BB97ED3FF4A5908B03" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D2F11B5687484D9EBF6D1DEB3F303A20" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>計算指標 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_7FAB1CF2ACC44D9198C648D3FC9E52D9" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8BCC2EE92CC04778809D1BD48D2623D7" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタムコンバージョンイベント </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D75C764B83AE4491A7E68C459FED1300" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>入口 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E9A1FCDFCB924D75ABFAEBD5570D4EE0" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5E57974B5A64F3FA3A145428420EB23" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>出口 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_BE343F94EAD74D54B6ABC80E8A76A9BD" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_3183B2BB62C24B048EDED3295F2BEC85" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>インスタンス </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8733F5AC189E43DAA8D1847416EA68C8" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_B10AB2898F3D4EBA947FADB27B118143" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページビュー数 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8BD2B23FBDA64A648BED40A2993F7C1C" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_CBDFD74340FA4973847033C1F956F0AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パーティシペーション指標 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E63F978830FB46809E62654F37C4C182" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_6AB756A4598F4452887D29AD4971985A" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>購入指標 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8F8AB7CD02764245BA73CA1E6B69BAE1" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リロード回数 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_FBE0C84E01004937B7B408198A33A9E7" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>買い物かご指標 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_123993465D734EABB311730ED03263F6" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>単一アクセス </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_038C6991E3F341B18E7A355D17C88895" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合計滞在時間 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_090587D29F1649319033D5A15B34B138" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_841DF09FD32A44B1B1B876F4E0CE29AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>実訪問者数 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_38556E6A43B04E2E8A01855452D30A83" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5D4BDE1AA9C4C58A6402418390EEC52" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪問回数 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_017BB279C5824028870360A5D4D27556" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

* **分類**：prop は相関関係を使用して、同じイメージリクエスト内で呼び出された他のトラフィック変数に関するページビュー数を表示します。eVar は下位関係を使用して、成功イベントに関連する他のコンバージョン変数による分類を提供します。

## prop または eVar 固有の利点 {#section_B384031AB8674065BA5187B0A3A3DAB9}

バージョン 15 のリリースでは、prop と eVars の機能にほとんど違いはありません。eVar は最近アップデートされ、訪問回数／実訪問者などの機能とパス指標が追加されました。

prop は eVar の利点をいくつか有しており、その一部は回避することができます。

* prop データは収集されてすぐにレポートで使用できます。eVar はレポートスイートデータに表示されるまでに 30 分以上かる場合があります。
* すべての prop でフローチャート形式のレポートを有効にすることができます。これにより、訪問者のサイトまでの遷移を確認できます。These pathing flow reports are available for both Props and eVars in [!UICONTROL Ad Hoc Analysis].
* prop は複数のレベルに関連付けることができますが、eVar は下位レベルに一度だけ関連付けることができます。この制限は、セグメント化を使用し、クロス集計として同一データを提供することで軽減できます。
* パーティシペーション指標では、成功イベントの前に関係した prop の値を確認できます。

一方、eVar は prop の制限的な特性を凌ぐ様々な利点を有しています。

* eVar は、成功イベントを指標として使用できます。prop はできません。
* eVar の期限は、すべてのヒットに有効期限を持たせるなどカスタマイズできます（ただし、永続値は設定できません）。prop はどのような方法であれ保持されません。

合計滞在時間、入口、出口などのパス指標は、以前は eVar でのみ使用できました。しかし、最近のアップデートにより eVar の値が増え、これらの指標を使用できるようになりました。

## どちらを使用するか {#section_022D016A4EEB45179A15BFF044A261A4}

**prop：**&#x200B;待ち時間が最大の懸念事項であり、このディメンションで（成功イベントではなく）トラフィックの測定のみをおこなう場合に適しています。

**eVar：**&#x200B;データの分類と関係性が最大の懸念事項である場合に適しています。

>[!TIP]
>
>eVarを永続的にしないようにするには、その有効期限を「ヒット」に変更して、ヒット以外のデータを保持しないようにします。

