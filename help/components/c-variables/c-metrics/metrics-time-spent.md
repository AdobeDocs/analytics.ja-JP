---
description: Adobe Analyticsで様々な滞在時間指標やオファーを使用できます。 その内容と計算方法を確認します。
title: 滞在時間
topic: Metrics
translation-type: tm+mt
source-git-commit: 8df1fdfb048dd69b4926b7b812ec5dfea4a97b89

---


# [!UICONTROL Time spent]

Various [!UICONTROL 'time spent'] metrics and dimensions are offered across Adobe Analytics products.

## [!UICONTROL 'Time spent'] 指標

| 指標 | 定義 | 利用可能な場所 |
|---|---|---|
| [!UICONTROL Total seconds spent] | 訪問者が特定のディメンション項目に関与した合計時間を表します。すべての後続のヒットにわたる値と永続性のインスタンスを含みます。prop の場合、滞在時間には後続のリンクイベントもカウントされます。 | Analysis Workspace、Reports &amp; Analytics、Report Builder（「合計滞在時間」と呼ばれる）、Data Warehouse、Ad Hoc Analysis |
| [!UICONTROL Time spent per visit] (Seconds) | *合計滞在時間（秒）/（訪問バウンス）*<br>各訪問で訪問者が特定のディメンション項目に関与した平均時間を表します。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL Time spent per visitor] (Seconds) | *合計滞在時間（秒）／（ユニーク訪問者）*<br> 訪問者のライフタイム（cookie の期間）にわたって訪問者が特定のディメンション項目に関与した平均時間を表します。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL Average time spent on site] (Seconds) | 特定のディメンション項目との訪問者の対話時間の合計を、ディメンション項目とのシーケンスごとに表します。 名前が示すように、単に「サイト」の平均に限定されるわけではありません。 シーケンスについて詳しくは、「滞在時間の計算方法」の節を参照してください。<br>**注意&#x200B;**： この指標は、計算での分母の違いにより、ディメンション項目レベルで「訪問別滞在時間」と異なる可能性が非常に高くなります。 | Analysis Workspace、Reports &amp; Analytics（分単位で表示）、Report Builder（分単位で表示）、Ad Hoc Analysis |
| [!UICONTROL Average time spent on page] | 廃止された指標です。<br>ディメンション項目の平均時間が必要な場合は、かわりに「サイトでの平均滞在時間」を使用することをお勧めします。 | Report Builder（リクエストにディメンションがある場合） |
| [!UICONTROL Total session length]など。 [!UICONTROL Previous session length] | Mobile アプリ SDK のみ。<br>アプリが次回起動されたときに、以前のセッションの長さが決まります。秒単位で計算された場合、この指標は、アプリがバックグラウンドにあるときはカウントされず、使用中の場合にのみカウントされます。 これは、セッションレベルの指標です。<br>例：アプリ ABC をインストールして起動し、2 分間使用してからアプリを閉じます。このセッション時間に関するデータは送信されません。The next time we launch the app, [!UICONTROL Previous Session Length] will be sent with a value of 120. | Analysis Workspace、Reports &amp; Analytics、Report Builder、Mobile Services UI |
| [!UICONTROL Average session length] (mobile) | *合計セッション長／（起動階数 — 初回起動）*<br>Mobile App SDKのみ。これは、セッションレベルの指標です。 | Report Builder、Mobile Services UI、Ad Hoc Analysis |

## 「滞在時間」ディメンション

