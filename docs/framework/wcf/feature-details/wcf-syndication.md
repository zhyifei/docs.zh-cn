---
title: "WCF 联合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1f7f5fd65fc298107a66e2049c059f3cc58b3d44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-syndication"></a><span data-ttu-id="96c60-102">WCF 联合</span><span class="sxs-lookup"><span data-stu-id="96c60-102">WCF Syndication</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="96c60-103"> 提供的支持可以轻松处理 Atom、RSS 或其他自定义格式的联合源，从而允许用户读取和创建这些联合源，还可以将它们公开为服务终结点。</span><span class="sxs-lookup"><span data-stu-id="96c60-103"> provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="96c60-104">本节中的主题详细描述用于联合的此种编程模型。</span><span class="sxs-lookup"><span data-stu-id="96c60-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96c60-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="96c60-105">In This Section</span></span>  
 [<span data-ttu-id="96c60-106">WCF 联合概述</span><span class="sxs-lookup"><span data-stu-id="96c60-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="96c60-107">概述由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的联合支持。</span><span class="sxs-lookup"><span data-stu-id="96c60-107">Provides an overview of syndication support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="96c60-108">联合体系结构</span><span class="sxs-lookup"><span data-stu-id="96c60-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="96c60-109">描述对象模型中的类和联合的扩展性。</span><span class="sxs-lookup"><span data-stu-id="96c60-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="96c60-110">WCF 联合对象模型如何映射到 Atom 和 RSS</span><span class="sxs-lookup"><span data-stu-id="96c60-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="96c60-111">描述源在 WCF 联合对象模型中的表示方式以及如何将它们转换为 RSS 和 Atom 源。</span><span class="sxs-lookup"><span data-stu-id="96c60-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="96c60-112">如何：创建基本 RSS 源</span><span class="sxs-lookup"><span data-stu-id="96c60-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="96c60-113">演示如何创建可使基本 RSS 源可用的服务。</span><span class="sxs-lookup"><span data-stu-id="96c60-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="96c60-114">如何：创建基本 Atom 源</span><span class="sxs-lookup"><span data-stu-id="96c60-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="96c60-115">演示如何创建可使基本 ATOM 源可用的服务。</span><span class="sxs-lookup"><span data-stu-id="96c60-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="96c60-116">如何：公开作为 Atom 和 RSS 的源</span><span class="sxs-lookup"><span data-stu-id="96c60-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="96c60-117">演示如何创建可将同一个源用于 ATOM 和 RSS 的服务。</span><span class="sxs-lookup"><span data-stu-id="96c60-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="96c60-118">联合扩展性</span><span class="sxs-lookup"><span data-stu-id="96c60-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="96c60-119">描述向联合源添加自定义元素和属性的方法。</span><span class="sxs-lookup"><span data-stu-id="96c60-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="96c60-120">参考</span><span class="sxs-lookup"><span data-stu-id="96c60-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="96c60-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="96c60-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c60-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="96c60-122">See Also</span></span>  
 [<span data-ttu-id="96c60-123">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="96c60-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="96c60-124">部分信任</span><span class="sxs-lookup"><span data-stu-id="96c60-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
