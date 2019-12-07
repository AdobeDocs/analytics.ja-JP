---
description: Adobe Analytics には、様々な滞在時間指標およびディメンションが用意されています。ここでは、その内容および計算方法について説明します。
title: 滞在時間
topic: Metrics
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# [!UICONTROL 滞在時間]

様々な滞 [!UICONTROL 在時間指標とディメンション] は、Adobe Analytics製品全体で提供されます。

## [!UICONTROL 「滞在時間」指標]

| 指標 | 定義 | 使用対象 |
|---|---|---|
| [!UICONTROL 合計滞在時間（秒）] | 訪問者が特定のディメンション項目に関与した合計時間を表します。値のインスタンスと、後続のすべてのヒットにわたる持続性を含みます。 prop の場合、滞在時間には後続のリンクイベントもカウントされます。 | Analysis Workspace、Reports &amp; Analytics、Report Builder（「合計滞在時間」と呼ばれる）、Data Warehouse、Ad Hoc Analysis |
| [!UICONTROL 訪問別滞在時間] （秒） | *合計滞在時間（秒）/（訪問バウンス）*<br>各訪問中に訪問者が特定のディメンション項目とやり取りする時間の平均を表します。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL 訪問者別滞在時間] （秒） | *合計滞在時間（秒）/個別*<br>訪問者：訪問者の全期間にわたって、訪問者が特定のディメンション項目を操作した平均時間を表します（cookieの長さ）。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL サイトでの平均滞在時間] （秒） | ディメンション項目のシーケンスごとに、訪問者が特定のディメンション項目に関与した合計時間を表します。名前が示すような「サイト」の平均に限定されません。シーケンスの詳細については、「滞在時間の計算方法」の節を参照してください。<br>**注意**:この指標は、計算の分母が異なるので、ディメンション項目レベルの「訪問別滞在時間」と非常に異なる可能性が高いです。 | Analysis Workspace、Reports &amp; Analytics（分単位で表示）、Report Builder（分単位で表示）、Ad Hoc Analysis |
| [!UICONTROL ページでの平均滞在時間] | 廃止された指標です。<br> 代わりに、ディメンション項目の平均滞在時間が必要な場合は、「サイトでの平均滞在時間」を使用することをお勧めします。 | Report Builder（リクエストにディメンションがある場合） |
| [!UICONTROL セッションの合計長](例：以前のセ [!UICONTROL ッションの長さ] | Mobile アプリ SDK のみ。<br>アプリが次回起動されたときに、以前のセッションの長さが決まります。この指標は、秒単位で計算され、アプリがバックグラウンドにある場合はカウントされず、使用中の場合のみカウントされます。これは、セッションレベルの指標です。<br>例：アプリABCをインストールして起動し、2分間使用した後、アプリを閉じます。 このセッション時間に関するデータは送信されません。 The next time we launch the app, [!UICONTROL Previous Session Length] will be sent with a value of 120. | Analysis Workspace、Reports &amp; Analytics、Report Builder、Mobile Services UI |
| [!UICONTROL セッションの平均長] （モバイル） | *合計セッション長/（起動回数 — 初回起動）*<br>Mobile App SDKのみ。 これは、セッションレベルの指標です。 | Report Builder、Mobile Services UI、Ad Hoc Analysis |

## '滞在時間'ディメンション

| ディメンション | 定義 | 使用対象 |
|---|---|---|
| [!UICONTROL 訪問別滞在時間 - 詳細] | 訪問中の合計滞在時間（秒単位）であり、訪問の一部として各ヒットに適用されます。これは、訪問レベルのディメンションです。 | Analysis Workspace、Ad Hoc Analysis |
| [!UICONTROL 訪問別滞在時間 - グループ] | 9 個の異なる範囲にグループ分けされた詳細なディメンションです。これは、訪問レベルのディメンションです。範囲を次に示します。<ul><li>1 分未満</li><li>1 ～ 5 分</li><li>5 ～ 10 分</li><li>10 ～ 30 分</li><li>30 ～ 60 分</li><li>1 ～ 2 時間</li><li>2 ～ 5 時間</li><li>5 ～ 10 時間</li><li>10 ～ 15 時間</li></ul>**注意**:1回の訪問は12時間のアクティビティの後に期限切れになるので、これより大きいグループは存在しません。 | Analysis Workspace、Reports &amp; Analytics、Report Builder、Ad Hoc Analysis |
| [!UICONTROL ページでの滞在時間 - 詳細] | 各ヒットに関する合計滞在時間（秒単位）です。これはヒットレベルのディメンションで、ページビューとリンクイベントの両方が含まれます。 名前にもかかわらず、「ページ」ディメンションに制限されません。 | Analysis Workspace、Ad Hoc Analysis |
| [!UICONTROL ページでの滞在時間 - グループ] | 10 個の異なる時間範囲にグループ分けされた詳細なディメンションです。ただし、グループディメンションは、ページビュー数のみをカウントします（リンクイベントを除く）。これは、ヒットレベルのディメンションです。範囲を次に示します。<ul><li>15 秒未満</li><li>15 ～ 29 秒</li><li>30 ～ 59 秒</li><li>1 ～ 3 分</li><li>3 ～ 5 分</li><li>5 ～ 10 分</li><li>10 ～ 15 分</li><li>15 ～ 20 分</li><li>20 ～ 30 分</li><li>31 分以上</li></ul> | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |

## 「滞在時間」の計算方法

Adobe Analytics は、明示的な値（リンクイベントおよびビデオ視聴を含む）を使用して、[!UICONTROL 滞在時間]を計算します。

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. For similar reasons, [!UICONTROL Bounce Visits] (i.e. visits with a single hit) also does not have a 'time spent' associated with it.

The **numerator** in all time spent calculations is total seconds spent.

The **denominator** is not available as a separate metric in Adobe Analytics. ヒットレベルの「滞在時間」指標の場合、分母はシーケンスです。 シーケンスは、連続したヒットのセットであり、特定の変数が同じ値を含みます（設定されるか、後続に展開するか、永続化によって）。「前方に拡散」とは、滞在時間を計算する目的で、ページビュー間（後続のリンクイベント間）のpropの持続性を指します。

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL 'Instances'] or [!UICONTROL 'Page Views'], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence).

