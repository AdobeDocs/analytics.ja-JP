---
description: 'null'
seo-description: 'null'
seo-title: ラベル設定の例
title: ラベル設定の例
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: tm+mt
source-git-commit: d2134271c4586d629c8b25f60c746902ba13683b

---


# ラベル設定の例

## ヒットデータのサンプル

以下のヒットデータがあるとします。

* 最初の行に各変数のラベルが含まれている。
* 2 番目の行は変数の名前である。ID ラベルがある場合は、割り当てられた名前空間が括弧内に含まれている。
* ヒットデータは 3 番目の行から開始する。

| ラベル | I2<br>ID-<br>PERSONDEL-<br>PERSONACC-PERSON | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL | I2<br>DEL-<br>PERSONACC-PERSON | I2<br>DEL-<br>DEVICEDEL-<br>PERSONACC-ALL | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL |
|---|---|---|---|---|---|
| **Variable Name**<br>**(Namespace)** | **MyProp1**<br>**(user)** | **訪問者ID**<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**（xyz）** |
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

| API の値 | API の値 | 返されるファイルタイプ | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File |
|--- |--- |--- |---|---|---|---|---|
| **名前空間／ID** | **expandIDs** |  | **MyProp1** | **訪問者 ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | デバイス | 変数が存在しない | 77 | 変数が存在しない | M、P | X、W |
| AAID=77 | true | デバイス | 変数が存在しない | 77 | 変数が存在しない | M、P | X、W |
| user=Mary | false | ユーザー | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | ユーザー | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | デバイス | 存在しない | 77、88 | 存在しない | N、P | U、W |
| user=Mary AAID=66 | true | ユーザー | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary AAID=66 | true | デバイス | 存在しない | 66、77、88 | 存在しない | N、P | U、W、Z |
| xyz=X | false | デバイス | 存在しない | 55、77 | 存在しない | M、R | X |
| xyz=X | true | デバイス | 存在しない | 55、77 | 存在しない | M、P、R | W、X |

Cookie ID が使用されている場合、expandIDs の設定は出力に影響しないことに注意してください。

## 削除要求のサンプル

表の最初の行にある API の値を使用した削除要求の場合、ヒットの表は以下のように更新されます。

| AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | プライバシー —7398 | プライバシー —9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | プライバシー —1866 | プライバシー —8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] AAID = 77およびDEL-DEVICEラベルを含む行のセルのみが影響を受けます。

| user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| プライバシー —0523 | 77 | プライバシー —1866 | プライバシー —3681 | X |
| プライバシー —0523 | 88 | プライバシー —2178 | プライバシー —1975 | はい |
| プライバシー —0523 | 99 | Privacy-9045 | プライバシー —2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] user=MaryとDEL-PERSONラベルを含む行のセルのみが影響を受けます。 また、実際には、A_IDを含む変数はpropまたはeVarで、その置換値は「プライバシー — 」で始まり、次に乱数(GUID)が続く文字列になり、数値を別の乱数値に置き換えるのではなくなります。

| user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| プライバシー —5782 | 09 | プライバシー —0859 | プライバシー —8183 | プライバシー —9152 |
| プライバシー —5782 | 16 | プライバシー —6104 | プライバシー —2911 | プライバシー —6821 |
| プライバシー —5782 | 83 | プライバシー —2714 | プライバシー —0219 | Privacy-4395 |
| John | 09 | D | Privacy-8454 | プライバシー —8216 |
| John | 16 | E | プライバシー —2911 | プライバシー —2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

以下のことに注意してください。

* Cells on rows containing `user=Mary` and a `DEL-DEVICE` or `DEL-PERSON` label are impacted, as well as cells with a `DEL-DEVICE` label on rows containing any Visitor ID that occurred on a row containing `user=Mary`.
* `MyEvar2`4 番目および 5 番目の行には、最初および 番目の行と同じ Visitor ID 値が含まれているので、これらの行の 2 は更新されます。そのため、これらは、デバイスレベルの削除用に、ID 拡張に含まれます。
* The values of `MyEvar2` in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request.
* `MyEvar3` の動作は ID 拡張をおこなわない場合とは非常に異なりますが、これは、ID 拡張をおこなわないとどの とも一致しないからです。`ID-DEVICES`Now `AAID` matches on the first five rows.
