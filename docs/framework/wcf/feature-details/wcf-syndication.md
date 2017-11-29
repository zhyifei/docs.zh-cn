---
title: "WCF 联合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 51cf7c6e4db1ee0ff68bcc7fccb46fd643f04bf4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-syndication"></a><span data-ttu-id="499ce-102">WCF 联合</span><span class="sxs-lookup"><span data-stu-id="499ce-102">WCF Syndication</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="499ce-103"> 提供的支持可以轻松处理 Atom、RSS 或其他自定义格式的联合源，从而允许用户读取和创建这些联合源，还可以将它们公开为服务终结点。</span><span class="sxs-lookup"><span data-stu-id="499ce-103"> provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="499ce-104">本节中的主题详细描述用于联合的此种编程模型。</span><span class="sxs-lookup"><span data-stu-id="499ce-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="499ce-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="499ce-105">In This Section</span></span>  
 [<span data-ttu-id="499ce-106">WCF 联合概述</span><span class="sxs-lookup"><span data-stu-id="499ce-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="499ce-107">概述由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的联合支持。</span><span class="sxs-lookup"><span data-stu-id="499ce-107">Provides an overview of syndication support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="499ce-108">联合体系结构</span><span class="sxs-lookup"><span data-stu-id="499ce-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="499ce-109">描述对象模型中的类和联合的扩展性。</span><span class="sxs-lookup"><span data-stu-id="499ce-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="499ce-110">WCF 联合对象模型如何映射到 Atom 和 RSS</span><span class="sxs-lookup"><span data-stu-id="499ce-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="499ce-111">描述源在 WCF 联合对象模型中的表示方式以及如何将它们转换为 RSS 和 Atom 源。</span><span class="sxs-lookup"><span data-stu-id="499ce-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="499ce-112">如何： 创建基本 RSS 源</span><span class="sxs-lookup"><span data-stu-id="499ce-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="499ce-113">演示如何创建可使基本 RSS 源可用的服务。</span><span class="sxs-lookup"><span data-stu-id="499ce-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="499ce-114">如何： 创建基本 Atom 馈送</span><span class="sxs-lookup"><span data-stu-id="499ce-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="499ce-115">演示如何创建可使基本 ATOM 源可用的服务。</span><span class="sxs-lookup"><span data-stu-id="499ce-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="499ce-116">如何： 公开源作为 Atom 和 RSS</span><span class="sxs-lookup"><span data-stu-id="499ce-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="499ce-117">演示如何创建可将同一个源用于 ATOM 和 RSS 的服务。</span><span class="sxs-lookup"><span data-stu-id="499ce-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="499ce-118">联合扩展性</span><span class="sxs-lookup"><span data-stu-id="499ce-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="499ce-119">描述向联合源添加自定义元素和属性的方法。</span><span class="sxs-lookup"><span data-stu-id="499ce-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="499ce-120">参考</span><span class="sxs-lookup"><span data-stu-id="499ce-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="499ce-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="499ce-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499ce-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="499ce-122">See Also</span></span>  
 [<span data-ttu-id="499ce-123">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="499ce-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="499ce-124">部分信任</span><span class="sxs-lookup"><span data-stu-id="499ce-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
