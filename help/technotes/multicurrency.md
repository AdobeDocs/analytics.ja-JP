---
description: 複数通貨のサポートを有効にするためにターゲット通貨コードを定義する方法について説明します。
title: 複数通貨のサポート
uuid: null
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f3eb3c024a80d0b65729929960173f8b3a4267b0
workflow-type: tm+mt
source-wordcount: '1358'
ht-degree: 100%

---

# 複数通貨のサポート

このドキュメントでは、複数通貨のサポートを有効にするためにターゲット通貨コードを定義する方法について説明します。

ターゲット通貨コードは、次の 3 つのレベルで定義されます。

## ページレベル

ターゲット通貨の JavaScript 変数は、ページレベルで設定できます。サイトの所有者は、（このドキュメントで以下に示すとおり）この変数を適切な 3 文字の ISO 4217 通貨コードで設定します。[currencyCode](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/vars/config-vars/currencycode.html) 変数がこのレベルで設定されていない場合、デフォルトの通貨はレポートスイートで指定された通貨と同じになります。ページレベルの変数がレポートスイートで指定された変数と競合する場合は、レポートスイートの変数が優先されます。


## レポートスイートレベル

**ベース通貨**&#x200B;は、[レポートスイートの作成](https://docs.adobe.com/content/help/ja-JP/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html)時に指定されます。これは通貨のデフォルト設定で、ページレベルで設定された通貨コードよりも優先されます。したがって、レポートスイートにアメリカドル、ユーロ、イギリスポンドを受け付ける注文が含まれていて、レポートスイートのデフォルトの通貨コードが「アメリカドル」に設定されている場合、レポートのバックエンドデータベースがすべてのトランザクションをアメリカドルに変換します。

マーケティングレポートでは、イメージリクエストが発生した時点の為替レートを使用して、ページレベルの通貨価値をレポートスイートのデフォルトの通貨価値に変換します。レポートスイートは、「アメリカドル」をデフォルトの通貨として使用します。


## レポートレベル

ユーザーは、ユーザーログインセッションのためにデフォルトのレポート通貨を設定できます。これには、任意のコンバージョンレポートの&#x200B;**表示オプション**&#x200B;リンクを通してアクセスできます。マーケティングレポートでは、レポートが実行された時点の為替レートを使用して、レポートスイートの通貨価値を、レポートの指定する通貨価値に変換します。

## サポートされる通貨コード（ISO 4217）

Analytics では現在、次の通貨形式のトランザクション変換をサポートしています。


「AFA」アフガニスタン アフガニ（AFA）

「AFN」アフガニスタン アフガニ（AFN）

「ALL」アルバニア レク（ALL）

「DZD」アルジェリア ディナール（DZD）

「AOA」アンゴラ クワンザ（AOA）

「ARS」アルゼンチン ペソ（ARS）

「AMD」アルメニア ドラム（AMD）

「AWG」アルバ ギルダー（AWG）

「AUD」オーストラリア ドル（AUD）

「AZM」アゼルバイジャン マナト（AZM）

「AZN」アゼルバイジャン ニューマナト（AZN）

「BSD」バハマ ドル（BSD）

「BHD」バーレーン ディナール（BHD）

「BDT」バングラデシュ タカ（BDT）

「BBD」バルバドス ドル（BBD）

「BYR」ベラルーシ ルーブル（BYR）

「BZD」ベリーズ ドル（BZD）

「BMD」バミューダ ドル（BMD）

「BTN」ブータン ニュルタム（BTN）

「BOB」ボリビア ボリビアーノ（BOB）

「BAM」ボスニアヘルツェゴビナ 兌換マルク（BAM）

「BWP」ボツワナ プラ（BWP）

「BRL」ブラジル レアル（BRL）

「BND」ブルネイ ドル（BND）

「BGN」ブルガリア レフ（BGN）

「BIF」ブルンジ フラン（BIF）

「KHR」カンボジア リエル（KHR）

「CAD」カナダ ドル（CAD）

「CVE」カーボベルデ エスクード（CVE）

「KYD」ケイマン諸島 ドル（KYD）

「CLP」チリ ペソ（CLP）

「CNY」中国元（人民幣）（CNY）

「COP」コロンビア ペソ（COP）

「XOF」アフリカ金融共同体（BCEAO） CFA フラン（XOF）

「XAF」アフリカ金融共同体（BEAC） CFA フラン（XAF）

「KMF」コモロ フラン（KMF）

「XPF」CFP フラン（XPF）

「CDF」コンゴ／キンシャサ フラン（CDF）

「CRC」コスタリカ コロン（CRC）

