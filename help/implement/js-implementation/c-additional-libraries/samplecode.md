---
description: HTML サンプルページ内でのサーバー生成イメージタグの使用例を示します。
keywords: Analyticsの導入;変数
seo-description: HTML サンプルページ内でのサーバー生成イメージタグの使用例を示します。
seo-title: サンプルコード
solution: Analytics
title: サンプルコード
topic: 開発者と導入
uuid: 47e5e82c- cfb2-4912-919b-720b2ee852ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# サンプルコード

HTML サンプルページ内でのサーバー生成イメージタグの使用例を示します。

次の表に、サンプルで使用されている値を示します。

| 変数 | 値 |
|---|---|
| pageName | Order Confirmation |
| 現在の URL | https://www.somesite.com/cart/confirmation.asp |
| events | purchase,event1 |
| c1 | Registered |
| purchaseID | 0123456 |
| products | Books;Book Name;1;19.95 |
| state | CA |
| zip | 90210 |
| 乱数 | 123456 |

## 例 1 {#section_91D91CE318AE43F0ADDF6005607E83C7}

次の例は、サーバーサイドのイメージタグを示しています。強調表示された乱数は、イメージのキャッシュを防いでいます。

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<img src="https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS 
<codeph outputclass="syntax">
  /123456?pageName=Order%20 Confirmation&events=purchase%2Cevent1&c1=Registered&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=https%3A//www.somesite.com/cart/confirmation.asp" width="1" height="1" border="0" /> 
 </body> 
 </html> 
  
</codeph outputclass="syntax">
```

## 例 2 {#section_726D12029583428BA853043F988ED1B8}

次の例は、最小限の JavaScript イメージタグを示しています。

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456. 
<script language="javascript"><!— 
s.s_date = new Date(); 
s.s_rdm = s.s_date.getTime(); 
s.s_desturl="<img width=\"1\" height=\"1\" 
src=\"https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS/" + s.s_rdm + 
"?pageName=Order%20Confirmation&events=purchase%2Cevent1&c1=Registered 
&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=http 
s%3A//www.somesite.com/cart/confirmation.asp\">"; 
document.write(s.s_desturl); 
//--></script> 
</body> 
</html> 
```

