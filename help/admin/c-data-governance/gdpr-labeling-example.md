---
description: 'null'
title: ラベル設定の例
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: ht
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# ラベル設定の例

## ヒットデータのサンプル

以下のヒットデータがあるとします。

* 最初の行に各変数のラベルが含まれている。
* 2 番目の行は変数の名前である。ID ラベルがある場合は、割り当てられた名前空間が括弧内に含まれている。
* ヒットデータは 3 番目の行から開始する。

| ラベル | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **変数名**<br>**（名前空間）** | **MyProp1**<br>**（ユーザー）** | **訪問者 ID**<br>**（AAID）** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**（xyz）** |
| ヒットデータ | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## アクセス要求のサンプル

アクセス要求を送信する場合、概要ファイルには、以下の表に示された値が含まれます。要求は、デバイスファイルファイルのみ、ユーザーファイルのみまたはどちらか 1 つを返す可能性があります。2 つの概要ファイルは、ユーザー ID が使用され、expandIDs が true の場合にのみ返されます。

| API の値 | API の値 | 返されるファイルタイプ | 概要アクセスファイルのデータ<br> | 概要アクセスファイルのデータ<br> | 概要アクセスファイルのデータ<br> | 概要アクセスファイルのデータ<br> | 概要アクセスファイルのデータ<br> |
|--- |--- |--- |---|---|---|---|---|
| **名前空間／ID** | **expandIDs** |  | **MyProp1** | **訪問者 ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | デバイス | 変数が存在しない | 77 | 変数が存在しない | M、P | X、W |
| AAID=77 | true | デバイス | 変数が存在しない | 77 | 変数が存在しない | M、P | X、W |
| user=Mary | false | ユーザー | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | ユーザー | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | デバイス | 存在しない | 77、88 | 存在しない | N、P | U、W |
| user=MaryAAID=66 | true | ユーザー | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=MaryAAID=66 | true | デバイス | 存在しない | 66、77、88 | 存在しない | N、P | U、W、Z |
| xyz=X | false | デバイス | 存在しない | 55、77 | 存在しない | M、R | X |
| xyz=X | true | デバイス | 存在しない | 55、77 | 存在しない | M、P、R | W、X |

Cookie ID が使用されている場合、expandIDs の設定は出力に影響しないことに注意してください。

## 削除要求のサンプル

表の最初の行にある API の値を使用した削除要求の場合、ヒットの表は以下のように更新されます。

| AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | Privacy-7398 | Privacy-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | Privacy-1866 | Privacy-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

> [!NOTE]AAID = 77 および DEL-DEVICE ラベルを含む行のセルのみが影響を受けます。

| user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-0523 | 77 | Privacy-1866 | Privacy-3681 | X |
| Privacy-0523 | 88 | Privacy-2178 | Privacy-1975 | Y |
| Privacy-0523 | 99 | Privacy-9045 | Privacy-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

> [!NOTE]user=Mary および DEL-PERSON ラベルを含む行のセルのみが影響を受けます。また、実際は、A_ID を含む変数は、おそらく prop または eVar で、その置き換える値は、数値を異なるランダムな数値で置き換えるのではなく、「GDPR-」で始まり、乱数（GUID）が続く文字列です。

| user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-5782 | 09 | Privacy-0859 | Privacy-8183 | Privacy-9152 |
| Privacy-5782 | 16 | Privacy-6104 | Privacy-2911 | Privacy-6821 |
| Privacy-5782 | 83 | Privacy-2714 | Privacy-0219 | Privacy-4395 |
| John | 09 | D | Privacy-8454 | Privacy-8216 |
| John | 16 | E | Privacy-2911 | Privacy-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

以下のことに注意してください。

* `user=Mary`、および `DEL-DEVICE` または `DEL-PERSON` ラベルを含む行のセルが影響を受けます。また、`user=Mary` を含む行にある訪問者 ID を含む行の `DEL-DEVICE` ラベルの付いたセルも影響を受けます。
* `MyEvar2`4 番目および 5 番目の行には、最初および 番目の行と同じ Visitor ID 値が含まれているので、これらの行の 2 は更新されます。そのため、これらは、デバイスレベルの削除用に、ID 拡張に含まれます。
* 行 `MyEvar2` および 5 の 2 の値は、削除の前後で一致しますが、削除後は、その行が削除要求の一環として更新されなかったので、最後の行にある値 N と一致しません。
* `MyEvar3` の動作は ID 拡張をおこなわない場合とは非常に異なりますが、これは、ID 拡張をおこなわないとどの `ID-DEVICES` とも一致しないからです。現在は、`AAID` の最初の 5 行が一致します。
