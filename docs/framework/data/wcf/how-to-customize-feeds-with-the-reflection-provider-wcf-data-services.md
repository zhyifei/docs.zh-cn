---
title: 如何：使用反射提供程序 （WCF 数据服务） 自定义源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: f09c9827498dfd6b85a8476e824d06bfb481d1f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876546"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="ecf12-102">如何：使用反射提供程序 （WCF 数据服务） 自定义源</span><span class="sxs-lookup"><span data-stu-id="ecf12-102">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="ecf12-103">使您可以在数据服务响应中自定义 Atom 序列化，以便可以将实体属性映射到在 AtomPub 协议中定义的未使用的元素。</span><span class="sxs-lookup"><span data-stu-id="ecf12-103">enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="ecf12-104">本主题演示如何为使用反射提供程序定义的数据模型中的实体类型定义映射特性。</span><span class="sxs-lookup"><span data-stu-id="ecf12-104">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="ecf12-105">有关详细信息，请参阅[馈送的自定义](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf12-105">For more information, see [Feed Customization](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="ecf12-106">主题中定义此示例中的数据模型[如何：创建数据服务使用反射提供程序](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="ecf12-106">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecf12-107">示例</span><span class="sxs-lookup"><span data-stu-id="ecf12-107">Example</span></span>  
 <span data-ttu-id="ecf12-108">在以下示例中，`Order` 类型的两个属性均映射到现有的 Atom 元素。</span><span class="sxs-lookup"><span data-stu-id="ecf12-108">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="ecf12-109">`Product` 类型的 `Item` 属性映射到单独的命名空间中的自定义源特性。</span><span class="sxs-lookup"><span data-stu-id="ecf12-109">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="ecf12-110">示例</span><span class="sxs-lookup"><span data-stu-id="ecf12-110">Example</span></span>  
 <span data-ttu-id="ecf12-111">上面的示例为 URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` 返回以下结果。</span><span class="sxs-lookup"><span data-stu-id="ecf12-111">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="ecf12-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecf12-112">See also</span></span>

- [<span data-ttu-id="ecf12-113">反射提供程序</span><span class="sxs-lookup"><span data-stu-id="ecf12-113">Reflection Provider</span></span>](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
