---
description: '送信する ID では、Analytics でデータ主体に関連付けることができるヒットデータの一部をカバーできない場合もあります。Analytics では、ID のセットを拡張し、関連付けられているデータを GDPR 要求に含めることができます。このオプションは、送信する各DGPRリクエストへのオプションのパラメーターで、JSONリクエストに追加できます '
seo-description: '送信する ID では、Analytics でデータ主体に関連付けることができるヒットデータの一部をカバーできない場合もあります。Analytics では、ID のセットを拡張し、関連付けられているデータを GDPR 要求に含めることができます。このオプションは、送信する各DGPRリクエストへのオプションのパラメーターで、JSONリクエストに追加できます '
seo-title: ID 拡張
title: ID 拡張
uuid: 2672d17d- c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# ID 拡張 #

送信する ID では、Analytics でデータ主体に関連付けることができるヒットデータの一部をカバーできない場合もあります。Analytics では、ID のセットを拡張し、関連付けられているデータを GDPR 要求に含めることができます。このオプションを要求するには、送信する各 GDPR 要求に対するオプションのパラメーターを JSON 要求に追加します。

```
"expandIds": true
```

このオプションを要求に含める方法の例については、[サンプルの JSON 要求](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_DB9DE6492FE740918F91D413E7BAB88F)を参照してください。詳しくは、[GDPR API のドキュメント](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)を参照してください。

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タイプ </th> 
   <th colname="col2" class="entry"> 注意点 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID の拡張 </p> </td> 
   <td colname="col2"> <p>Many Analytics customers originally used the (Legacy) <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external"> Analytics Cookie </a>, but are now using the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service (ECID) </a>, previously known as the Marketing Cloud ID Service (MCID). 移行後に、こうしたお客様の Web サイトを初めて訪問したユーザーの場合は、ECID のみが使用されます。ただし、従来の Cookie しか利用できなかった時期に Web サイトを初めて訪問し、それ以降も訪問し続けているユーザーの場合は、一部のデータで両方の Cookie が使用され、古いデータでは Analytics Cookie のみ、最新のデータでは稀に ECID のみが使用される場合もあります。 </p> <p>Analytics（訪問者 ID）Cookie または ECID で識別された 1 人の訪問者に関するすべてのデータが確実に検出される必要があります。このため、現在は ECID を使用し、以前は Analytics Cookie を使用していた場合、いずれかのタイプの ID を使用して要求を送信する場合はいつでも、要求に両方の ID を含めるか、expandIDs オプションを指定する必要があります。expandIDs を指定すると、指定した任意の Cookie ID に対応する他の ECID または Analytics Cookie がないかどうかチェックされます。新しく特定されたこれらの Cookie ID を含めるように要求が自動的に拡張されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタム ID から Cookie ID への拡張 </p> </td> 
   <td colname="col2"> <p>e コマース Web サイトでは、訪問者がログインせずにサイトを閲覧して商品を買い物かごに追加し、チェックアウトプロセスに入ることも珍しくありません。ユーザーのログイン時に GDPR 要求のユーザーを特定するために使用された ID がカスタム変数に保存される場合、このログイン前のアクティビティはこの ID に関連付けられません。Analytics Cookie ID を使用すると、Cookie ID がログインをまたいでも保持されるので、ログイン前の閲覧行動をログイン後の購入操作に関連付けることができます。 </p> <p>実装でログイン ID（CRM ID、ユーザー名、ロイヤルティ番号、電子メールアドレスなど、またはこれらの値のハッシュ）がカスタム変数（prop や eVar）またはカスタム訪問者 ID に保存され、この ID を GDPR アクセス要求に使用しているとします。宣伝した項目が閲覧されただけで購入には至っていない場合、データ主体は特に、すべての閲覧情報がアクセス要求の一部として返されないことを意外に思うかもしれません。 </p> <p>そのため Analytics による GDPR の処理では、ID 拡張に対応しており、任意のカスタム ID と同じヒット内のすべての Cookie ID を検出してから、要求を拡張してそれらの ID も含めます。 </p> <p>Cookie の名前空間以外の任意の名前空間と共に expandIDs を指定すると、指定した ID を含んでいるヒットから検出されたすべての Cookie ID（ECID または Analytics Cookie）を含めるように要求が拡張されます。上記の Cookie ID の拡張は、その後、新しく検出されたあらゆる Cookie ID に対して実行されます。 </p> <p>expandIDs オプションをアクセス要求に使用した場合で、指定した ID に ID-PERSON のラベルがある場合は、2 つのファイルセットが返されます。最初のファイルセット（ユーザーセット）には、指定した ID が検出されたヒットのデータのみ含まれています。2番目のファイルセット（デバイスセット）には、指定した ID は存在していなかったが拡張 ID が検出されたヒットのデータのみ含まれています。 </p> </td> 
  </tr> 
 </tbody> 
