---
description: ヒットデータ、アクセス要求、削除要求のデータラベル付けの方法の例を示します
title: ラベル設定の例
feature: Data Governance
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: c8e3d9bd40a427387da746c084188b5d13f45bcd
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 95%

---

# ラベル設定の例

## サンプルのヒットデータ {#hit}

以下のヒットデータがあるとします。

* 最初の行に各変数のラベルが含まれている。
* 2 番目の行は変数の名前である。ID ラベルがある場合は、割り当てられた名前空間が括弧内に含まれている。
* ヒットデータは 3 番目の行から開始する。

| ラベル | I2 <br> ID-PERSON <br> DEL-PERSON <br> ACC-PERSON | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL | I2 <br> DEL-PERSON <br> ACC-PERSON | I2 <br> DEL-DEVICE <br> DEL-PERSON <br> ACC-ALL | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL |
|---|---|---|---|---|---|
| **変数名** <br> **(名前空間)** | **MyProp1** <br> **（user）** | **訪問者 ID** <br> **（AAID）** | **MyEvar1** | **MyEvar2** | **MyEvar3** <br> **（xyz）** |
| ヒットデータ | Mary | 77 | A | M | X |
|  | Mary | 88 | B | いいえ | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | いいえ | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | いいえ | Z |

## アクセス要求の例 {#access}

アクセス要求を送信すると、概要ファイルには次の表に示されている値が含まれます。要求は、デバイスファイルファイルのみ、ユーザーファイルのみまたはどちらか 1 つを返す可能性があります。2 つの概要ファイルは、ユーザー ID が使用され、expandIDs が true の場合にのみ返されます。

<table>
  <tr>
    <th colspan="2" style="text-align:center">API の値</th>
    <th rowspan="2">返される<br>ファイルタイプ</th>
    <th colspan="5" style="text-align:center">概要アクセスファイルのデータ</th>
  </tr>
  <tr>
    <th>名前空間／ID</th>
    <th>expandIDs</th>
    <th>MyProp1</th>
    <th>訪問者 ID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>false</td>
    <td>デバイス</td>
    <td>存在しない</td>
    <td>77</td>
    <td>存在しない</td>
    <td>M、P</td>
    <td>X、W</td>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>true</td>
    <td>デバイス</td>
    <td>存在しない</td>
    <td>77</td>
    <td>存在しない</td>
    <td>M、P</td>
    <td>X、W</td>
  </tr>
  <tr>
    <td>user=Mary</td>
    <td>false</td>
    <td>ユーザー</td>
    <td>Mary</td>
    <td>77、88、99</td>
    <td>A、B、C</td>
    <td>M、N、O</td>
    <td>X、Y、Z</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary</td>
    <td rowspan="2">true</td>
    <td>ユーザー</td>
    <td>Mary</td>
    <td>77、88、99</td>
    <td>A、B、C</td>
    <td>M、N、O</td>
    <td>X、Y、Z</td>
  </tr>
  <tr>
    <td>デバイス</td>
    <td>存在しない</td>
    <td>77、88</td>
    <td>A、B、C</td>
    <td>N、P</td>
    <td>U、W</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary<br>AAID=66</td>
    <td rowspan="2">true</td>
    <td>ユーザー</td>
    <td>Mary</td>
    <td>77、88、99</td>
    <td>A、B、C</td>
    <td>M、N、O</td>
    <td>X、Y、Z</td>
  </tr>
  <tr>
    <td>デバイス</td>
    <td>存在しない</td>
    <td>66、77、88</td>
    <td>A、B、C</td>
    <td>N、P</td>
    <td>U、W、Z</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>false</td>
    <td>デバイス</td>
    <td>存在しない</td>
    <td>55、77</td>
    <td>存在しない</td>
    <td>M、R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>true</td>
    <td>デバイス</td>
    <td>存在しない</td>
    <td>55、77</td>
    <td>存在しない</td>
    <td>M、P、R</td>
    <td>W、X</td>
  </tr>
</table>

