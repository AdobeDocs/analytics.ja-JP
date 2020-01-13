---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomainPeriods

変数は、ページ URL のドメイン内のピリオド数を指定することで、[!DNL Analytics] の cookie である `s_cc` と `s_sq` を設定するドメインを決定します。この変数は、一部のプラグインで、プラグインの cookie を設定するための適切なドメインを決定する際にも使用されます。

*`cookieDomainPeriods`* のデフォルト値は「2」です。この値は、*`cookieDomainPeriods`* が省略された場合に使用されます。例えば、ドメイン`www.mysite.com`*`cookieDomainPeriods`を使用する場合、* は「2」にする必要があります。`www.mysite.co.jp` の場合、*`cookieDomainPeriods`* は「3」にする必要があります。

*`cookieDomainPeriods`* が「2」で、ドメインに 3 つのピリオドが含まれている場合、JavaScript ファイルはドメインのサフィックスに対して cookie を設定しようとします。

例えば、*`cookieDomainPeriods`* が `www.mysite.co.jp` ドメインで「2」に設定され、`s_cc` および `s_sq` cookies はドメイン `co.jp` 上で作成されます。`co.jp` は無効なドメインであるので、ほぼすべてのブラウザーでこれらの cookie が拒否されます。その結果、訪問者クリックマップ用のデータが消失し、[!UICONTROL 訪問者プロファイル]／[!UICONTROL 技術]／[!UICONTROL cookie] レポートに、ほぼ 100 ％の訪問者から cookie が拒否されたと示されます。

*`cookieDomainPeriods`* が「3」で、ドメインにピリオドが 2 つだけ含まれている場合、JavaScript ファイルはサイトのサブドメインに対して cookie を設定します。例えば、*`cookieDomainPeriods`* が `www2.mysite.com` ドメインで「3」に設定され、`s_cc` および `s_sq` cookies はドメイン `www2.mysite.com` 上で作成されます。訪問者がサイトの別のサブドメイン（`www4.mysite.com` など）に移動した場合、`www2.mysite.com` によって設定されたすべての cookie を読み取ることができなくなります。

> [!NOTE]*`cookieDomainPeriods`* の一部に追加のサブドメインを含めないでください。例えば、`store.toys.mysite.com` の場合、*`cookieDomainPeriods`* は引き続き「2」に設定されます。この変数定義によって、ルートドメイン [!DNL mysite.com] に対して cookie が正しく設定されます。*`cookieDomainPeriods`* を「3」に設定すると、[!DNL toys.mysite.com] ドメインに対して cookie が設定されるようになります。これは、前述の例と同様です。

「[s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)」も参照してください。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | CDP | 訪問者 ID の保存方法と処理方法を制御するため、複数のレポートに影響します。 | "2" |

>[!NOTE]
>
>一部のクラウドコンピューティングサービスはトップレベルドメインと見なされ、Cookie を書き込むことができません（`*.googlecode.com`、`compute.amazonaws.com`、`*.herokuapp.com` など）。これらのサービスに実装すると、お客様の独自のドメインを設定していない場合（導入をテストする場合など）に、すべての Cookie をブロックしているユーザーを削除する Analytics のプライバシー設定による影響が生じることがあります。その場合は、システムによって Cookie が無効化されている、機能していないまたはアクセスできないと判断されたヒットは、すべてオプトアウトされるので、レポートからは除外されます。

## 例

変数を手動で設定します。

```js
s.cookieDomainPeriods = "3";
```

コア JavaScript ファイルで両方のタイプをホストしている場合に、変数を動的に設定するいくつかの例を示します。

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## 注意事項、質問、ヒント

* 訪問者クリックマップ用のデータがないことに気付いた場合、または[!UICONTROL トラフィック]／[!UICONTROL 技術]／[!UICONTROL cookie] レポートで、大部分の訪問者が cookie を拒否していることを示している場合は、*`cookieDomainPeriods`* の値が正しいことを確認します。

* *`cookieDomainPeriods`* がドメインのセクション数より多い場合、cookie はフルドメインに設定されます。この設定により、訪問者がサブドメインを切り替えたときにデータが消失する可能性があります。
* *`cookieDomainPeriods`* 変数は、*`trackingServer`* を訪問者 ID cookie に設定する前の、非推奨となった実装に使用されていました。この変数は古いコードにしか存在していませんが、この状況で.*`cookieDomainPeriods`* が正しく定義されていない場合、実装でデータを失うリスクが発生します。
