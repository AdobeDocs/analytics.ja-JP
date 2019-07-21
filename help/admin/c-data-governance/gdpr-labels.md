---
description: 'null'
seo-description: 'null'
seo-title: Analytics 変数用の GDPR ラベル
title: Analytics 変数用の GDPR ラベル
uuid: a37a1278-7a0d-4e14- ae35-43bc460e7d12
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Analytics 変数用の GDPR ラベル

## データにラベルを設定する理由{#section_A075CDF3AD0744BD8CEB41CE3FB7BFB3}

アドビ製品をご利用の多くのお客様は、GDPR 関連の法律をチェックし、GDPR に準拠するためにデータをどのように処理するかを決める法務チームを設けています。法律の解釈は企業によって異なり、希望するデータ処理設定もお客様によって異なります。GDPR のデータ処理方法とデータセットはお客様によって異なるので、アドビでは、データ管理者であるお客様が、自社の GDPR データの処理設定をカスタマイズできるようにしています。これにより、それぞれのお客様が、ブランドのニーズと保有するデータセットに最適な方法で GDPR 要求を処理できます。

計測データのプライバシー性と契約上の制限に従ってデータをラベルで分類するためのツールを提供開始します。ラベルは、（1）データ主体の識別、（2）アクセス要求に対応するデータの特定、（3）削除要求に対して削除する必要があるデータフィールドの識別をおこなう場合に重要かつ有用です。

どの変数やフィールドにどのラベルを適用するかを把握するためには、Analytics データから取得する [ID について理解](../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E)し、GDPR 要求でどのような ID を使用するかを決める必要があります。

Adobe Analytics の GDPR 実装では、識別データ、機密データ、データガバナンス用に以下のラベルを利用できます。

## DULE ラベル {#section_B2E78130957647338495EF37DE21D6BC}

>[!NOTE]
>
>データ使用状況のラベル&amp;実行（DB）フレームワークは、すべてのアドビソリューション/サービス/プラットフォームにわたって一貫性のある方法を提供し、Adobe Experience Cloud全体でデータに関するメタデータを取得、通信および使用するように設計されています。データ管理者はこのメタデータを利用して、どのデータが個人情報や機密情報に該当するかを指定したり、契約上のどの制限事項がデータと関連しているかを指定したりできます。この初期リリースでは、Analytics は、GDPR に関連する DULE ラベルのみを公開しています。他のアドビ製品が DULE ラベルのサポートを実装するのに伴い、将来のリリースでは、追加の機密データラベルに加えて契約のラベルが導入されます。これは、製品間で共有されたデータが法的に許容される方法でのみ使用されることを保証するのに役立ちます。

## 識別データラベル（DULE） {#section_D7F4E4B60D6D40BEBC86B7004EF42AFF}

識別データの「I」ラベルは、個人を特定できるデータまたは個人に連絡できるデータの分類に使用されます。