Cookie ID が使用されている場合、expandIDs の設定は出力に影響しないことに注意してください。

## 削除リクエストの例 {#delete}

表の最初の行にある API の値を使用した削除要求の場合、ヒットの表は以下のように更新されます。

<table>
  <tr>
    <th colspan="5" style="text-align:center">AAID=77 <br>（expandIDs の値は関係ありません）</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Mary</td>
    <td>42</td>
    <td>A</td>
    <td>Privacy-7398</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>88</td>
    <td>B</td>
    <td>いいえ</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>99</td>
    <td>C</td>
    <td>O</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>42</td>
    <td>D</td>
    <td>Privacy-1866</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>いいえ</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>いいえ</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>AAID = 77 および DEL-DEVICE ラベルを含む行のセルのみが影響を受けます。

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=false</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>77</td>
    <td>Privacy-1866</td>
    <td>Privacy-3681</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>88</td>
    <td>Privacy-2178</td>
    <td>Privacy-1975</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>99</td>
    <td>Privacy-9045</td>
    <td>Privacy-2864</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>77</td>
    <td>D</td>
    <td>P</td>
    <td>W</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>いいえ</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>いいえ</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>user=Mary および DEL-PERSON ラベルを含む行のセルのみが影響を受けます。また、実際は、A_ID を含む変数は、おそらく prop または eVar です。 置き換える値は、数値を別のランダムな数値で置き換えた文字列ではなく、「Privacy-」で始まり、その後にランダムな数値（GUID）が続く文字列になります。

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=true</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>09</td>
    <td>Privacy-0859</td>
    <td>Privacy-8183</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>16</td>
    <td>Privacy-6104</td>
    <td>Privacy-2911</td>
    <td>Privacy-6821</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>83</td>
    <td>Privacy-2714</td>
    <td>Privacy-0219</td>
    <td>Privacy-4395</td>
  </tr>
  <tr>
    <td>John</td>
    <td>09</td>
    <td>D</td>
    <td>Privacy-8454</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>16</td>
    <td>E</td>
    <td>Privacy-2911</td>
    <td>Privacy-2930</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>いいえ</td>
    <td>Z</td>
  </tr>
</table>

以下のことに注意してください。

* `user=Mary` と `DEL-PERSON` ラベルを含んだ行のセルが影響を受けます。
* ID 拡張により、`AAID=77`、`AAID=88` または `AAID=99`（`user=Mary` を含んだ行の AAID 値）および `DEL-DEVICE` ラベルを含んだ行のセルが影響を受けます。これには、`user=Mary` を満たす行の、`DEL-DEVICE` ラベルが付いたセルが含まれます。これにより、`DEL-DEVICE` ラベル（AAID、MyEvar2 および MyEvar3）を持つ 4 行目と 5 行目（および 1〜3 行目）のセルが難読化されます。
* ExpandIDs 設定は、`user=Mary` の場合、ID-DEVICE ラベルを持つ MyEvar3（`X`、`Y` および `Z`）に存在する値を含めるための呼び出しまでは拡大適用されません。ExpandIDs は、`user=Mary` の行に訪問者 ID（この例では AAID だけでなく ECID も）を含むように拡張するだけです。したがって、`X` および `Z` の MyEvar3 値を含んだ最後の 2 行は影響を受けません。
* `MyEvar2` 4 番目および 5 番目の行のは、同じ訪問者 ID 値 (`77` および `88`) を最初の行と 2 番目の行のものとして扱います。 その結果、ID 拡張には、デバイスレベルの削除用にこれらが含まれます。
* 2 行目と 5 行目の `MyEvar2` の値は、削除の前後で一致します。ただし、削除後は、その行が削除リクエストの一環として更新されなかったので、最後の行にある値 `N` と一致しなくなります。
* `MyEvar3` の動作は ID 拡張をおこなわない場合とは非常に異なりますが、これは、ID 拡張をおこなわないとどの `ID-DEVICES` とも一致しないからです。これで、最初の 5 行で `AAID` が一致します。
