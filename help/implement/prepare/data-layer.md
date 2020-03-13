---
title: データレイヤーの作成
description: Analytics の実装におけるデータレイヤーと、それらを Adobe Analytics で変数のマッピングに使用する方法について説明します。
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# データレイヤーの作成

データレイヤーは、サイト上のJavaScriptオブジェクトのフレームワークで、実装で使用されるすべての変数値を含みます。 これにより、導入の管理とメンテナンスが容易になります。

## 前提条件

[ソリューションデザインドキュメントの作成](solution-design.md) — 組織がトラッキング要件に合わせて調整することが重要です。 組織の開発チームに近づく前に、ソリューションデザインドキュメントの準備が整っていることを確認します。

## ワークフロー

データレイヤーを使用してAdobe Analyticsを実装する場合は、通常、次の手順に従います。

1. **サイト開発チームと協力して、データレイヤーを実装します**。サイト開発チームは主に、データレイヤーオブジェクトに正しい値が入力されることを確認する必要があります。 サイト開発チームとこのページを見直し、チーム間で期待値が一致することを確認します。
   > [!NOTE] アドビ推奨のデータレイヤー仕様に従うことはオプションです。 データレイヤーが既に存在する場合、またはアドビの仕様に従わない場合は、組織が従うべき仕様に従っていることを確認します。
2. **ブラウザーコンソールを使用して、データレイヤーを検証します**。データレイヤーが作成されたら、任意のブラウザーの開発者コンソールを使用して、データレイヤーが機能していることを検証できます。 デベロッパーコンソールは、キーを使用して、ほとんどのブラウザーで開くことが `F12` できます。 変数の値の例を次に示します `digitalData.page.pageInfo.pageID`。
3. **Adobe Experience Platform Launchを使用して、データレイヤーオブジェクトをLaunchデータ要素にマップします**。「起動」でデータ要素を作成し、データレイヤーで概要を示すJavaScript属性にマップします。
4. **起動のAdobe Analytics拡張機能を使用して、データ要素をAnalytics変数にマップします**。ソリューションデザインドキュメントに従って、各データ要素を適切なAnalytics変数に割り当てます。

## 仕様

アドビでは、 [Customer Experience Digital Data Community Groupで概要を説明している](https://www.w3.org/2013/12/ceddl-201312.pdf) 「Customer Experience Digital Data Layer」 [をフォローすることをお勧めします](https://www.w3.org/community/custexpdata/)。 次の節では、データレイヤー要素とAdobe Analyticsとの関わり方について説明します。

使用するデータレイヤーオブジェクトのオーバーチ処理は、を推奨しま `digitalData`す。 次の例は、ある程度包括的なデータレイヤーJSONオブジェクトとサンプル値を示しています。

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory1: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product1: {
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    },
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event1: {
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    component1: {
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    user1: {
        segment: "Premium membership",
        profile1: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }
    },
    privacy: {
        accessCategories1: {
            categoryName: "Default",
            domains: "adobedtm.com"
        }
    },
    version: "1.0"
}
```

各オブジェクト [とサブオブジェクトの詳細については、](https://www.w3.org/2013/12/ceddl-201312.pdf) 「顧客体験デジタルデータレイヤー」レポートを使用します。 すべてのサイトですべてのオブジェクトを使用しているわけではありません。例えば、ニュースサイトをホストする場合、そのオブジェクトを使用する可能性は低くな `digitalData.product` ります。

データ層は拡張可能で、組織に固有の要件がある場合は、その要件に対応するためにオブジェクトをデータレイヤーに含めることができます。

## データレイヤー値の設定

通常、データレイヤーはサーバー側を生成し、サイトコンテンツの構築に使用したのと同じオブジェクトを参照します。 組織のソリューションデザインドキュメントで設定された追跡要件に基づいて、サイトのデータレイ [ヤーを確立します](solution-design.md)。

## 次の手順

[データレイヤーオブジェクトのデータ要素へのマップ](../launch/layer-to-elements.md):Adobe Experience Platform Launchでサイトのデータレイヤーを使用します。