<table id="table_6B5368D714424E52835D5DFE189BD080"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ラベル </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> その他の要件 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>I1 </p> </td> 
   <td colname="col2"> <p><b>個人を直接的に特定可能</b>：名前や電子メールアドレスなど、個人を特定できるデータまたは個人に直接連絡できるデータ。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_4E2AD59D119E40D28B869D0BB63B9FD9"> 
     <li id="li_AC3E99B57E3A4AE2A12BE219680AFC58">イベントには設定できません。 </li> 
     <li id="li_BB66992863C8402F8D58656293F31E71">マーチャンダイジング eVar には設定できません。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I2 </p> </td> 
   <td colname="col2"> <p><b>個人を間接的に特定可能</b>：他のデータと組み合わせることで、個人やデバイスを特定できるデータまたは個人やデバイスに連絡できるデータ。 </p> <p>単独では個人を特定することはできないものの、他の情報（自分が所有しているものとそうでないものを含む）と組み合わせることで個人を特定できる ID。例えば、顧客のロイヤルティ番号や、企業の CRM システムで使用される顧客ごとの一意の ID などが該当します。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A0EF0F3DC5804D4FBE228946D697ABEB"> 
     <li id="li_A592EA6DA82C4D8C80E03F02ADF4E20E">イベントには設定できません。 </li> 
     <li id="li_46CE7B1E84884CDAB356A6DF89397849">マーチャンダイジング eVar には設定できません。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 機密データラベル（DULE） {#section_533E1406F3F24A01B51D94139B94CAEC}

機密データの「S」ラベルは、地理データなどの機密データの分類に使用されます。将来的に、他のタイプの機密情報を特定するために、追加の機密データラベルが導入される予定です。

<table id="table_A778A508620545CCB37830E5CF1C75B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ラベル </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>S1 </p> </td> 
   <td colname="col2"> <p> 緯度と経度に関連する正確な位置情報データ。デバイスの正確な位置（誤差 100 m以内）の特定に使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>S2 </p> </td> 
   <td colname="col2"> <p> 広義の地域境界エリアの特定に使用できる位置情報データ。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## データガバナンスラベル（GDPR） {#section_0C7F9EC4BB414A6D915C69F1D3259F1B}

データガバナンスラベルを使用すると、規制や企業のポリシーに準拠するためにプライバシー関連の注意事項や契約条件を反映したデータを分類できます。

**GDPR アクセスラベル**

<table id="table_663EFF43A454498386F7F3E60875E0F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ラベル </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> その他の要件 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>なし </p> </td> 
   <td colname="col2"> <p>この変数が、GDPR アクセス要求の一環としてデータ主体に返されたデータに含まれている必要があるデータを含んでいない場合に、このオプションを選択します。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-ALL </p> </td> 
   <td colname="col2"> <p>このフィールドの値は、<u>すべての</u> GDPR アクセス要求に含める必要があります。 </p> <p>このヒットの発生源が複数のユーザーが共有するデバイスの場合に、データ管理者であるお客様がこのラベルを適用すると、その共有デバイスへのアクセス権を持つすべてのユーザー間でこのフィールドのデータを共有することを許可したことになります。 </p> </td> 
   <td colname="col3"> <p>このラベルが設定されたフィールドは、すべての GDPR 要求で返されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-PERSON </p> </td> 
   <td colname="col2"> <p> このフィールドの値は、ID-PERSON フィールドの値と一致する GDPR 要求 ID を基に、ヒットの発生源がデータ主体であると合理的に判断できる場合のみ、GDPR アクセス要求に含める必要があります。 </p> </td> 
   <td colname="col3"> <p>また、このレポートスイート内の何らかの変数に対して ID-PERSON ラベルを設定する必要があり、その ID を使用して要求を送信する必要があります。そうでない場合、このラベルは適用されません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

ほとんどの変数は他のラベルを受け取りませんが、アクセスラベルが多くの変数に適用されることが期待されます。ただし、自社の法務チームと相談し、収集したデータのうちどれをデータ主体と共有するかを決めるのは、お客様次第です。

**GDPR 削除ラベル**

<table id="table_59DFCE4D90214CB5972BDDE5B7391B4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ラベル </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> その他の要件 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>他のラベルとは異なり、これらの削除ラベルは相互に排他的ではありません。どちらか、両方、なしを選択できます。どちらの削除オプションもチェックしないことで「なし」という状態が示されるので、個別の「なし」ラベルは不要です。 </p> </td> 
   <td colname="col3"> <p>削除ラベルは、データ主体と関連付けられるヒットを許可する（つまり、データ主体の ID を許可する）値を含むフィールドに対してのみ必要です。 </p> <p> 他の個人情報（お気に入り、閲覧／購入履歴、健康状態など）は、データ主体との関連付けがなくなるので、削除する必要はありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-DEVICE </p> </td> 
   <td colname="col2"> <p>GDPR 削除要求では、このフィールドの値は、指定された ID-DEVICE がヒットに含まれる要求でのみ匿名化する必要があります。 </p> <p>同じ値が他のヒットで発生し、削除されない場合は、それらの値は変更されません。そのため、このフィールドのユニークカウント数を算出するレポートで、カウント数が変わります。共有デバイスでは、これによってデータ主体だけでなく、他のユーザーの ID が削除される場合があります。 </p> <p>このフィールドに ID-DEVICE ラベルも設定されており、このフィールドの値が GDPR 要求で ID として使用されていた場合は、カウント数は変わりません。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_45C3A09E1F05492B97C3F3DEA7C78FBC"> 
     <li id="li_BAB277F92F284ADE9D7B6839BDD716E2">I1、I2 または S1 ラベルも必要です。 </li> 
     <li id="li_6DDFC0571457489CBA9D76F547247F20">イベントには設定できません。 </li> 
     <li id="li_E79C6DFC6C58478EAA1504E3820D512C">マーチャンダイジング eVar には設定できません。 </li> 
     <li id="li_B78E273212E447D49D0707E174B66DEC">分類には設定できません。 </li> 
     <li id="li_F0F52D0DE7454557A6A97063C1FBC372">ID-DEVICE を使用して要求を送信するか、expandIDs を true に設定する必要があります。そうでない場合、このラベルは適用されません。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-PERSON </p> </td> 
   <td colname="col2"> <p>GDPR 削除要求では、このフィールドの値は、指定された ID-PERSON がヒットに含まれる要求でのみ匿名化する必要があります。 </p> <p>同じ値が他のヒットで発生し、削除されない場合は、それらの値は変更されません。そのため、このフィールドのユニークカウント数を算出するレポートで、カウント数が変わります。このフィールドに ID-PERSON ラベルも設定されており、値が GDPR 要求で ID として使用されていた場合は、カウント数は変更されません。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_6722E42E036E47B4B5E17DC213636D51"> 
     <li id="li_6C1A64FF68AF428A827D8C6C33E22970">I1、I2 または S1 ラベルも必要です。 </li> 
     <li id="li_8053533FFE874EE795C8B6043A4F73B3">イベントには設定できません。 </li> 
     <li id="li_D6700CF4D03E44DDA83C4DDBB5B70CC3">マーチャンダイジング eVar には設定できません。 </li> 
     <li id="li_B6C2B15484B344889DBF29B62E2EA8FD">分類には設定できません。 </li> 
     <li id="li_3BBD0C27D9644C2B9618457A0BFC15EF">また、このレポートスイート内の何らかの変数に対して ID-PERSON ラベルを設定する必要があり、その ID を使用して要求を送信する必要があります。そうでない場合、このラベルは適用されません。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**GDPR ID ラベル**

<table id="table_F6BBC868457443A19A7B693BD6C55B4B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ラベル </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> その他の要件 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>なし </p> </td> 
   <td colname="col2"> <p>この変数には GDPR 要求に使用される ID が含まれていません </p> </td> 
   <td colname="col3"> <p>このフィールドに、GDPR API または UI でアクセス要求または削除要求を送信する際に使用する ID が含まれている場合にのみ、他のラベルのどちらかを設定する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-DEVICE </p> </td> 
   <td colname="col2"> <p>このフィールドには、GDPR 要求のデバイスを識別するために使用できる ID が含まれていますが、共有デバイスの個々のユーザーを区別することはできません。 </p> <p>ID を含むすべての変数にこのラベルを指定する必要はありません（このために I1／I2 ラベルがあります）。この変数に保存された ID を使用して GDPR 要求を送信し、特定の ID についてこの変数を検索したい場合に、このラベルを使用します。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_618019CB8FCA4A5C94C47636240197B2"> 
     <li id="li_0E5ADED36FF24A348FDD434E2CC8C8EE">I1 または I2 ラベルも必要です。 </li> 
     <li id="li_20BCFF07B2BF468C8E0D477C10B2EF9F">イベントには設定できません。 </li> 
     <li id="li_0BD73EEF4184475D8E97878CF8DBEB90">マーチャンダイジング eVar には設定できません。 </li> 
     <li id="li_129851035C4A4BF0922296B4C3BEE39B">分類には設定できません。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-PERSON </p> </td> 
   <td colname="col2"> <p>このフィールドには、GDPR 要求で認証済みユーザー（特定のユーザー）の識別に使用できる ID が含まれています。 </p> <p>ID を含むすべての変数にこのラベルを指定する必要はありません（このために I1／I2 ラベルがあります）。この変数に保存された ID を使用して GDPR 要求を送信し、指定された ID についてこの変数を検索したい場合に、このラベルを使用します。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_0C7EEC8FCB5C4BCDA5D48F3C98770A67"> 
     <li id="li_2E781AE8D7A046A7996C7300CA854B86">I1 または I2 ラベルも必要です。 </li> 
     <li id="li_EB4C6430C218405DAAE81DEE010DCAA2">イベントには設定できません。 </li> 
     <li id="li_05AA67B45974474F9DA520E8B877BA11">マーチャンダイジング eVar には設定できません。 </li> 
     <li id="li_8A6BF4B40ED249289EAD46FE1C755FB0">分類には設定できません。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 変数を ID-DEVICE または ID-PERSON としてラベル設定する際の名前空間の提供 {#section_F0A47AF8DA384A26BD56032D0ABFD2D7}

変数を ID-DEVICE または ID-PERSON としてラベル設定する場合、名前空間を提供するよう指示されます。以前定義した名前空間を使用することも、新しい名前空間を定義することもできます。

**以前定義した名前空間の使用**

以前、ログイン会社の任意のレポートスイートの他の変数に ID ラベルを割り当てている場合、これらの既存の名前空間の 1 つを選択できます。名前空間で既にラベル付けされている他の変数と同じタイプの ID がこの変数に含まれている場合、また要求を送信する際に、それらの ID をすべて検索する必要がある場合、その名前空間を再利用してください。

1. 「**[!UICONTROL 名前空間を選択]」をクリックして、既存の名前空間の 1 つを選択します。**
1. Click **[!UICONTROL Apply]**.

![](assets/namespace.png)

**新しい名前空間の定義**

また、新しい名前空間を定義することもできます。名前空間文字列は、英数字、アンダースコア、ダッシュおよびスペースに制限することをお勧めします。すべて小文字に変換されます。

1. 「**[!UICONTROL 名前空間を選択]」をクリックして、名前空間のタイトルを入力します。**

   ![](assets/namespace2.png)

1. **[!UICONTROL Enter]キーを押してこの名前空間を追加します。**&#x200B;これで「適用」ボタンがアクティブになります。
1. Click **[!UICONTROL Apply]**.

名前空間として指定した文字列は、GDPR API で要求を「名前空間」パラメーターの値として送信する際に使用する必要がある文字列と同じです。この要求により、Adobe Analytics は、要求で指定した ID について、この名前空間を共有するすべてのレポートスイートのすべての変数を検索します。

ID を含むすべての変数に ID-DEVICE ラベルまたは ID-PERSON ラベルを指定する必要はありません（このために I1／I2 ラベルがあります）。この変数に保存された ID を使用して GDPR 要求を送信し、特定の ID についてこの変数を検索したい場合に、このラベルを使用します。例えば、eVar1 に電子メールアドレスを、eVar2 にログインユーザー名を含むことができるが、ユーザー名のみを使用して要求を送信する場合、eVar1 には I1、ACC-PERSON、DEL-PERSON とラベル設定しますが、eVar2 は名前空間「ユーザー名」と共に、I2、ACC-PERSON、DEL-PERSON、ID-PERSON とラベル設定します。次に、以下のようにユーザーセクション JSON ブロックを使用して要求を送信します。

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

同じレポートスイート内の異なる変数に同じ名前空間を使用することもできます。例えば、一部のカスタム実装は、prop と eVar の両方に CRM-ID を保存します。CRM-ID が常にこれらのどちらか一方（例えば eVar）にあり、他方（prop）にあるのはまれであり、eVar にない場合は prop にもない場合、eVar だけで ID を検索できるので、ID ラベルおよび名前空間が必要なのは eVar のみとなります。ただし、CRM-ID が一方の変数にあることも、もう一方の変数にあることもある場合、両方が同じ名前空間を持つ必要があり、アドビは、この名前空間を持つ、GDPR 要求の一環として指定した ID について、両方の変数を検索します。それでも、これらのすべての変数に対して DEL ラベルを設定する必要があります。それにより、どこで出現しても値が匿名化されます。

別の例として、eVar1 を使用して送信されることも、prop7 を使用して送信されることもある CRM ID があるとします。また、eVar1 から eVar3（存在する場合）に値をコピーする処理ルールがあります。そうでない場合は、prop7 から eVar3 に値をコピーします。このシナリオでは、CRM ID がわかっている場合、必ずそれが eVar3 に格納されるので、ID-PERSON ラベルが必要なのは eVar3 のみとなります。

## 変数のタイプとそれぞれが対応している GDPR／DULE ラベル {#section_CE7C3EDE1344466A98BC45E394B40762}

GDPR／DULE のラベル設定は、Analytics 変数の 4 つの主要クラスに影響します。すべての変数ですべてのラベルを利用できるわけではありません。以下の表には、各変数で利用できるラベルと利用できないラベルがまとめられています。

<table id="table_95D4416B3A8A40C28B2610D0003456E6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数の種類 </th> 
   <th colname="col2" class="entry"> 利用できるラベル </th> 
   <th colname="col3" class="entry"> 利用できないラベル </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_0615B545A5AD43F2A6F25698A47AAD3E"> 
     <li id="li_A4B3E8E241B149C99F2A71B21227AD72">カスタム成功イベント </li> 
     <li id="li_8AEF688AE9B8426C82D199E4B195330D">マーチャンダイジング eVar </li> 
     <li id="li_DFFCA65DCC6146AEB6D47476B4D4CC3B">複数値の変数（mvVar） </li> 
     <li id="li_3192D08B12C249D1AAA8AAEEDE2FD7D7">階層変数 </li> 
    </ul> </td> 
   <td colname="col2"> <p>S1／S2 </p> <p>ACC-ALL、ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1／I2 </p> <p>ID-DEVICE、ID-PERSON </p> <p>DEL-DEVICE、DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>分類 </p> </td> 
   <td colname="col2"> <p>I1／I2、S1／S2 </p> <p>ACC-ALL、ACC-PERSON、 </p> </td> 
   <td colname="col3"> <p>ID-DEVICE、ID-PERSON </p> <p>DEL-DEVICE、DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_1C2FD4D606664965A88F10818E1C11A9"> 
     <li id="li_590975F5C7304317B22C80B20718E914">トラフィック変数（prop） </li> 
     <li id="li_6E614B7036994434BFDA71A4424529A0">コマース変数（非マーチャンダイジング eVar） </li> 
    </ul> </td> 
   <td colname="col2"> <p>すべてのラベル </p> </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>その他のほとんどの変数 </p> <p><i>（例外は以下の表を参照）</i> </p> </td> 
   <td colname="col2"> <p>ACC-ALL、ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1／I2、S1／S2 </p> <p>ID-DEVICE、ID-PERSON </p> <p>DEL-DEVICE、DEL-PERSON </p> </td> 
  </tr> 
 </tbody> 
</table>

## ACC-ALL／ACC-PERSON 以外のラベルを割り当てる／変更することができる変数 {#section_4FA003003D1B4E2EBCFCDB1A7CD4A824}

<table id="table_0972910DB2D7473588F23EA47988381D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> グループ </th> 
   <th colname="col2" class="entry"> 変数 </th> 
   <th colname="col3" class="entry"> 変更可能なラベル </th> 
   <th colname="col4" class="entry"> コメント </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_62FA1BAA3B9245909509566D8C03F900"> 
     <li id="li_38F7C4E18ECB42C292370713F502B8EB">コンバージョンディメンション </li> 
     <li id="li_41CB61F927CB4402AAB4A62E219CD153">カスタムトラフィックディメンション </li> 
    </ul> </td> 
   <td colname="col2"> <p>分類を除くすべて </p> </td> 
   <td colname="col3"> <p>すべて </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>分類 </p> </td> 
   <td colname="col3"> <p>なし／I1／I2 </p> <p>なし／S1／S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンバージョンイベント </p> </td> 
   <td colname="col2"> <p>すべて </p> </td> 
   <td colname="col3"> <p>なし／S1／S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ソリューションのディメンションとイベント </p> </td> 
   <td colname="col2"> <p>Activity Map リンク、 </p> <p>Activity Map ページ </p> </td> 
   <td colname="col3"> <p>なし／I1／I2 </p> <p>なし／DEL-DEVICE／DEL-PERSON </p> </td> 
   <td colname="col4"> <p>変数に、個人を直接的または間接的に特定できるデータを含む URL パラメーターが追加される場合があります。これらの変数で個人を直接的または間接的に特定できるデータを収集しない実装の場合は、識別ラベルおよび削除ラベルは不要です。 </p> <p>削除によって URL パラメーターはクリアされますが、元の URL は保持されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>データ処理ディメンション </p> </td> 
   <td colname="col2"> <p>カスタム訪問者 ID </p> </td> 
   <td colname="col3"> <p>ID-DEVICE／ID-PERSON </p> <p>DEL-DEVICE／DEL-PERSON </p> </td> 
   <td colname="col4"> <p>IDまたはYOBラベル（「なし」に設定）を削除することはできませんが、カスタムID実装に応じて、デバイスまたは人物のバリエーションを変更することができます。 </p> <p>カスタム訪問者 ID を使用しない場合、設定は関係ありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">標準のディメンション </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">データ処理ディメンション </li> 
    </ul> </td> 
   <td colname="col2"> <p>IP アドレス </p> <p>IP アドレス 2 </p> </td> 
   <td colname="col3"> <p>DEL-DEVICE／DEL-PERSON </p> </td> 
   <td colname="col4"> <p>DEL ラベルを削除することはできませんが、DEL-DEVICE または DEL-PERSON、または両方に変更できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ClickMap アクション（従来）、 </p> <p>ClickMap コンテキスト（従来）、 </p> <p>ページ、 </p> <p>ページ URL、 </p> <p>オリジナルエントリページ URL、 </p> <p>リファラー、 </p> <p>訪問開始ページ URL </p> </td> 
   <td colname="col3"> <p>なし／I1／I2 </p> <p>なし／DEL-DEVICE／DEL-PERSON </p> </td> 
   <td colname="col4"> <p>変数に、個人を直接的または間接的に特定できるデータを含む URL パラメーターが追加される場合があります。これらの変数で個人を直接的または間接的に特定できるデータを収集しない実装の場合は、識別ラベルおよび削除ラベルは不要です。 </p> <p>削除によって URL パラメーターはクリアされますが、元の URL は保持されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 削除処理 {#section_F3DEE591671A4B16A8E043F91C137ECB}

Adobe Analytics での GDPR 削除要求は、レポートへの影響を最小限に抑えるように設計されています。ほとんどの場合、レポートに表示される指標は変わりません。GDPR 削除の前に実行された履歴レポートは、削除の後に実行された同じレポートと一致します。これは、削除されたデータをデータ主体から完全に切り離し、個人を特定できないデータを保持してレポートの値の一貫性を保つことで実現されます。

次の表に、様々な変数の「削除」方法を示します。ここでは一部のみをリストしています。

<table id="table_A329C2E2645F4685BC208826D070A5F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 削除方法 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>• トラフィック変数（prop） </p> <p>• コマース変数（eVar） </p> </td> 
   <td colname="col2"> <p>既存の値は、「GDPR-356396D55C4F9C7AB3FBB2F2FA223482」という形の新しい値で置き換えられます。ここで、「GDPR-」プレフィックスの後の 32 桁の 16 進数値は、暗号として強固な 128 bit 疑似乱数です。基本的にランダムな文字列で置き換えられるので、この新しい値から元の値を判別する方法はなく、新しい値をたどって元の値を知ることはできません。 </p> <p>特定の変数について、置き換えられる値と同一の値が、同じ GDPR 要求の一部として削除される他のヒット内に存在する場合、その値のすべてのインスタンスが同じ新しい値に置き換えられます。 </p> <p>値の一部のインスタンスがある削除要求で置き換えられる場合で、後の要求が元の値の他の（新しい）インスタンスを削除する場合、新しく置き換えられる値は、元の置き換えられる値とは違うものになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>購入 ID </p> </td> 
   <td colname="col2"> <p>既存の値は、「G-7588FCD8642718EC50」という形の新しい値で置き換えられます。ここで、「G-」プレフィックスの後の 18 桁の 16 進数は、暗号として強固な 128 bit 疑似乱数の最初の 18 桁です。トラフィックおよびコマース変数の削除に適用されるすべてのコメントは、ここにも適用されます。 </p> <p>購入 ID はトランザクション ID で、購入確認ページの表示を更新する場合など、購入の二重処理がおこなわれていないことを確認することが主な目的です。ID 自体は、購入が記録される独自の DB 内の行に購入を関連付けている場合があります。ほとんどの場合、この ID を削除する必要はないので、デフォルトでは削除されません。独自のデータの GDPR 削除要求の後でもまだ購入をユーザーに関連付けできる場合、この訪問者の Analytics データを購入者に関連付けできないように、このフィールドを削除する必要がある場合があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪問者 ID </p> </td> 
   <td colname="col2"> <p>値は、128 bit 整数で、暗号として強固な 128 bit 疑似乱数値に置き換わります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• MCID </p> <p>• カスタム訪問者 ID </p> <p>• IP アドレス </p> <p>• IP アドレス 2 </p> </td> 
   <td colname="col2"> <p>値はクリアされます（変数のタイプに応じて、空の文字列または 0 に設定されます）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• ClickMap アクション（従来） </p> <p>• ClickMap コンテキスト（従来） </p> <p>• ページ </p> <p>• ページ URL </p> <p>• オリジナルエントリページ URL </p> <p>• リファラー </p> <p>• 訪問開始ページ URL </p> </td> 
   <td colname="col2"> <p>URL パラメーターはクリアまたは削除されます。この値が URL のように見えない場合、値はクリアされます（空の文字列に設定されます）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• 緯度 </p> <p>• 経度 </p> </td> 
   <td colname="col2"> <p>精度は低下して 1 km よりも悪くなります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 定められた削除ラベルをサポートしない変数 {#section_956B766EFFEC427E87E6CFF3A4217E86}

ここでは、削除に対応していない Analytics 変数について説明します。これらの変数は、変数に含まれているデータのタイプを理解しておらず、変数の名前に基づいて不適切な判断をしかねない Analytics 以外のユーザー（法務チームなど）によって削除されてしまう可能性があります。ここでは、これらの変数の一部をリストします。また、削除が不要な理由や、特定の削除ラベルを必要としない理由も示します。

<table id="table_6FECF3D654514862912D371E6BE4143B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> コメント </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>新規訪問者 ID </p> </td> 
   <td colname="col2"> <p>新規訪問者 ID はブール値で、特定の訪問者 ID が初めて表示されるときに true になります。訪問者 ID は一度匿名化されたら、削除する必要はありません。匿名化の後は、匿名化された ID が初めて表示されたときの状態に対応します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>郵便番号 </p> <p>位置情報の郵便番号 </p> </td> 
   <td colname="col2"> <p>郵便番号は、米国で生成されたヒットの場合にのみ設定されます。EU で生成されたヒットには設定されません。設定された場合でも、データ主体の再特定が困難な広範囲の地域のみが提供されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>位置情報の緯度 </p> <p>位置情報の経度 </p> </td> 
   <td colname="col2"> <p>これらは、IP アドレスから得られる大まかな位置を提供します。精度は通常、郵便番号と同様で、実際の位置から数十 km 以内です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザーエージェント </p> </td> 
   <td colname="col2"> <p>ユーザーエージェントは、使用されたブラウザーのバージョンを識別します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー ID </p> </td> 
   <td colname="col2"> <p> データが含まれる Analytics レポートスイート（番号）を指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートスイート ID </p> </td> 
   <td colname="col2"> <p> データが含まれる Analytics レポートスイートの名前を指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪問者 ID </p> <p>MCID／ECID </p> </td> 
   <td colname="col2"> <p> これらには DEL-DEVICE ラベルが設定されていますが、DEL-PERSON ラベルを追加することはできません。各要求で<a href="../../admin/c-data-governance/gdpr-id-expansion.md#concept_917A5666010A4E6BA599FE372DADD1BD" format="dita" scope="local"> ID 拡張</a>を指定した場合、ID-PERSON を使用している要求も含め、すべての削除要求に対して、これらの ID が自動的に削除されます。 </p> <p>ID 拡張を使用しないが、一致する ID が prop または eVar に含まれているヒットでこれらの Cookie ID を匿名化したい場合は、実際にユーザーを特定できる場合でも、prop または eVar に ID-DEVICE ラベルを設定することで、このラベル設定の制限を回避できます（すべての DEL-PERSON ラベルを DEL-DEVICE ラベルに変更する必要があります）。この場合、訪問者 ID または ECID の一部のインスタンスのみが匿名化されるので、履歴レポートでは個別訪問者数が変更されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ID </p> </td> 
   <td colname="col2"> <p> Adobe Advertising Cloud IDは、変更できないK- DEVICEラベルを持つソリューション変数です。これは、訪問者 ID や MCID と同様に、Cookie から値が入力されます。これは、他の ID が削除されるたびに、ヒットから削除される必要があります。詳細については、それらの変数の説明を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## アクセス要求のデータフィールド {#section_6678FB4FF42B481C9B78E64F61782397}

5 つのタイムスタンプを含む標準変数があります。

<table id="table_49A9255366254F799E1682C30CBD98EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タイムスタンプ </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ヒット時刻 (UTC) </p> </td> 
   <td colname="col2"> <p>Adobe Analytics がヒットを受信した時刻。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタムヒット時刻 (UTC) </p> </td> 
   <td colname="col2"> <p>ヒットが発生した時刻。一部のモバイルアプリおよびその他の実装では、受信した時刻よりも早い可能性があります。例えば、発生時にネットワーク接続が利用できなかった場合、アプリはヒットを保持し、接続が利用できるようになったら送信します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日時 </p> </td> 
   <td colname="col2"> <p>「カスタムヒット時刻 (UTC)」と同じ値ですが、GMT ではなく、レポートスイートのタイムゾーンです。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>初回ヒット時刻 (GMT) </p> </td> 
   <td colname="col2"> <p>このヒットの訪問者 ID 値に対して受信した初回ヒットの「カスタムヒット時刻 (UTC)」の値。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪問開始時刻 (UTC) </p> </td> 
   <td colname="col2"> <p>この訪問者 ID の現在の値に対して受信した初回ヒットの「カスタムヒット時刻 (UTC)」の値。</p> </td> 
  </tr> 
 </tbody> 
</table>

GDPR アクセス要求用に返されたファイルを生成するコードでは、少なくとも最初の 3 つのタイムスタンプ変数のいずれかがアクセス要求に含まれている（この要求のタイプに適用する ACC ラベルを持つ）必要があります。これらがいずれも含まれていない場合、「カスタムヒット時刻 (UTC)」が ACC-ALL ラベルを持つかのように扱われます。

GDPR アクセス要求用に返されたヒットレベル CSV ファイルは、これらのフィールドの値を Unix タイムスタンプから YYYY-MM-DD HH:MM:SS 形式（例：2018-05-01 13:49:22）の日付／時刻フィールドに変換します。概要 HTML ファイルでは、これらのタイムスタンプ値は、日付 YYYY-MM-DD のみを含むように切り捨てられて、これらのフィールド用に発生する一意の値の数を減らします。
