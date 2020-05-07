---
description: コホート分析の使用例です。
keywords: Analysis Workspace
title: コホート分析の使用例
topic: Reports and analytics
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
translation-type: tm+mt
source-git-commit: 79849c574909543d74e2935e493008927700585d
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 77%

---


# [!UICONTROL コホート分析] の使用例

Use case examples for [!UICONTROL Cohort Analysis].

## アプリエンゲージメントの使用例 {#section_ADEC6EE79F1846319B2E0D9544CC5E40}

アプリをインストールしたユーザーが時間の経過に伴ってアプリとどのように関わっているかを分析したいとします。インストールしてから一度も使用していないのか、しばらく使用してから離れていったのか、それとも、長期間継続して使用しているのかといったことを分析します。

You can create a six-month [!UICONTROL Cohort Analysis]:

**精度**：毎月、2015 年 1 月から 2015 年 6 月まで

**インクルージョン指標**：アプリインストール数

**リターン指標**：セッション数または開始数

訪問者は、その後の数ヶ月は&#x200B;*`engaged`*&#x200B;ものとしてカウントされません（セッションをおこなっているか少なくともアプリを起動している場合を除く）。[!UICONTROL コホート分析] は、0か月目に常に発生する使用パターンを示し *`App Install`* ます。 ユーザーがアプリをインストールしているかどうかにかかわらず、2 ヶ月目には使用量が下がることに気づくかもしれません（2015 年 1 月にアプリをインストールした場合、2 ヶ月目は 2015 年 3 月です。2015 年 2 月にアプリをインストールした場合、2 ヶ月目は 2015 年 4 月です。以下同様）。この分析により、アプリをインストールしてから 2 ヶ月目の間にすべてのユーザーに電子メールやプッシュメッセージを送信して、アプリの使用を促すことができます。

## サブスクリプションの使用例 {#section_FDECB16766CF415BB84AE46BA491FB5F}

Adobe.com で、無料の Creative Cloud サブスクリプションを提供しているとします。目的は、ユーザーに無料版から 30 日間の体験版にアップグレードしてもらうこと、または最終的に有料版にアップグレードしてもらうことです。

**精度**：毎月

**インクルージョン指標**：ダウンロードリンク

**リターン指標**：有料の Creative Cloud の購入

Using this [!UICONTROL Cohort Analysis], you could see, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. 12～15 ％が 2 ヶ月使用してアップグレードします。それ以降は、アップグレードは大幅に低下します。3 ヶ月目には 4～5 ％、4 ヶ月目には 3～4 ％、そして 5 ヶ月目には 1～2 ％になります。

3 ヶ月目の潜在顧客を失わないようにする必要があると認識し、3 ヶ月目の中頃にサンプルユーザーに電子メールを発送するキャンペーンを設定し、まだアップグレードしていないユーザーに 50 ドルのクーポンを提供します。

数ヶ月後にコホート分析レポートを見直します。キャンペーンの開始後に形成されたコホートに関して、3 ヶ月目の Creative Cloud の有料サブスクリプションへのコンバージョンが 4～5 ％から 13～14 ％に上昇し、以来 3 ヶ月に達した各月のコホートでは、結果的にコホートあたり数十万ドルになりました。

## 複雑なコホートセグメントの使用例

ある大手ホテルチェーンは、複数の顧客グループをターゲットにしてプロモーションを展開し、パフォーマンスを追跡しています。ターゲットとする最適なユーザーコホートのグループを特定するために、非常に限定的なコホートグループを作成したいと考えています。Using the augmented [!UICONTROL Inclusion] and [!UICONTROL Return] Criteria within [!UICONTROL Cohort] Tables, they are able to define just the right cohort groupings with multiple metrics and segments to identify underperforming customers groups in order to target them with promotions and deals to increase bookings.

## アプリの採用バージョンの使用例

ある大手保険会社は、モバイルアプリを通じて様々な顧客エンゲージメントを促進しています。ただ、アプリに新機能を追加する際には、顧客に最新バージョンのアプリにアップグレードしてもらうことが重要になります。They can analyze and compare all of their app versions side-by-side using [!UICONTROL Custom Dimension] Cohort to see which customers on which app version to target. また、リテンションとチャーンの両方を追跡すれば、顧客が時間の経過と共にアプリを使用しなくなっているかどうかを特定のバージョンごとに確認できます。このような利用者に向けて、最新バージョンにアップグレードして最新の機能を利用するようモバイルメッセージで呼びかけ、ユーザーとのつながりを再構築できます。

## キャンペーンの定着率の使用例

ある多国籍メディア企業は、ターゲットキャンペーンを使用してユーザーを様々なプラットフォームに誘導し、エンゲージメントを高めようとしています。プラットフォームごとの広告費は、顧客のエンゲージメントとリテンションに基づいて決定されます。そのため、キャンペーンの成功が、このメディア企業の成功にとって重要となります。They use our new [!UICONTROL Custom Dimension] Cohort feature in [!UICONTROL Cohort] Tables to compare various campaigns side-by-side to identify which campaigns are most effective at acquiring and retaining users to increase engagement. その後、どの側面がキャンペーンを成功に導いているかを特定し、それを他のキャンペーンに適用して、様々なプラットフォームでのエンゲージメントを改善できます.

## 製品ローンチでの使用例

ある大手衣料品小売業者は、企業収益の大部分を生み出すいくつもの顧客セグメントを抱えています。各セグメントに向けて、そのセグメントを念頭に置いた特別な製品がデザインされ、製造されています。この小売業者は、製品を発売する際に、新製品が時間の経過と共に様々なコホートでどのように売上を伸ばしたかを把握したいと考えています。[!UICONTROL コホート分析の新しい] 待ち時間テーブル [!UICONTROL 設定を使用すると]、開始前と開始後の特定の顧客セグメントの行動と売上高を分析できます。 この情報に基づいて、新たな収益を生み出している製品や、顧客に受けていない製品を特定できます。

## 個人の定着度 - 最も忠誠心の高いユーザー使用例

ある大手航空会社は、収益の多くをリピート客と常連客から得ています。常連の旅行客が収益の柱になっているので、事業の長期的な成功のためには、顧客を維持することが重要になります。忠誠心が高くリピート率の高い顧客を特定することは、しばしば難しい作業です。However, using the new [!UICONTROL Rolling Calculation] setting in [!UICONTROL Cohort Analysis], they were able to analyze loyal customer segments and find out which travelers were repeat purchasers month-over-month. これにより、常連客にポイントや特典を付与できるようになります。また、コホートタイプをリテンションからチャーンに切り替えると、前月比でリピート購入していない顧客を特定し、これらのセグメントをターゲットにして、再エンゲージメントや継続利用を促すプロモーションを実施できます。