「HRK」クロアチア クーナ（HRK）

「CUC」キューバ 兌換ペソ（CUC）

「CUP」キューバ ペソ（CUP）

「CYP」キプロス ポンド（CYP）

「CZK」チェコ共和国 コルナ（CZK）

「DKK」デンマーク クローネ（DKK）

「DJF」ジブチ フラン（DJF）

「DOP」ドミニカ共和国 ペソ（DOP）

「XCD」東カリブ ドル（XCD）

「EGP」エジプト ポンド（EGP）

「SVC」エルサルバドル コロン（SVC）

「ERN」エリトリア ナクファ（ERN）

「XBT」ERR（XBT）

「EEK」エストニア クローン（EEK）

「ETB」エチオピア ブル（ETB）

「EUR」ユーロ（EUR）

「FKP」フォークランド諸島 ポンド（FKP）

「FJD」フィジー ドル（FJD）

「GMD」ガンビア ダラシ（GMD）

「GEL」グルジア ラリ（GEL）

「GHC」ガーナ セディ（GHC）

「GHS」ガーナ セディ（GHS）

「GIP」ジブラルタル ポンド（GIP）

「XAU」金オンス（XAU）

「GTQ」グアテマラ ケツァル（GTQ）

「GGP」ガーンジー ポンド（GGP）

「GNF」ギニア フラン（GNF）

「GYD」ガイアナ ドル（GYD）

「HTG」ハイチ グールド（HTG）

「HNL」ホンジュラス レンピラ（HNL）

「HKD」香港ドル（HKD）

「HUF」ハンガリー フォリント（HUF）

「ISK」アイスランド クローナ（ISK）

「INR」インド ルピー（INR）

「IDR」インドネシア ルピア（IDR）

「XDR」国際通貨基金特別引き出し権（XDR）

「IRR」イラン リアル（IRR）

「IQD」イラク ディナール（IQD）

「IMP」マン島 ポンド（IMP）

「ILS」イスラエル 新シェケル（ILS）

「JMD」ジャマイカ ドル（JMD）

「JPY」日本円（JPY）

「JEP」ジャージー ポンド（JEP）

「JOD」ヨルダン ディナール（JOD）

「KZT」カザフスタン テンゲ（KZT）

「KES」ケニア シリング（KES）

「KWD」クウェート ディナール（KWD）

「KGS」キルギス ソム（KGS）

「LAK」ラオス キープ（LAK）

「LVL」ラトビア ラティ（LVL）

「LBP」レバノン ポンド（LBP）

「LSL」レソト ロチ（LSL）

「LRD」リベリア ドル（LRD）

「LYD」リビア ディナール（LYD）

「LTL」リトアニア リタス（LTL）

「MOP」マカオ パタカ（MOP）

「MKD」マケドニア デナル（MKD）

「MGA」マダガスカル アリアリ（MGA）

「MWK」マラウイ クワチャ（MWK）

「MYR」マレーシア リンギット（MYR）

「MVR」モルディブ ルフィア（MVR）

「MTL」マルタ リラ（MTL）

「MRO」モーリタニア ウギア（MRO）

「MUR」モーリシャス ルピー（MUR）

「MXN」メキシコ ペソ（MXN）

「MDL」モルドバ レウ（MDL）

「MNT」モンゴル トゥグルグ（MNT）

「MAD」モロッコ ディルハム（MAD）

「MZN」モザンビーク メティカル（MZN）

「MZM」モザンビーク メティカル（MZM）

「MMK」ミャンマー チャット（MMK）

「NAD」ナミビア ドル（NAD）

「NPR」ネパール ルピー（NPR）

「ANG」オランダ領アンティル ギルダー（ANG）

「NZD」ニュージーランド ドル（NZD）

「NIO」ニカラグア コルドバ（NIO）

「NGN」ナイジェリア ナイラ（NGN）

「KPW」北朝鮮ウォン（KPW）

「NOK」ノルウェー クローネ（NOK）

「OMR」オマーン リアル（OMR）

「PKR」パキスタン ルピー（PKR）

「XPD」パラジウムオンス（XPD）

「PAB」パナマ バルボア（PAB）

「PGK」パプアニューギニア キナ（PGK）

「PYG」パラグアイ グアラニー（PYG）

「PEN」ペルー ヌエボソル（PEN）

「PHP」フィリピン ペソ（PHP）

「XPT」プラチナオンス（XPT）

「PLN」ポーランド ズウォティ（PLN）

「QAR」カタール リヤル（QAR）

「ROL」ルーマニア レウ（ROL）

「RON」ルーマニア ニューレウ（RON）

