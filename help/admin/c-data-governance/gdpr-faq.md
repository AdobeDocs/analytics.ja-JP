---
description: 'null'
seo-description: 'null'
seo-title: よくある質問
title: よくある質問
uuid: 1cd41253- d74f-4b92-92e6-56f9afa3df85
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
   <td colname="col1"> <p><b>Adobe Analyticsは、顧客（データコントローラー）によって検証されたエンドユーザー（データ項目）に対するアクセスおよび削除要求をどのようにサポートしますか。</b> </p> </td> 
   <td colname="col2"> <p>GDPR が発効すると、Adobe Analytics は、より自動化されたプロセスを可能にするために、データ管理者によって Experience Cloud GDPR API に送信された、認められた要求の処理をサポートします。アドビの GDPR API は、Adobe Experience Cloud ソリューションに保存されたお客様のデータに対する個人の権利に基づく要求（例えば、アクセス要求および削除要求）を処理するのを支援するように設計されています。データ主体から企業が受け取ったデータアクセスおよび削除要求の数に応じた柔軟性とスケーラビリティがあります。また、GDPR API を使用すると、お客様はどのようにデータアクセスおよび削除要求が実行されているかに関するステータスをチェックできます。 </p> <p>詳しくは、<a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external">GDPR API のドキュメント</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>エンドユーザーからGGPRリクエストを受信、受け入れ、およびfulfillにすると、</b> </p> </td> 
   <td colname="col2"> <p>データ管理者（つまりアドビの製品をご利用のお客様）は、GDPR の下での個人の権利に基づく要求に応じて、データ主体に個人データを提供することに単独で責任を負います。データコントローラーには、リクエストを受信し、リクエストを受け入れ、データサブジェクトのIDを検証してリクエストを承認することもあります。これにより、Adobe Analyticsに保存されたデータに関連するデータサブジェクトのIDを使用して、アドビに連絡することができます。アドビは、データ処理者として、認められた要求を許容可能な時間内に処理するために、データ管理者に適切な支援を提供する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>アドビの製品をご利用のお客様（データ管理者）が GDPR 処理のために Adobe Analytics でどの GDPR 要求をどの ID にマッピングしているかを調べるにはどうしたらよいですか？</b> </p> </td> 
   <td colname="col2"> <p>データ管理者は、データ主体からの要求の ID を解決する方法を決めます。Consider deploying <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> Adobe's GDPR ID Retrieval Tag </a>. 開発チームは、GDPR 要求を処理するためにアドビの GDPR ID 取得タグを使用してユーザー ID（Cookie ID）をキャプチャし、アドビの GDPR API を使用してそれらのユーザー ID を Adobe Experience Cloud の関連ソリューションに送信することで、時間を節約できます。 </p> <p>GDPR API は、複数の Adobe ソリューションにわたる様々な顧客 ID をサポートできます。データ件名がリクエストを識別子（カスタム変数- propまたはeVar）と共に送信した場合、Adobe Analyticsは、特定の識別子について収集されたデータの保持履歴全体をスキャンします。Analytics propまたはeVarに保存されているカスタムIDを設定する方法について詳しくは、[名前空間]（/help/admin/c- data- management/dgpr- namespace. md）のAnalyticsドキュメントを参照してください。
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics データガバナンスは、GDPR 要求の処理にどのように役立ちますか？</b> </p> </td> 
   <td colname="col2"> <p>データガバナンスは、データ管理者に Analytics データのデータ管理および分類機能を提供する、Adobe Analytics の新しいツールです。この新しいツールにより、アドビの製品をご利用のお客様は、GDPR データのアクセスおよび削除要求の処理をカスタマイズする権利が付与されます。データガバナンスコンソールでは、管理者は、Adobe Analytics に存在する様々なデータ列に適用する設定を定義できます。これらのラベルが定義されると、アドビは、お客様の希望するラベル設定に従って、任意のダウンストリームアクセス要求または削除要求に対応し、処理します。これらのラベル設定に関して、確認および法定代理人の助言を受けるのは、データ管理者の責任です。Adobe Analytics は、GDPR 発行日の 2018 年 5 月 25 日より前にデータラベルを正しく設定して、GDPR API を活用した要求の完了をカスタマイズすることをクライアントに促します。 </p> <p>データガバナンスツールには、以下のデータラベルが含まれます。 </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_D7F4E4B60D6D40BEBC86B7004EF42AFF" format="dita" scope="local">ID データラベル</a>：直接または他のデータと組み合わせて個人を特定できるデータを分類するために使用されます（なし、I1、I2）。 </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_533E1406F3F24A01B51D94139B94CAEC" format="dita" scope="local">機密データラベル</a>：適用法の下で機密として定義される可能性のあるデータとしてデータを分類するために使用されます（なし、S1、S2）。現在の Adobe Analytics での機密データの使用は、適用法の下で適切に取得された正確な位置情報データ（一部の管轄地域で機密データ見なされることがあります）を除いて、通常、禁止されています。 </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_0C7F9EC4BB414A6D915C69F1D3259F1B" format="dita" scope="local">GDPR データラベル</a>：GDPR 要求で使用する個人を特定できる識別子を含む可能性があるフィールドまたは GDPR 削除要求の一環として削除する必要があるフィールドを定義するために使用されます。これらのラベルは、場合によっては、ID および機密データラベルと重複する可能性があります。 </li> 
    </ul> <p>データガバナンスラベルについて詳しくは、<a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local">Analytics 変数用の GDPR ラベル</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics で GDPR に対応するには、何から始めればよいですか？</b> </p> </td> 
   <td colname="col2"> <p>GDPR に対応するための手順については、<a href="../../admin/c-data-governance/an-gdpr-workflow.md#concept_1D1C0C1EAC3B4772AEDF5CC9F0EA604B" format="dita" scope="local">Adobe Analytics GDPR ワークフロー</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>ユーザーエンゲージメントに関して、データ管理者は同意についてどのように考えればよいですか？</b> </p> </td> 
   <td colname="col2"> <p>GDPR は、同意が必要なタイミングの判断やユーザーへの価値提案を含め、同意管理戦略および習慣を再考する良い機会です。消費者のプライバシーに対する価値提案を検討します。これは、コンバージョンおよび忠誠度を高めるのに役立ちます。 </p> <p>同意管理領域（例えば、ツール、標準、ベストプラクティス）は急速に進化している、注目すべき領域です。ユーザーエンゲージメントへの影響を最小限に抑えるには、管理者は、この領域でベンダーと連携し、助言を得て、同意と Cookie に関する新しい EU 法およびガイダンスに従います。データ収集活動の価値提案を提示する、ブランドに合った文脈的に関連のあるエクスペリエンスを使用することで、「経験的プライバシー」について考えることは、良い戦略です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>GDPR に関して、データ管理者はデータ保持についてどのように考えればよいですか？</b> </p> </td> 
   <td colname="col2"> <p>GDPR は、通常、個人データは、収集された目的を達成するために必要な期間以上に保持しないということが規定されています。 </p> <p>アドビが 2 月のお客様とのコミュニケーションで説明したように、他の合意（顧客通知と認証が必要）がなされない限り、ほとんどのお客様に対して 25 ヶ月のデータ保持計画を適用します。お客様は、アドビが GDPR 要求を処理できるように、データ保持ポリシーを設定する必要があります。 </p> <p>Adobe Analytics では、お客様は GDPR 要求を処理するためのデータ保持を設定する必要があります。新しいデータガバナンス管理 UI には、各レポートスイートの現在のデータ保持ポリシーが表示されます。データ保持ポリシーを調整する必要がある場合は、アドビの担当窓口までご連絡ください。<a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Adobe Analytics データ保持の FAQ</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>お客様は、デフォルトのデータ保持期間を短縮または延長できますか？</b> </p> </td> 
   <td colname="col2"> <p>お客様は、カスタマーケアに問い合わせることで、25 ヶ月より前にデータを削除することを要求できます。拡張機能を購入することで、25か月を超えるデータ保持を顧客に提供することができます。</p><p>
   拡張子は、1年分（1年）の増分（1年あたりの最大8桁）（10年分の合計）まで使用できます。これらの延長には、更新された契約条件および追加費用が必要になることがあります。
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics から個人データが書き出される際にデータ管理者が責任を負うプライバシーの考慮事項は何ですか？</b> </p> </td> 
   <td colname="col2"> <p>お客様が Adobe Analytics データフィードを使用して Analytics からエンタープライズデータウェアハウスまたはアドビ以外の他のシステムにデータを書き出す場合、削除要求がデータに適用されるのを確認することは、お客様（データ管理者）の責任です。また、これは、Adobe Data Workbench（Insight）のオンプレミス実装（進行中の Adobe Analytics データフィードが Data Workbench データに設定される）にも適用されます。アドビは、特定のタイプのデータフィード（Data Workbench で使用されるデータフィードを含む）からレコードを検索および削除するのを支援するツールを提供することがありますが、独自の内部データ保持および削除ポリシーに基づいてデータが削除されたことを確認するのは、依然としてお客様（データ管理者）の責任です。 </p> <p>また、従業員が個人データを含む Adobe Analytics レポートをダウンロードする可能性も考慮してください。これらのレポートは、レポートに存在する可能性のある ID が関わる GDPR または他のプライバシー関連の削除要求を受け取った場合に、更新または削除される必要がある可能性があります。お客様は、会社の法律顧問と連携して保持期間およびこれらのタイプのドキュメントに適用する必要のあるプライバシーおよびセキュリティ要件を決める必要があります。 </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b>収集するつもりのなかったデータが誤って Adobe Analytics に送信されてしまいました。Can we use the GDPR API to cleanup this data?</b> </p> </td><td colname="col2"> <p>DGPR APIが提供され、DGPRリクエストの実行時に時間がかかります。この API をその他の目的に使用することはサポートされておらず、そのような利用はユーザーからの優先度の高い GDPR 要求をアドビの他のお客様のためにタイムリーに処理する能力に影響を及ぼす可能性があります。大規模な訪問者グループ全体にわたって間違って送信されたデータを消去するなど、本来の目的とは異なる用途に GDPR API を使用することは避けください。</p> <p>また、GDPR 削除要求の結果、ヒットが削除（更新または匿名化）された訪問者の状態情報はリセットされるということを認識しておく必要があります。そのような訪問者が再び Web サイトを訪問した場合は、新規訪問者として扱われます。eVar の割り当ては最初からすべてやり直され、訪問回数、リファラー、最初に訪問したページなどの情報も最初から収集し直されます。データフィールドを消去すると、このような望ましくない副次的効果が生じます。これは、GDPR API がそのような用途に適していない理由の 1 つでもあります。 </p> <p>PIIまたはデータの問題を削除するには、担当のエンジニアリングアーキテクトコンサルティングチームに連絡して、担当のエンジニアリングアーキテクトコンサルティングチームにお問い合わせください。</p></td></tr> <tr> 
   <td colname="col1"> <p><b>特定の変数を使用して長年にわたって収集してきた値が最新のプライバシーポリシーに準拠していないとの指摘を法務チームから受けました。その変数を通じて収集したすべての値を消去する目的に GDPR API を使用することはできますか？</b> </p> </td><td colname="col2"> <p>DGPR APIが提供され、DGPRリクエストの実行時に時間がかかります。この API をその他の目的に使用することはサポートされておらず、そのような利用はユーザーからの優先度の高い GDPR 要求をアドビの他のお客様のためにタイムリーに処理する能力に影響を及ぼす可能性があります。大規模な訪問者グループ全体にわたって間違って送信されたデータを消去するなど、本来の目的とは異なる用途に GDPR API を使用することは避けください。</p> <p>また、GDPR 削除要求の結果、ヒットが削除（更新または匿名化）された訪問者の状態情報はリセットされるということを認識しておく必要があります。そのような訪問者が再び Web サイトを訪問した場合は、新規訪問者として扱われます。eVar の割り当ては最初からすべてやり直され、訪問回数、リファラー、最初に訪問したページなどの情報も最初から収集し直されます。データフィールドを消去すると、このような望ましくない副次的効果が生じます。これは、GDPR API がそのような用途に適していない理由の 1 つでもあります。 </p> <p>PIIまたはデータの問題を削除するには、担当のエンジニアリングアーキテクトコンサルティングチームに連絡して、担当のエンジニアリングアーキテクトコンサルティングチームにお問い合わせください。</p></td>
 </tbody> 
</table>

その他の GDPR リソース：

* [GDPR の一般用語](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud GDPR [ケアパッケージ](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 経験的プライバシーに関する[ブログ投稿](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