| ディメンション | 定義 | 利用可能な場所 |
|---|---|---|
| [!UICONTROL Time spent per visit - granular] | 訪問中の合計滞在時間（秒単位）であり、訪問の一部として各ヒットに適用されます。これは、訪問レベルのディメンションです。 | Analysis Workspace、Ad Hoc Analysis |
| [!UICONTROL Time spent per visit - bucketed] | 精度の高いディメンションは、9つの異なる範囲にグループ化されました。 これは、訪問レベルのディメンションです。範囲には次のものが含まれます。<ul><li>1分未満</li><li>1 ～ 5 分</li><li>5 ～ 10 分</li><li>10 ～ 30 分</li><li>30 ～ 60 分</li><li>1～2 時間</li><li>2～5 時間</li><li>5～10 時間</li><li>10～15 時間</li></ul>**メモ**：訪問は 12 時間のアクティビティの後に有効期限が切れるので、これより大きいグループはありません。 | Analysis Workspace、Reports &amp; Analytics、Report Builder、Ad Hoc Analysis |
| [!UICONTROL Time spent on page - granular] | 各ヒットに関する合計滞在時間（秒単位）です。ヒットレベルのディメンションであり、ページビュー数およびリンクイベントを含みます。名前にもかかわらず、「ページ」ディメンションに制限されません。 | Analysis Workspace、Ad Hoc Analysis |
| [!UICONTROL Time spent on page - bucketed] | 粒子ディメンションは10の異なる範囲にグループ化され、ただし、グループディメンションではページ表示のみがカウントされます(リンクイベントは除く)。 これは、ヒットレベルのディメンションです。 範囲には次のものが含まれます。<ul><li>15 秒未満</li><li>15 ～ 29 秒</li><li>30 ～ 59 秒</li><li>1 ～ 3分</li><li>3 ～ 5分</li><li>5 ～ 10分</li><li>10 ～ 15分</li><li>15 ～ 20分</li><li>20 ～ 30分</li><li>30分以上</li></ul> | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |

## 「滞在時間」の計算方法

Adobe Analytics uses explicit values (including link events and video views) to calculate [!UICONTROL Time Spent].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. For similar reasons, [!UICONTROL Bounce Visits] (i.e. visits with a single hit) also does not have a &#39;time spent&#39; associated with it.

すべての滞在時間の計算での&#x200B;**分子**&#x200B;は、「合計滞在時間（秒）」です。

**分母**&#x200B;は、Adobe Analytics では個別の指標として使用できません。ヒットレベルの「滞在時間」指標では、分母はシーケンスです。シーケンスは、連続したヒットのセットであり、特定の変数が同じ値を含みます（設定されるか、後続に展開するか、永続化によって）。「後続に展開」とは、滞在時間を計算するための、ページビュー間の（つまり、後続のリンクイベントにまたがる）prop の永続性のことをいいます。

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL 'Instances'] or [!UICONTROL 'Page Views'], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence).

* バウンスおよび離脱ヒットも、滞在&#39;時間が確認できないので、分母から削除されます。

## よくある質問（FAQ）

**Q1：すべての滞在&#39;時間&#39;指標を任意のディメンションに適用できますか。**

回答：任意のディメンションに適用できる「滞在時間」指標は次のとおりです。

* [!UICONTROL Total seconds spent]

* [!UICONTROL Time spent per visit] (Seconds)

* [!UICONTROL Time spent per visitor] (Seconds)

* [!UICONTROL Average time spent on site] (Seconds)

**Q2：他のディメンションを使用した分類で使用するのに最適なのは、どの滞在時間ディメンションですか。**

A:ディメ [!UICONTROL Time Spent on Page – granular] ンションは、ヒットレベルのディメンションです。 これを他のディメンションで分類すると、ヒットが存続して分類ディメンションも存在した秒数がわかります。次の例では、検索語句「classifieds」が 54 秒、59 秒などのヒット時間に関連付けられており、おそらく訪問者がその語句で返されたコンテンツを読むのに時間を費やしていることを示しています。

![](assets/time-spent1.png)

**第3四半期：ディメンションに対して適切な指標は何[!UICONTROL Time Spent on Page – granular]か。**

回答：任意の指標です。このディメンションは、イベントが発生したヒットの滞在時間を表します。滞在時間が長くなると、訪問者がイベントが発生したページ（ヒット）により長く滞在したことを意味します。

![](assets/time-spent2.png)

**第4四半期：～との違い[!UICONTROL Average Time Spent on Site]は何です[!UICONTROL Time Spent per Visit]か。**

回答：違いは、指標の分母です。