「RUB」ロシア ルーブル（RUB）

「RUR」ロシア ルーブル（RUR）

「RWF」ルワンダ フラン（RWF）

「SHP」セントヘレナ ポンド（SHP）

「WST」サモア タラ（WST）

「STD」サントメプリンシペ ドブラ（STD）

「SAR」サウジアラビア リヤル（SAR）

「SPL」セボルガ ルイジーノ（SPL）

「RSD」セルビア ディナール（RSD）

「CSD」セルビア ディナール（CSD）

「SCR」セーシェル ルピー（SCR）

「SLL」シエラレオネ レオン（SLL）

「XAG」銀オンス（XAG）

「SGD」シンガポール ドル（SGD）

「SKK」スロバキア コルナ（SKK）

「SIT」スロベニア トラール（SIT）

「SBD」ソロモン諸島 ドル（SBD）

「SOS」ソマリア シリング（SOS）

「ZAR」南アフリカ ランド（ZAR）

「KRW」韓国ウォン（KRW）

「LKR」スリランカ ルピー（LKR）

「SDD」スーダン ディナール（SDD）

「SDG」スーダン ポンド（SDG）

「SRD」スリナム ドル（SRD）

「SRG」スリナム ギルダー（SRG）

「SZL」スワジランド リランゲニ（SZL）

「SEK」スウェーデン クローナ（SEK）

「CHF」スイス フラン（CHF）

「SYP」シリア ポンド（SYP）

「TWD」新台湾ドル（TWD）

「TJS」タジキスタン ソモニ（TJS）

「TZS」タンザニア シリング（TZS）

「THB」タイ バーツ（THB）

「TOP」トンガ パアンガ（TOP）

「TTD」トリニダードトバゴ ドル（TTD）

「TND」チュニジア ディナール（TND）

「TRY」トルコ リラ（TRY）

「TRL」トルコ リラ（TRL）

「TMM」トルクメニスタン マナト（TMM）

「TMT」トルクメニスタン ニューマナト（TMT）

「TVD」ツバル ドル（TVD）

「UGX」ウガンダ シリング（UGX）

「UAH」ウクライナ フリヴニャ（UAH）

「AED」アラブ首長国連邦 ディルハム（AED）

「GBP」イギリス ポンド（GBP）

「USD」アメリカ ドル（USD）

「UYU」ウルグアイ ペソ（UYU）

「UZS」ウズベキスタン スム（UZS）

「VUV」バヌアツ バツ（VUV）

「VEB」ベネズエラ ボリバル（VEB）

「VEF」ベネズエラ ボリバルフエルテ（VEF）

「VND」ベトナム ドン（VND）

「YER」イエメン リアル（YER）

「ZMK」ザンビア クワチャ（ZMK）

「ZMW」ザンビア クワチャ（ZMW）

「ZWD」ジンバブエ ドル（ZWD）


## AppMeasurement.js の例

`currencyCode` 変数は、AppMeasurement.js ファイル内でグローバルに定義できます。このファイルで currencyCode 変数を定義すると、すべての通貨トランザクションで同一の通貨コードが使用されるようになります。次の例では、AppMeasurement.js ファイルの `CONFIG SECTION` における `currencyCode` 変数としてユーロを指定しています。すべての購入イベントは、レポートでは「ユーロ」トランザクションとして解釈されます。

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
s.account="devnow"
s.currencyCode="EUR"
s.trackInlineStats=true 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
***
    
```

## 追加の導入時の注意

* 通貨コードはページ間で変換できますが、あるページリクエストで定義されたすべてのコンバージョン行項目は、同じ通貨を使用する必要があることに注意してください（例えば、同じページビューにユーロ、イギリスポンド、アメリカドルを定義することはできません）。通貨換算をおこなわない場合は、currencyCode 値を空白にしておく必要があります。これにより、値が変換されることなく直接レポートに渡されます。

* 無効な currencyCode（サポートされている通貨コードリストにない値）を設定すると、ヒット全体が除外され、そのトランザクションに関するデータは収集されません。実稼働環境に `currencyCode` を設定する前に、テスト用のレポートスイートを使用して、データが正常に収集され、通貨換算が正しいことを確認します。

* セパレーターとしてピリオド（.）を使用しない通貨は、通常のセパレーターの代わりにピリオドを使用するように変更する必要があります。例えば、コンマ（,）を使用するスウェーデン クローナは、コンマの代わりにピリオドを使用するように変更する必要があります。Analytics ではコンマは値を区切るのに使用されるので、データが適切に渡されなくなります。ピリオドを使用することで、レポートに値を正しく渡すことができます。