</table>

GDPR の施行後最初の数ヶ月の間、Analytics GDPR 要求の大部分は ID 拡張を要求しませんでした。ただし、組織にとって適切な値の決定はユーザー次第です。使用する ID を含むデータおよび Adobe Analytics 内で収集するデータに対して ID 拡張が必要かどうかを法務チームに問い合わせる必要があります。第一に考慮すべきことは、複数のユーザーがサイトに訪問した共有デバイス上では、ID 拡張を使用すると、（デバイスファイルの）アクセス要求で返されたデータにデバイスの他のユーザーからのヒットが含まれるということです。訪問したページのように、デバイスファイルにプライベートデータが含まれていないといったラベリングのベストプラクティスに従っていたとしても、そのデバイスファイルには、訪問したページの数とそれらの各訪問の回数が含まれます。訪問者でない可能性があるユーザーとこの情報を共有してもいいのでしょうか。

削除要求の場合、ID 拡張が使用されていないので、Cookie 以外の ID（ECID や Analytics Cookie 以外の任意の ID）を使用して削除する必要があるヒットを特定する場合、そしてその ID が ID-DEVICE ラベルを持つ場合、Cookie ID の一部のインスタンスのみが匿名化されるので、レポートの個別訪問者数が変更されますが、他は変更されません。ID 拡張を指定していない場合、要求に Cookie ID を使用するか、ID-PERSON ラベルと共に ID を使用することをお勧めします。

アドビが ID 拡張を実行する場合、追加のフルデータスキャンが必要になる可能性があります。これにより、アドビが要求を完了するのにかかる時間が増加し、多くの場合、処理時間が 1 週間増加します。

## その他のDGPRリクエストフラグ ##

Analytics では、「expandIDs」フラグに加え、GDPR 要求の一部として渡すことができるフラグが 2 種類サポートされています。これらのフラグとそのデフォルト値は次のとおりです。

```
"analyticsDeleteMethod": “anonymize”
“priority”: “normal”
```

今後、「analyticsDeleteMethod」では、デフォルト値の「anonymize」に加え、「purge」という値もサポートされる可能性があります。この値がサポートされると、単純に DEL ラベルが付いたヒットフィールドの値が更新されるのではなく、ヒット全体が削除されるようになります。

priority フィールドでは、デフォルト値に加え、「low」という値もサポートされています。この値は、データ主体による要求の結果として発生した要求ではないために 30 日以内に完了しなければならないという法的義務が課せられていない要求に対して指定する必要があります。アドビでは、データ主体からの要求以外の目的で GDPR API を使用すること推奨していません。GDPR API はデータの消去や修正を目的としたツールではなく、そのような目的にこの API を使用すると意図しない結果が生じます。

>[!NOTE]
>DGPR APIが提供され、DGPRリクエストの実行時に時間がかかります。このAPIの使用はアドビによってサポートされていないため、アドビの機能に影響を与えることがあります。また、アドビのお客様に対して、高い優先度/優先順位、ユーザーによって開始されるGGPRリクエストの提供に影響する可能性があります。DGPR APIを使用しないでください。これは、大量の訪問者に誤って送信されたデータの消去など、その他の目的のためにDGPR APIを使用しないというものです。
>
>GGPR/削除要求の結果としてヒットを削除（更新または非表示）した訪問者は、状態情報をリセットすることに注意する必要があります。次回訪問者がWebサイトに戻ったとき、その訪問者は新しい訪問者になります。訪問回数、リファラー、最初のページなど、すべてのeVar属性が再度開始されます。この副作用は、データフィールドをクリアし、データフィールドをクリアする場合に望ましくありません。また、DGPR APIがこの使用に適していない理由をハイライトします。
>
>PIIまたはデータの問題を削除するには、担当のエンジニアリングアーキテクトコンサルティングチームに連絡してください。

