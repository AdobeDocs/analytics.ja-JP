---
description: コホート分析のユースケースの例について説明します。
keywords: Analysis Workspace
title: コホート分析の使用例
feature: Visualizations
role: User, Admin
exl-id: fc7e7bad-ab57-4bb8-a448-60b9397ef5af
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 99%

---

# コホート分析のユースケース

[!UICONTROL コホート分析]のユースケースの例です。

## アプリエンゲージメントの使用例

アプリをインストールしたユーザーが時間の経過に伴ってアプリとどのように関わっているかを分析したいとします。インストールしてから一度も使用していないのか、しばらく使用してから離れていったのか、それとも、長期間継続して使用しているのかといったことを分析します。

6 ヶ月間のコホート分析を作成できます。

**精度**：毎月、2015 年 1 月から 2015 年 6 月まで

**インクルージョン指標**：アプリインストール数

**リターン指標**：セッション数または開始数

訪問者は、セッションを実行しているか、少なくともアプリを起動していない限り、後続の月では *`engaged`* としてカウントされません。[!UICONTROL コホート分析]は、*`App Install`* が常に 0 ヶ月目に発生する使用状況のパターンを示します。ユーザーがアプリをインストールしているかどうかにかかわらず、2 ヶ月目には使用量が下がることに気づくかもしれません（2015 年 1 月にアプリをインストールした場合、2 ヶ月目は 2015 年 3 月です。2015年2月にアプリをインストールした場合、2 か月目は 2015年4月です。その後も同様に続きます）。この分析により、アプリをインストールしてから 2 か月以内にすべてのユーザーにメールまたはプッシュメッセージを送信して、アプリの使用を促すことができます。

## サブスクリプションの使用例

Adobe.com で、無料の Creative Cloud サブスクリプションを提供しているとします。目的は、ユーザーに無料版から 30 日間の体験版にアップグレードしてもらうこと、または最終的に有料版にアップグレードしてもらうことです。

**精度**：毎月

**インクルージョン指標**：ダウンロードリンク

**リターン指標**：有料の Creative Cloud の購入

[!UICONTROL コホート分析]を使用すると、例えば、無料版 Creative Cloud ユーザーの 8 ％～10 ％が、いつインストールしたかにかかわらず、インストールしてから最初の月にアップグレードするということがわかります。12～15 ％が 2 ヶ月使用してアップグレードします。それ以降は、アップグレードは大幅に低下します。3 ヶ月目には 4～5 ％、4 ヶ月目には 3～4 ％、そして 5 ヶ月目には 1～2 ％になります。

3 ヶ月目の潜在顧客を失わないようにする必要があると認識し、3 ヶ月目の中頃にサンプルユーザーに電子メールを発送するキャンペーンを設定し、まだアップグレードしていないユーザーに 50 ドルのクーポンを提供します。

数ヶ月後にコホート分析レポートを見直します。キャンペーンの開始後に形成されたコホートに関して、3 ヶ月目の Creative Cloud の有料サブスクリプションへのコンバージョンが 4～5 ％から 13～14 ％に上昇し、以来 3 ヶ月に達した各月のコホートでは、結果的にコホートあたり数十万ドルになりました。

## 複雑なコホートセグメントの使用例

ある大手ホテルチェーンは、複数の顧客グループをターゲットにしてプロモーションを展開し、パフォーマンスを追跡しています。ターゲットとする最適なユーザーコホートのグループを特定するために、非常に限定的なコホートグループを作成したいと考えています。[!UICONTROL コホートテーブル]の拡張された[!UICONTROL インクルージョン]条件および[!UICONTROL リターン]条件を使用して複数の指標およびセグメントによる適切なコホートグループを定義することで、パフォーマンスの低い顧客グループを特定し、それらのグループをターゲットにしてプロモーションやお買い得商品を提供して予約を増やすことができます。

## アプリの採用バージョンの使用例

ある大手保険会社は、モバイルアプリを通じて様々な顧客エンゲージメントを促進しています。ただ、アプリに新機能を追加する際には、顧客に最新バージョンのアプリにアップグレードしてもらうことが重要になります。[!UICONTROL カスタムディメンション]コホートを使用すれば、すべてのアプリバージョンを並べて分析および比較し、どのバージョンを使用している顧客をターゲットにすべきかを確認できます。また、リテンションとチャーンの両方を追跡すれば、顧客が時間の経過と共にアプリを使用しなくなっているかどうかを特定のバージョンごとに確認できます。このような利用者に向けて、最新バージョンにアップグレードして最新の機能を利用するようモバイルメッセージで呼びかけ、ユーザーとのつながりを再構築できます。

## キャンペーンの定着率の使用例

ある多国籍メディア企業は、ターゲットキャンペーンを使用してユーザーを様々なプラットフォームに誘導し、エンゲージメントを高めようとしています。プラットフォームごとの広告費は、顧客のエンゲージメントとリテンションに基づいて決定されます。そのため、キャンペーンの成功が、このメディア企業の成功にとって重要となります。[!UICONTROL コホート]テーブルの新しい[!UICONTROL カスタムディメンション]コホート機能を使用すると、様々なキャンペーンを並べて比較し、ユーザーの獲得および保持に最も効果的なキャンペーンを特定して、エンゲージメントを向上できます。その後、どの側面がキャンペーンを成功に導いているかを特定し、それを他のキャンペーンに適用して、様々なプラットフォームでのエンゲージメントを改善できます.

## 製品ローンチのユースケース

ある大手衣料品小売業者は、企業収益の大部分を生み出すいくつもの顧客セグメントを抱えています。各セグメントに向けて、そのセグメントを念頭に置いた特別な製品がデザインされ、製造されています。この小売業者は、製品を発売する際に、新製品が時間の経過と共に様々なコホートでどのように売上を伸ばしたかを把握したいと考えています。[!UICONTROL コホート分析]の新しい[!UICONTROL 待ち時間テーブル]の設定を使用して、特定の顧客セグメントの発売前と発売後の行動および収益を分析できます。この情報に基づいて、新たな収益を生み出している製品や、顧客に受けていない製品を特定できます。

## 個人の定着度 - 最も忠誠心の高いユーザーのユースケース

ある大手航空会社は、収益の多くをリピート客と常連客から得ています。常連の旅行客が収益の柱になっているので、事業の長期的な成功のためには、顧客を維持することが重要になります。忠誠心が高くリピート率の高い顧客を特定することは、しばしば難しい作業です。しかし、[!UICONTROL コホート分析]の新しい[!UICONTROL ローリング計算]設定を使用すれば、常連客セグメントを分析し、前月比でリピート率の高い顧客を特定できます。その後、これらの顧客をターゲットに、ロイヤルティに対する報酬と特典を提供できるようになりました。また、コホートタイプをリテンションからチャーンに切り替えると、前月比でリピート購入していない顧客を特定し、これらのセグメントをターゲットにして、再エンゲージメントや継続利用を促すプロモーションを実施できます。
