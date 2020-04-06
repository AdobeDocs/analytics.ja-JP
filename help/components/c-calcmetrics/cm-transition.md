---
description: Analyticsでの計算指標の動作方法に対するこれらの変更は、ユーザーに影響を与える可能性があります。
title: よくある質問
uuid: 9b7f1cd1-b969-4b15-8af1-969d816b65b8
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# よくある質問

処理に影響を及ぼす可能性のある、[!DNL Analytics] における計算指標の機能の変更を次に示します。

[計算指標ビルダーにアクセスするにはどうすればよいですか？](/help/components/c-calcmetrics/cm-transition.md#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1)

[計算指標マネージャにアクセスするにはどうすればよいですか？](/help/components/c-calcmetrics/cm-transition.md#section_DD0BD13E9EC940268EBE8BC88241A152)

[同じ名前の計算指標が多数あるのはなぜですか？](/help/components/c-calcmetrics/cm-transition.md#section_E15C5B6CCC58498CAEC3FBDA8988F0A1)

[グローバル計算指標はどうなりましたか？](/help/components/c-calcmetrics/cm-transition.md#section_7351D4C7361F4ABAA1B43F8E89AAD211)

[ログイン会社で共有されていたグローバル計算指標はどうなりましたか？](/help/components/c-calcmetrics/cm-transition.md#section_59E5CD948ED643AE9AD3D2E4277647F8)

[分類が Numeric または Numeric2 の計算指標はどうなりましたか？](/help/components/c-calcmetrics/cm-transition.md#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B)

[全期間指標はどうなりましたか？](/help/components/c-calcmetrics/cm-transition.md#section_AEDB02EF24584DAD8731BED9DDCE4F48)

[日別／週別／月別／四半期別／年別訪問者数指標に基づく計算指標についてどのような情報が必要ですか？](/help/components/c-calcmetrics/cm-transition.md#section_E9A77EBB41CE4881B196CC1C282B2DF3)

[古いレポートスイート API メソッドを使用して作成または管理されている計算指標はどうなりますか？](/help/components/c-calcmetrics/cm-transition.md#section_13ED1BAD02634674BDAEB479B060A4B6)

[「現在のデータ」はすべてのタイプの計算指標をサポートしますか？](/help/components/c-calcmetrics/cm-transition.md#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2)

[移行した計算指標とともに表示される「名前が指定されていません」というメッセージはどのような意味ですか？](/help/components/c-calcmetrics/cm-transition.md#section_C90CBB72A67644F38D583301981F8D03)

[ユーザーが削除された場合、そのユーザーの計算指標はどうなりますか？](/help/components/c-calcmetrics/cm-transition.md#section_42ED4C15830540879C4A161423690E5A)

[作成および他のレポートスイートへの適用が可能な計算指標がそれらのレポートスイートで「有効」でない場合、「不明」と表示されるのはなぜですか？](/help/components/c-calcmetrics/cm-transition.md#section_6772818EFDED46E9B7095D64C3B77211)

[従来の計算指標に対して行った変更が保存されないのはなぜですか？](/help/components/c-calcmetrics/cm-transition.md#section_81CDEFCA1FD542579AF183DA1494EAF0)

[計算指標がマーケティングチャネルレポートに表示されないのはなぜですか？](/help/components/c-calcmetrics/cm-transition.md#section_FC350359A775433AB5F43C7CAB304D62)

[一部の計算指標の数式に、追加した丸括弧が表示されないのはなぜですか？](/help/components/c-calcmetrics/cm-transition.md#section_AC0D1E9714AD487F9A1C73359F518B5E)

[（Ad Hoc Analysis のみ）埋め込みまたはインラインのセグメント定義を含む計算指標は引き続きサポートされますか？](/help/components/c-calcmetrics/cm-transition.md#section_B25C924A282F49388AB604E3D826F44C)

[（Report Builder のみ）計算指標が要求に表示されなくなったのはなぜですか？](/help/components/c-calcmetrics/cm-transition.md#section_DA4792FE5D7945218CD5E6328DE08E82)

[計算指標の合計はどのように計算されますか？](/help/components/c-calcmetrics/cm-transition.md#section_57BA3A299C7948ABB82B0392A9B0F33E)

## 計算指標ビルダーにアクセスするにはどうすればよいですか？ {#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1}

* Click **[!UICONTROL + Add]** at the top of the Calculated Metric Manager, or
* In any Analytics report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Add]**.

## 計算指標マネージャにアクセスするにはどうすればよいですか？ {#section_DD0BD13E9EC940268EBE8BC88241A152}

* Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Components]** in the left navigation. その後、「**[!UICONTROL Calculated Metrics]**」をクリックします。

* In any [!DNL Analytics] report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Manage]**.

## 同じ名前の計算指標が多数あるのはなぜですか？ {#section_E15C5B6CCC58498CAEC3FBDA8988F0A1}

(以前は、グローバル計算指標は特定の管理者ユーザーが所有しておらず、そのレポートスイートのすべてのユーザーに対して表示されていました。 指標はレポートスイートによって区別されました。 あるレポートスイートの指標の名前が別のレポートスイートの指標と同じである場合、レポートスイートを切り替えたときに、その指標は単に同じ指標として表示されます)。

現在は、指標がレポートスイートによって区別されなくなりました。 あるレポートスイートの指標の名前が別のレポートスイートの指標と同じである場合、その指標は計算指標ビルダーと指標セレクターの両方に表示され、同じ定義を持つ場合と持たない場合でも、重複指標として表示されます。

そのため、次に示すように「`<report suite>` のみ」チェックボックスを選択解除している場合のみ、同じ名前の（別のレポートスイートで作成された）計算指標が複数表示されます。

![](assets/report_suite.png)

**必要な操作**

名前と定義が類似した計算指標の統合を検討し、統合する際は注意が必要です。 計算指標マネージャでレポートスイートの計算指標をチェックして、元のレポートスイートを確認できます。 また、指標の統合が正しく行われていることを確認するために、潜在的な重複を削除する際に、指標の定義を確認する必要があります。

>[!NOTE]計算指標が特定のレポートスイートにバインドされなくなり、ログイン会社に対して表示されるすべてのレポートスイートで使用できるようになりましたが、その計算指標が作成された、または最後に保存されたレポートスイートは引き続き計算指標マネージャに表示されます。

>[!NOTE]計算指標が削除されても、その指標を参照するブックマークやダッシュボードレポートは引き続き機能します。

## グローバル計算指標はどうなりましたか？ {#section_7351D4C7361F4ABAA1B43F8E89AAD211}

（以前は、管理者は管理ツールを使用して、「グローバル計算指標」または「レポートスイート計算指標」と呼ばれる計算指標をレポートスイートで作成できました）。

グローバル計算指標は、ログイン会社の管理者リストの最初の管理者ユーザーが所有するようになりました。 デフォルトでは「全員」と共有されます。 このパターンは、セグメントと同じ共有モデルおよび移行計画に従います。

**必要な操作**

何も。 ただし、新しい管理者の所有者は、これらの計算指標を変更または削除する際には注意が必要です。計算指標は、多数のブックマーク付きレポートやダッシュボードで使用される場合があります。

>[!NOTE]計算指標が削除されても、その指標を参照するブックマークやダッシュボードレポートは引き続き機能します。

## ログイン会社で共有されていたグローバル計算指標はどうなりましたか？ {#section_59E5CD948ED643AE9AD3D2E4277647F8}

（以前は、管理者は管理ツールを使用して、「グローバル計算指標」または「レポートスイート計算指標」と呼ばれる計算指標をレポートスイートで作成できました）。 複数のログイン会社にレポートスイートを追加することで、これらの指標をログイン会社間で「共有」できます。

グローバル計算指標は、ログイン会社間で共有できなくなりました。 これらは、特定のレポートスイートに結び付けられたり、結び付けられたりするのではなく、特定のログイン会社に結び付けられます。 ログイン会社で共有された計算指標

* 対象のレポートスイートへのアクセス権を持つすべてのログイン会社に移行されます。
* デフォルトで「全員と共有」されます。
* 他のすべてのログイン会社とは無関係のコピーとして扱われます。

>[!NOTE]計算指標がブックマーク、ダッシュボード、アラートまたは予定レポートで使用されていた場合は、新しいコピーを編集しても、維持されていた古い計算指標には影響しません。

## 分類が Numeric または Numeric2 の計算指標はどうなりましたか？ {#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B}

(Previously, calculated metrics with a Numeric or Numeric2 classification were only visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs.)

Now, calculated metrics with a Numeric or Numeric2 classification will continue to be visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs. ただし、このような指標は、セグメントが適用されたレポートではサポートされません。

また、分類がNumericまたはNumeric2の計算指標は、次のコンポーネントではサポートされません。、 [!UICONTROL Ad Hoc Analysis]、レポ [!UICONTROL Analysis Workspace]ート、 [!UICONTROL Real-Time] お [!UICONTROL Anomaly Detection]よび [!UICONTROL Contribution Analysis]。 分類がNumericまたはNumeric2の計算指標を作成または編集すると、互換性に関する警告が表示され、その計算指標が製品の特定の領域と互換性がないことが示されます。

**必要な操作**

指標をセグメントまたは互換性のないコンポーネントと共に使用する場合は、Numeric1分類またはNumeric2分類を使用して計算指標を作成しないでください。

## 全期間指標はどうなりましたか？ {#section_AEDB02EF24584DAD8731BED9DDCE4F48}

全期間指標のサポートは終了しました。したがって、全期間指標は [!UICONTROL Reports & Analytics] UI やその他の UI には表示されません。レポートAPIでクエリすることはできません。

他の有効な指標が1つ以上含まれている限り、全時間指標を含むブックマーク、ダッシュボード、予定レポートまたはアラートは、引き続きその指標なしで実行されます。 ブックマーク、ダッシュボード、予定レポートまたはアラートの唯一の指標が全時間指標の場合、レポートは実行されなくなります。

## 日別／週別／月別／四半期別／年別訪問者数指標に基づく計算指標についてどのような情報が必要ですか？ {#section_E9A77EBB41CE4881B196CC1C282B2DF3}

Calculated metrics based on Unique Visitor metrics will be visible in the following [!DNL Analytics] components: [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and Reporting API.

ただし、これらの指標は次のコンポーネントではサポートされません。、 [!UICONTROL Segments]、レポ [!UICONTROL Analysis Workspace]ート、 [!UICONTROL Real-Time] お [!UICONTROL Anomaly Detection]よび [!UICONTROL Contribution Analysis]。 個別訪問者数指標に基づく計算指標を作成または編集すると、互換性に関する警告が表示されます。この警告は、特定の分野の製品との互換性がその指標にないことを示します。

セグメントを含むレポートで、ベースの訪問者数指標を使用します。 個別訪問者数指標に基づく計算指標の作成は可能ですが、セグメントを含むレポートにその計算指標を適用することはできません。また、その計算指標にセグメントを埋め込むこともできません。

## 古いレポートスイート API メソッドを使用して作成または管理されている計算指標はどうなりますか？ {#section_13ED1BAD02634674BDAEB479B060A4B6}

以前は、（1.3または1.4） APIメソッドReportSuite.SaveCalculatedMetricsを使用して計算指標を保存する方法は、管理コンソールで計算指標を作成または更新する方法と同じでした。 ReportSuite.DeleteCalculatedMetricsにも同様です。 また、管理コンソールに表示される計算指標のリストや、ReportSuite.GetCalculatedMetricsを呼び出す際に表示される計算指標の情報も同じでした。

現在、ReportSuite CalculatedMetrics API メソッド（1.3 または 1.4）は、引き続き古いストアを使用して計算指標の保存、削除および取得を行います。既存の計算指標は移行され、新しい計算指標ビルダーに表示されます。 **APIメソッドで作成された新しい計算指標は、APIでのみ表示されます。 引き続き、レポートAPIで使用できます。**

**必要な操作**

APIと計算指標ビルダーの両方を使用する必要がある場合は、ReportSuite CalculatedMetrics APIメソッドの使用を停止し、代わりに新しいCalculatedMetrics APIメソッド(Get、Save、Delete、GetFunctions)を使用する必要があります。

## 「現在のデータ」はすべてのタイプの計算指標をサポートしますか？ {#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2}

現在のデータは、セグメントや統計関数を含む計算指標をサポートしていません。 サポートされている関数は、加算、削除、乗算、除算、否定(-x)などの基本的な数学関数のみです。

## 移行した計算指標とともに表示される「名前が指定されていません」というメッセージはどのような意味ですか？ {#section_C90CBB72A67644F38D583301981F8D03}

「名前が指定されていません」は、指標名が移行された指標に関連付けられていない（つまり、説明的な名前のないただの数式である）ことを意味します。

## ユーザーが削除された場合、そのユーザーの計算指標はどうなりますか？ {#section_42ED4C15830540879C4A161423690E5A}

このユーザーが作成した計算指標もすべて削除されます。 ただし、削除した計算指標は、保存されたブックマーク、ダッシュボードまたは予定レポートの一部として引き続き機能します。

## 作成および他のレポートスイートへの適用が可能な計算指標がそれらのレポートスイートで「有効」でない場合、「不明」と表示されるのはなぜですか？ {#section_6772818EFDED46E9B7095D64C3B77211}

選択したレポートスイートに存在しないベース指標またはベースディメンションが計算指標に含まれている場合は、ユーザーインターフェイスに「不明」と表示されます。

## 従来の計算指標に対して行った変更が保存されないのはなぜですか？ {#section_81CDEFCA1FD542579AF183DA1494EAF0}

これは、2015年6月15日から6月18日の間に新しい計算指標データベースに移行するタイミングが原因である可能性があります。

**必要な操作**

従来の指標に対して行った変更をやり直す必要があります。

## 計算指標がマーケティングチャネルレポートに表示されないのはなぜですか？ {#section_FC350359A775433AB5F43C7CAB304D62}

(以前は、「ファーストタッチ」および「ラストタッチ」オプションを含むマーケティングチャネルレポートの指標セレクターに、すべての計算指標が表示されていました)。

現在は、計算指標ビルダーで配分タイプが「ファーストタッチ」または「ラストタッチ」に特定設定されている計算指標のみが、マーケティングチャネルレポートの指標セレクターで使用できます。 既にマーケティングチャネルレポートに適用されている計算指標は、引き続き適用され、以前と同じように機能します。 マーケティングチャネル用の計算指標を作成するには、指標ビルダーの設定アイコンをクリックし、配分タイプとして「ファーストタッチ」または「ラストタッチ」を選択します。 この処理を行うと、計算指標がマーケティングチャネルレポートとのみ互換性を持つようになり、他のレポートでは使用できなくなるので注意が必要です。

## 一部の計算指標の数式に、追加した丸括弧が表示されないのはなぜですか？ {#section_AC0D1E9714AD487F9A1C73359F518B5E}

移行中に、一部の数式から余分な丸括弧が削除されました。 削除されたのは、指標の計算に影響しない丸括弧のみです。 この処理は数式を簡略化するためのものであり、データが変更されることはありません。

## （Ad Hoc Analysis のみ）埋め込みまたはインラインのセグメント定義を含む計算指標は引き続きサポートされますか？ {#section_B25C924A282F49388AB604E3D826F44C}

Ad Hoc指標で作成された計算指標には、以前は分析内のセグメント定義を含めることができました。 これはもはや不可能です。

**必要な操作**

セグメントを明示的に保存する必要があります。インラインセグメント定義を含む既存の計算指標は引き続き正しく実行され、Ad Hoc Analysis でも表示できます。ただし、このような計算指標を保存するには、セグメントを明示的に保存する必要があります。

## （Report Builder のみ）計算指標が要求に表示されなくなったのはなぜですか？ {#section_DA4792FE5D7945218CD5E6328DE08E82}

v5.2 で作成された要求に計算指標が含まれている場合、v5.1（またはそれ以前のバージョン）ではその指標が表示されません。これは、計算指標がグローバルID（レポートスイート固有でないID）を使用するようになったためです。

**必要な操作**

これらの指標を表示するには、v5.2にアップグレードする必要があります。

## 計算指標の合計はどのように計算されますか？ {#section_57BA3A299C7948ABB82B0392A9B0F33E}

When [!UICONTROL Reports & Analytics] shows a calculated metrics total in [!UICONTROL Reports & Analytics], it&#39;s just applying the formula to the total. 例えば、注文件数/訪問回数という計算指標の合計は、合計注文件数を取得し、合計訪問回数で割ります。 ただし、計算指標の合計が行項目の合計ではなく、サイトの合計になる場合があります。

例1:訪問者:同じ訪問者が複数の用語を検索した可能性があるので、この場合、合計訪問者数は行項目の合計と等しくありません。

例2:製品のページ表示:買い物かごには複数の商品が入っている場合があるので、その結果、買い物かごには複数のページ表示が存在します。 行項目の合計をレポートの合計と比較する方法について詳しくは、このナレッジベース [の記事を参照してください](https://helpx.adobe.com/jp/analytics/kb/sum-line-items-different-from-total.html)。
