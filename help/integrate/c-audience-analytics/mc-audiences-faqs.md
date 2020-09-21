---
description: Audience Analytics を実装するときによくある質問への回答です。
solution: Experience Cloud
title: よくある質問
uuid: 9dfc8f19-f9b2-4c2e-bff9-3d91cfe01bca
translation-type: ht
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16
workflow-type: ht
source-wordcount: '1098'
ht-degree: 100%

---


# よくある質問

Audience Analytics を実装するときによくある質問への回答です。

## 法的事項についてよくある質問（FAQ） {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Q：Analytics データに個人情報（PII）が含まれているかどうかを把握するにはどうしますか。含まれている場合は、どうしたらいいですか。</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">prop または eVar に電子メール／アドレスなどを格納している場合は、収集時にデータをハッシュすることを検討します。 </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">お客様の国で IP アドレスが PII（個人情報）と見なされる場合は、<a href="https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/exclude-ip.html"  >IP の不明化を有効にします</a>。 </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">Analytics 管理者に問い合わせて、収集内容を確認します。 </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">社内の法務部に問い合わせて、PII と見なされる情報を確認します。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q：レポートスイートで、オンサイトでのパーソナライゼーションやオフサイト／オンサイトでのターゲティングを実行するかどうかを把握するにはどうしますか。</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">これらは、Adobe Audience Manager への Adobe Analytics データの送信には適用されません。 </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">自身で確認：MCA ディメンション付きの Analytics 共有セグメントを Experience Cloud で共有しますか。 </li> 
     <li id="li_C52D969681B94F4AAA18FDEB21EC5B49">これらの目的で使用するビジネスインテリジェンス（BI）システムに（データフィードなどを介して）エクスポートしますか。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## AAM 固有のよくある質問（FAQ）  {#section_6BDF746BA6464359A6A89A64EB025D12}