* [!UICONTROL Average time spent on site] ディメンション項目を含むシーケンスを使用します。

* [!UICONTROL Time spent per visit] 訪問回数を使用

結果として、これらの指標は、訪問レベルでは似たような結果を生みますが、ヒットレベルでは異なります。

**Q5:内訳の合計が親行項目と一[!UICONTROL Average Time Spent on Site]致しないのはなぜですか？**

A:ディメ [!UICONTROL Average Time Spent on Site] ンションの壊れていないシーケンスに依存し、内部レポートは、これらの実行を計算する際に外部レポートに依存しないので、

例えば、次の訪問を考えてみましょう。
|hit#|1|2|3||—|—|—||**滞在時間**|30|100|10||**Page Name**|Home|Product|Home||**date**|Jan 1|Jan 1|Jan 1||

ホームページのタイムスペントを計算するときは(30+10)/2=20となりますが、日別に分割すると(30+10)/1=40となります。これは、1月1日が1回のみ連続して実行されるからです。

結果として、これらの指標は、訪問レベルでは似たような結果を生みますが、ヒットレベルでは異なります。

## 計算の [!UICONTROL Time Spent] 例

次のサーバーコールのセットは、1 回の訪問での 1 名の訪問者のものであるとします。

| 訪問ヒット数 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **訪問経過時間（秒）** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **滞在時間（秒）** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **ヒットタイプ** | ページ | リンク | ページ | ページ | ページ | ページ | ページ |
| **ページ名** | ホーム | - | 製品 | ホーム | ホーム（リロード） | 買い物かご | 注文確認 |
|  |  |  |  |  |  |  |  |
| **prop1** | A（セット） | A（前方に広がる） | 未設定 | B（設定） | B（設定） | A（セット） | C（セット） |
| **prop1秒** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | 赤（設定） | 赤（持続） | （期限切れ） | 青（設定） | 青（設定） | 青（持続） | 赤（設定） |
| **eVar1 滞在時間（秒）** | 30 | 50 | - | 10 | 40 | 60 | - |

上の表に基づいて、滞在時間指標は次のように計算されます。

| prop1 | 合計滞在時間（秒） | 訪問別滞在時間 | 訪問者別滞在時間 | シーケンス数 | サイトでの平均滞在時間 |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| 非帰属時間 | 100 | - | - | - | - |

| eVar1 | 合計滞在時間（秒） | 訪問別滞在時間 | 訪問者別滞在時間 | シーケンス数 | サイトでの平均滞在時間 |
|---|---|---|---|---|---|
| 赤 | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| ブルー | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| 非帰属時間 | 100 | - | - | - | - |

訪問別滞在時間（詳細）：290ページでの滞在時間（詳細）：10、30、40、50、60、100

この例の補足として、次の追加の注意事項があります。

* すべての滞在時間の計算は、訪問の最初のヒットでゼロから始まる、訪問の経過時間に基づいています。

* 「滞在時間（秒）」は、現在のヒットのタイムスタンプと次のヒットのタイムスタンプの間の差異です。その結果、訪問（およびバウンス）の最後のヒットには滞在時間がありません。

* 「シーケンス」とは、特定の変数に同じ値が含まれる連続したヒットのセットです（設定によるヒット、広がり、永続化によるヒットなど）。 例えば、prop1 &quot;A&quot;には2つのシーケンスがあります。ヒット1と2、ヒット6。 最後のヒットに滞在時間がないので、訪問の最後のヒットの値が新しいシーケンスを開始することはありません。 サイトでの平均滞在時間は、分母内でシーケンスを使用した時間です。

   * 滞在時間を目的とする場合のみ、前述の prop1 のヒット 2 に示されているように、prop がページヒットから後続のリンクヒットに「後続に展開」されます。これにより、prop1 のヒット 1（「A」）に設定された値をヒット 2 の滞在時間に累計できます。

   * eVar は、eVar が設定または永続化された任意のヒットの滞在時間を累計します。eVar の永続性は、「Analytics／管理者の eVar 設定」で定義されます。