* 「滞在時間」を把握できないので、バウンスヒットと離脱ヒットも分母から削除されます。

## よくある質問（FAQ）

**Q1:すべての「滞在時間」指標を任意のディメンションに適用できますか。**

A:任意のディメンションに適用できる「滞在時間」指標は次のとおりです。

* [!UICONTROL 合計滞在時間（秒）]

* [!UICONTROL 訪問別滞在時間] （秒）

* [!UICONTROL 訪問者別滞在時間] （秒）

* [!UICONTROL サイトでの平均滞在時間] （秒）

**Q2:他のディメンションとの分類に最も適した滞在時間ディメンションはどれか。**

A: The [!UICONTROL Time Spent on Page – granular] dimension is a hit-level dimension. これを他のディメンションで分類すると、ヒットが存続して分類ディメンションも存在した秒数がわかります。次の例では、検索用語「classifieds」がヒット時間54秒、59秒などに関連付けられています。訪問者がその用語に返されたコンテンツを読み取るのに時間を費やしていることを示している可能性があります。

![](assets/time-spent1.png)

**Q3:ページでの滞在時間のディメンションに対して適[!UICONTROL 切な指標は何ですか]。**

A:任意の指標。 ディメンションには、イベントが発生した正確なヒットに費やした時間が表示されます。 滞在時間が長くなると、訪問者がイベントが発生したページ（ヒット）により長く滞在したことを意味します。

![](assets/time-spent2.png)

**第4四半期：サイトでの[!UICONTROL 平均滞在時間は]、訪問別[!UICONTROL 滞在時間とどのように異なりますか]。**

A:差は指標の分母です。

* [!UICONTROL サイト滞在時間の平均は] 、ディメンション項目を含むシーケンスを使用します。

* [!UICONTROL 訪問別滞在時間は] 、訪問回数を使用します

結果として、これらの指標は、訪問レベルでは似たような結果を生みますが、ヒットレベルでは異なります。

## 滞在時 [!UICONTROL 間の計算例]

次のサーバーコールのセットは、1 回の訪問での 1 名の訪問者のものであるとします。

| 訪問ヒット数 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **訪問の経過時間（秒）** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **滞在時間（秒）** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **ヒットタイプ** | ページ | リンク | ページ | ページ | ページ | ページ | ページ |
| **ページ名** | ホーム | - | 製品      | ホーム | ホーム（リロード） | 買い物かご | 注文確認 |
|  |  |  |  |  |  |  |  |
| **prop1** | A（設定） | A（前方に広がる） | 未設定 | B（セット） | B（セット） | A（設定） | C（設定） |
| **prop1 滞在時間（秒）** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | 赤（設定） | 赤（持続） | （期限切れ） | 青（設定） | 青（セット） | 青（持続） | 赤（セット） |
| **eVar1秒滞在** | 30 | 50 | - | 10 | 40 | 60 | - |

上の表に基づいて、滞在時間指標は次のように計算されます。

| prop1 | 合計滞在時間（秒） | 訪問別滞在時間 | 訪問者別滞在時間 | シーケンスの数 | サイトでの平均滞在時間 |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| 不明な時間 | 100 | - | - | - | - |

| eVar1 | 合計滞在時間（秒） | 訪問別滞在時間 | 訪問者別滞在時間 | シーケンスの数 | サイトでの平均滞在時間 |
|---|---|---|---|---|---|
| 赤 | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| 青 | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| 不明な時間 | 100 | - | - | - | - |

訪問別滞在時間（詳細）:290ページでの滞在時間（詳細）:10、30、40、50、60、100

この例の補足として、次の追加の注意事項があります。

* すべての滞在時間の計算は、訪問の最初のヒット時に0から始まる訪問の経過時間に基づきます。

* 「滞在時間（秒）」は、現在のヒットのタイムスタンプと次のヒットのタイムスタンプの差です。 結果として、訪問の最後のヒット（およびバウンス数）には滞在時間が含まれません。

* 「シーケンス」は、連続したヒットのセットであり、特定の変数が同じ値を含みます（設定されるか、後続に展開するか、永続化によって）。例えば、prop1「A」には、ヒット 1 と 2 およびヒット 6 の 2 つのシーケンスがあります。最後のヒットは滞在時間を含まないので、訪問の最後のヒットの値では新しいシーケンスは開始されません。サイトでの平均滞在時間は、分母のシーケンスを使用します。

   * 滞在時間のみを考慮して、propは、ヒット2のprop1に対して上記のように、ページヒットから後続のリンクヒットに「次に広がる」のです。 これにより、prop1 のヒット 1（「A」）に設定された値をヒット 2 の滞在時間に累計できます。

   * eVarは、eVarが設定または持続するヒットに費やした時間を累積します。 eVarの永続性は、Analytics/管理者のeVar設定で定義します。

