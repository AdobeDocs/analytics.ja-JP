---
description: 'null'
seo-description: 'null'
seo-title: よくある質問
title: よくある質問
uuid: 1cd41253-d74f-4b92-92e6-56f9afa3df85
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# よくある質問

<table id="table_FA37A4B3960C4181B9CCDB569A476936"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>顧客（データコントローラー）が検証したエンドユーザー（データサブジェクト）に対するアクセスおよび削除のリクエストは、Adobe Analyticsでどのようにサポートされますか。</b> </p> </td> 
   <td colname="col2"> <p>様々なデータプライバシールール(GDPR、CCPA)が有効になると、Adobe Analyticsは、より自動化されたプロセスを有効にするために、Data ControllersがExperience Cloud Data Privacy APIに送信する検証済みのリクエストの処理をサポートします。 アドビのデータプライバシーAPIは、Adobe Experience cloudソリューションに保存されたお客様のデータに対する個々の権利の要求（アクセスや削除の要求など）を処理するのに役立つように設計されています。 データ主体から企業が受け取ったデータアクセスおよび削除要求の数に応じた柔軟性とスケーラビリティがあります。また、Data Privacy APIを使用すると、顧客はデータアクセスと削除の要求がどのように処理されているかをステータスで確認できます。 </p> <p>For more details see <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external"> Data Privacy API documentation </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>エンドユーザーからのデータプライバシーリクエストの受信、受け入れ、および履行を担当するのは誰ですか。</b> </p> </td> 
   <td colname="col2"> <p>データコントローラー（アドビのお客様）は、データプライバシーに基づく個々の権利の要請に応じて個人データをデータの対象に提供する責任を負います。 また、データコントローラーは、リクエストを受け取り、リクエストを受け入れる唯一の責任を持ちます。その一部は、Adobe Analyticsに保存されたデータに関連付けられたデータサブジェクトのIDをアドビに連絡する必要があります。 アドビは、データ処理者として、認められた要求を許容可能な時間内に処理するために、データ管理者に適切な支援を提供する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>アドビのお客様（データコントローラー）は、どのデータプライバシーリクエストがAdobe Analyticsのデータプライバシー処理のどのIDにマッピングされているかを、どのように判断しますか。</b> </p> </td> 
   <td colname="col2"> <p>データ管理者は、データ主体からの要求の ID を解決する方法を決めます。アドビのデータプ <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> ライバシーID取得タグの導入を検討しま </a>す。 開発チームは、Data Privacy ID取得タグを使用してユーザーID(cookie ID)を取得し、Data Privacy APIを使用してAdobe Experience cloudのデータプライバシーリクエスト処理の関連ソリューションにそれらのユーザーIDを送信することで、時間を節約できます。 </p> <p>Data Privacy APIは、複数のアドビソリューションにわたって、様々な顧客IDをサポートできます。 データの件名が識別子（カスタム変数 — propまたはeVar）と共にリクエストを送信した場合、Adobe Analyticsは、その識別子に対して収集されたデータの保持された履歴全体をスキャンします。 Analytics propまたはeVarに保存するカスタムIDの設定方法について詳しくは、[名前空間]のAnalyticsドキュメントを参照してください。](/help/admin/c-data-governance/gdpr-namespaces.md)
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analyticsのデータガバナンスは、データプライバシーリクエストの処理にどのように役立ちますか。</b> </p> </td> 
   <td colname="col2"> <p>データガバナンスは、データ管理者に Analytics データのデータ管理および分類機能を提供する、Adobe Analytics の新しいツールです。この新しいツールを使用すると、アドビのお客様は、データプライバシーデータアクセスおよびデータ削除リクエストの処理をカスタマイズできます。 データガバナンスコンソールでは、管理者は、Adobe Analytics に存在する様々なデータ列に適用する設定を定義できます。これらのラベルが定義されると、アドビは、お客様の希望するラベル設定に従って、任意のダウンストリームアクセス要求または削除要求に対応し、処理します。これらのラベル設定に関して、確認および法定代理人の助言を受けるのは、データ管理者の責任です。Adobe Analyticsは、GDPR発効日（2018年5月25日）の前に、データのラベル付けを正しく設定し、データプライバシーAPIを利用したリクエストの完了をカスタマイズできるようにすることを推奨します。 </p> <p>データガバナンスツールには、以下のデータラベルが含まれます。 </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_D7F4E4B60D6D40BEBC86B7004EF42AFF" format="dita" scope="local">ID データラベル</a>：直接または他のデータと組み合わせて個人を特定できるデータを分類するために使用されます（なし、I1、I2）。 </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_533E1406F3F24A01B51D94139B94CAEC" format="dita" scope="local">機密データラベル</a>：適用法の下で機密として定義される可能性のあるデータとしてデータを分類するために使用されます（なし、S1、S2）。現在の Adobe Analytics での機密データの使用は、適用法の下で適切に取得された正確な位置情報データ（一部の管轄地域で機密データ見なされることがあります）を除いて、通常、禁止されています。 </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_0C7F9EC4BB414A6D915C69F1D3259F1B" format="dita" scope="local"> データプライバシーデータラ </a>ベル：データプライバシーリクエストで使用する個人識別子を含むフィールドや、データプライバシー削除リクエストの一部として削除する必要があるフィールドを定義するために使用します。 これらのラベルは、場合によっては、ID および機密データラベルと重複する可能性があります。 </li> 
    </ul> <p>For more information on Data Governance labels, see <a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Data Privacy Labels for Analytics Variables </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analyticsでデータプライバシーの準備を始めるには、どこで手を貸しますか。</b> </p> </td> 
   <td colname="col2"> <p>データプライバシールールの準備に関する詳しい手順については、 <a href="../../admin/c-data-governance/an-gdpr-workflow.md#concept_1D1C0C1EAC3B4772AEDF5CC9F0EA604B" format="dita" scope="local"> Adobe Analyticsデータプライバシーワークフローを参照してくださ </a>い。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>ユーザーエンゲージメントに関して、データ管理者は同意についてどのように考えればよいですか？</b> </p> </td> 
   <td colname="col2"> <p>GDPRとCCPAは、同意が必要な時期を判断し、ユーザの価値提案について考えるなど、同意管理戦略と慣行を再検討する良い機会です。 消費者のプライバシーに対する価値提案を検討します。これは、コンバージョンおよび忠誠度を高めるのに役立ちます。 </p> <p>同意管理領域（例えば、ツール、標準、ベストプラクティス）は急速に進化している、注目すべき領域です。ユーザーエンゲージメントへの影響を最小限に抑えるには、管理者は、この領域でベンダーと連携し、助言を得て、同意と Cookie に関する新しい EU 法およびガイダンスに従います。データ収集活動の価値提案を提示する、ブランドに合った文脈的に関連のあるエクスペリエンスを使用することで、「経験的プライバシー」について考えることは、良い戦略です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>データのプライバシーに関して、データ保持に関してデータコントローラはどのように考えるべきですか。</b> </p> </td> 
   <td colname="col2"> <p>「データプライバシー」は、一般に、個人データを収集した目的を達成するために必要以上に長く保持すべきではないということを提供します。 </p> <p>アドビが 2 月のお客様とのコミュニケーションで説明したように、他の合意（顧客通知と認証が必要）がなされない限り、ほとんどのお客様に対して 25 ヶ月のデータ保持計画を適用します。お客様は、アドビがデータプライバシーリクエストを処理する前に、データ保持ポリシーを設定する必要があります。 </p> <p>Adobe Analyticsでは、データプライバシーリクエストを処理するために、データ保持期間の設定が必要です。 新しいデータガバナンス管理 UI には、各レポートスイートの現在のデータ保持ポリシーが表示されます。データ保持ポリシーを調整する必要がある場合は、アドビの担当窓口までご連絡ください。<a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Adobe Analytics データ保持の FAQ</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>お客様は、デフォルトのデータ保持期間を短縮または延長できますか？</b> </p> </td> 
   <td colname="col2"> <p>お客様は、カスタマーケアに問い合わせることで、25 ヶ月より前にデータを削除することを要求できます。お客様は、拡張機能を購入することで、25か月以上のデータ保持期間を延長できます。</p><p>
   年単位の延長は1回（1回）まで、年単位の延長は最大8回（合計10年）まで可能です。 これらの延長には、更新された契約条件および追加費用が必要になることがあります。
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics から個人データが書き出される際にデータ管理者が責任を負うプライバシーの考慮事項は何ですか？</b> </p> </td> 
   <td colname="col2"> <p>お客様が Adobe Analytics データフィードを使用して Analytics からエンタープライズデータウェアハウスまたはアドビ以外の他のシステムにデータを書き出す場合、削除要求がデータに適用されるのを確認することは、お客様（データ管理者）の責任です。また、これは、Adobe Data Workbench（Insight）のオンプレミス実装（進行中の Adobe Analytics データフィードが Data Workbench データに設定される）にも適用されます。アドビは、特定のタイプのデータフィード（Data Workbench で使用されるデータフィードを含む）からレコードを検索および削除するのを支援するツールを提供することがありますが、独自の内部データ保持および削除ポリシーに基づいてデータが削除されたことを確認するのは、依然としてお客様（データ管理者）の責任です。 </p> <p>また、従業員が個人データを含む Adobe Analytics レポートをダウンロードする可能性も考慮してください。レポートに存在するIDを含むデータプライバシー関連の削除リクエストを受け取った場合は、これらのレポートを更新または削除する必要があります。 お客様は、会社の法律顧問と連携して保持期間およびこれらのタイプのドキュメントに適用する必要のあるプライバシーおよびセキュリティ要件を決める必要があります。 </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b>収集するつもりのなかったデータが誤って Adobe Analytics に送信されてしまいました。データプライバシーAPIを使用してこのデータをクリーンアップできますか。</b> </p> </td><td colname="col2"> <p>データプライバシーAPIは、時間に依存するデータプライバシーリクエストを満たすのに役立つように提供されています。 他の目的でのこのAPIの使用は、アドビではサポートされていません。また、ユーザーが開始する、優先度の高いデータプライバシーリクエストを、アドビがタイムリーに回避する機能に影響を与える可能性があります。 データプライバシーAPIは、大量の訪問者グループに誤って送信されたデータの消去など、他の目的には使用しないでください。</p> <p>また、データプライバシー削除リクエストの結果、ヒットが削除（更新または匿名化）された訪問者は、その状態情報をリセットすることにも注意してください。 そのような訪問者が再び Web サイトを訪問した場合は、新規訪問者として扱われます。eVar の割り当ては最初からすべてやり直され、訪問回数、リファラー、最初に訪問したページなどの情報も最初から収集し直されます。この副作用は、データフィールドを消去し、データプライバシーAPIがこの使用に適していない理由の1つに焦点を当てる必要がある場合には望ましくありません。 </p> <p>PIIやデータの問題を取り除くためのさらなるレビューと作業レベルの提供を行うには、担当のアカウントマネージャー(CSM)にお問い合わせください。</p></td></tr> <tr> 
   <td colname="col1"> <p><b>特定の変数を使用して長年にわたって収集してきた値が最新のプライバシーポリシーに準拠していないとの指摘を法務チームから受けました。Can we use the Data Privacy API to clear out all values from this variable?</b> </p> </td><td colname="col2"> <p>データプライバシーAPIは、時間に依存するデータプライバシーリクエストを満たすのに役立つように提供されています。 他の目的でのこのAPIの使用は、アドビではサポートされていません。また、ユーザーが開始する、優先度の高いデータプライバシーリクエストを、アドビがタイムリーに回避する機能に影響を与える可能性があります。 データプライバシーAPIは、大量の訪問者グループに誤って送信されたデータの消去など、他の目的には使用しないでください。</p> <p>また、データプライバシー削除リクエストの結果、ヒットが削除（更新または匿名化）された訪問者は、その状態情報をリセットすることにも注意してください。 そのような訪問者が再び Web サイトを訪問した場合は、新規訪問者として扱われます。eVar の割り当ては最初からすべてやり直され、訪問回数、リファラー、最初に訪問したページなどの情報も最初から収集し直されます。この副作用は、データフィールドを消去し、データプライバシーAPIがこの使用に適していない理由の1つに焦点を当てる必要がある場合には望ましくありません。 </p> <p>PIIやデータの問題を取り除くためのさらなるレビューと作業レベルの提供を行うには、担当のアカウントマネージャー(CSM)にお問い合わせください。</p></td>
 </tbody> 
</table>

その他のデータプライバシーに関するリソース：

* [GDPR の一般用語](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience cloudデータプライバシーケアパ [ッケージ](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 経験的プライバシーに関する[ブログ投稿](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