<table id="table_15B44592161240BDA79F3B020EA9CC9D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q：Audience Manager で Analytics の宛先を作成するにはどうすればよいですか。</b> </p> </td> 
   <td colname="col2"> <a href="https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html"  >AAM での Analytics の宛先の設定</a>を参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：Analytics の宛先を作成して保存した後、選択したレポートスイートにデータが表示されるまでにどれくらい時間がかかりますか。</b> </p> </td> 
   <td colname="col2"> <p>レポートスイートに新しいデータが入力されるまでに数時間かかることがあります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：新しい Analytics の宛先を作成しましたが、使用可能なセグメントの「Destination Mappings 」セクションに表示されません。作成した宛先はどこに行ったのでしょうか。どうしたら見つかりますか。</b> </p> </td> 
   <td colname="col2"> <p>「<span class="uicontrol">Segment Mappings</span>」で「<span class="uicontrol">Automatically map all current and future segments</span>」オプションを選択すると、Analytics の宛先はセグメントの「Destination Mappings」セクションに表示されなくなります。 </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>これを防ぐには、自動オプションの代わりに「<span class="uicontrol">Manually map segments</span>」を選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Q：Analytics では、AAM からすべての情報が提供されますか。</b> </p> </td> 
   <td colname="col2"> <p>いいえ。Audience Manager オーディエンスの有効化中または有効化後、およびセグメント認定中／認定後にサイトを訪問するユーザーに関連するデータのみ提供されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Q：セグメントあたりの、アドレス指定可能なオーディエンスの合計数は提供されますか。</b> </p> </td> 
   <td colname="col2"> <p>いいえ。セグメント認定中または認定後にサイトを訪れた、そのセグメントの訪問者数が提供されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Q：Analytics を宛先とする従来の cookie との違いは何ですか。</b> </p> </td> 
   <td colname="col2"> <p>セグメントは、同じヒットでリアルタイムに認定されて返されます。 </p> <p>わかりやすい名前が自動的に表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：個人データがあるレポートスイートと個人データがないレポートスイートがある場合はどうすればよいですか。</b> </p> </td> 
   <td colname="col2"> <p>ヒント：2 つの宛先を作成します。個人データレポートスイートを 1 つの宛先に追加し、個人データ以外のレポートスイートを別の宛先に追加します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Analytics 固有のよくある質問（FAQ）{#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q：この統合は、Analytics でディメンションまたはセグメントのどちらとして表示されますか。</b> </p> </td> 
   <td colname="col2"> <p>ディメンション（オーディエンス ID およびオーディエンス名）として表示されます。です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：これらのディメンションは Analytics のどこで使用できますか。</b> </p> </td> 
   <td colname="col2"> <p>ほとんどどこでも使用できます。これらのディメンションは Analytics で収集されたほかのディメンションと同様に扱われます。例外が 1 つあります。現時点では、Data Workbench にはデータは表示されません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：Analytics でデータが受信されないのはなぜですか。</b> </p> </td> 
   <td colname="col2"> <p>データソースと宛先の間に競合する AAM プライバシー制御がある可能性があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：すべてのセグメントを送信するように選択しましたが、一部のセグメントが Analytics で欠落しているのはなぜですか。</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">宛先とセグメントのデータソースの AAM データエクスポート制御が競合して、特定のセグメントが送信されていない可能性があります。 </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">セグメントでサードパーティのデータ特性を使用している場合、それらのセグメントは個人データを含む宛先（一連のレポートスイート）と共有できません。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：Analytics レポートに「オーディエンスの上限に達しました」と表示されるのはなぜですか。（注意：また、Data Warehouse では「Audience ID = -1」および「::max_audiences_exceeded:::」としても表示されます。</b> </p> </td> 
   <td colname="col2"> <p>デフォルトでは、AAM の Audience Analytics 統合は、訪問者が認定されたすべてのセグメントをヒットごとに Analytics に送信します。単一のヒットで訪問者が 150 を超える AAM セグメントに属している場合、<b>150 個の最近認定されたセグメント</b>が Analytics に送信され、残りのリストは切り捨てられます。 </p> <p>セグメントリストが切り捨てられたことを示す追加のフラグが Analytics に送信され、オーディエンス名ディメンションに「オーディエンスの制限に達しました」と表示され、オーディエンス ID ディメンションに「-1」が表示されます。 </p> <p>特定のヒットで訪問者が 150 を超えるセグメントに認定されることはあまりありませんが、まれに起こる可能性があります。レポートに「オーディエンスの制限に達しました」が表示される場合は、2 つの選択肢があります。 </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>選択肢 1</b>：統合を初期状態で使用し、特定の訪問者が最近認定された 150 個のセグメントを送信します。 </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>選択肢 2</b>：AAM で、その統合でビジネスに最も重要な 150 個のセグメントを選択します。AAM はそれらの 150 セグメントに対してのみ訪問者をチェックします。この手法の欠点は、すべての訪問者に対してこの 150 セグメントしか受け取れないことです。一方、1 の手法の場合、統合にはヒットごとの特性があるので、セグメントを無制限に送信できます。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：この統合の追加のサーバーコールは Analytics に請求されますか。</b> </p> </td> 
   <td colname="col2"> <p>いいえ。AAM オーディエンスは、サーバー側で Analytics ヒットに含められます。これは、Analytics（プライマリまたはセカンダリ）への追加のサーバーコールとなりません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## サーバー側転送（SSF）のよくある質問（FAQ）{#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q：従来の SSF が実装されている場合は、Analytics 管理に移動してレポートスイートの SSF を有効にする必要がありますか。</b> </p> </td> 
   <td colname="col2"> <p>はい。AAM の宛先の設定では、SSF が有効にされているレポートスイートのみが表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：Analytics 管理で特定のレポートスイートを SSF に対して有効にできないのはなぜですか。</b> </p> </td> 
   <td colname="col2"> <p>Experience Cloud 組織にマップされているスイートのみを有効にできます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

このトピックに関するその他の FAQ については、[サーバー側転送 FAQ](/help/admin/admin/c-server-side-forwarding/ssf-faq.md)を参照してください。

## 一般事項についてのよくある質問（FAQ） {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Q：Audience Manager と Analytics でセグメント訪問者のカウント数が異なるのはなぜですか。</b> </p> </td> 
   <td colname="col2"> <p>詳しくは、<a href="/help/integrate/c-audience-analytics/visitor-count-reconciliation.md"  >訪問者数の相違</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：AAM の「オーディエンス」と Analytics の「セグメント」の違いは何ですか。</b> </p> </td> 
   <td colname="col2"> <p>詳しくは、<a href="/help/integrate/c-audience-analytics/aam-analytics-segments.md"  > Analytics と Audience Manager のセグメントについて </a>を参照してください。 </p> <p>AAM オーディエンスは、Analytics で使用するために送信されて、「ディメンション」コンポーネントとして共有されます。これらはセグメントビルダーなどではセグメントとして表示されませんが、セグメントを作成できるディメンションとして表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：顧客属性と AAM から統合された顧客データの違いは何ですか。</b> </p> </td> 
   <td colname="col2"> <p>顧客属性は時間ベースではなく、過去や未来の時点に適用されます。AAM の統合データは時間ベースであり、未来の時点にのみ適用されます。また、顧客属性は Experience Cloud の訪問者 ID の参照テーブルであり、AAM 統合は訪問者の各ヒットにステッチされるデータです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q：この問題に対する従来の手法（古いベータ版、コンサルティングプラグインの cookie の宛先など）は使用できますか。</b> </p> </td> 
   <td colname="col2"> <p>新しい統合を実装して古い宛先を削除することを推奨します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

