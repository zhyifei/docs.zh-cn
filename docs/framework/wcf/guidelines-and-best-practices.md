---
title: 指南与最佳做法
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, guidelines
- best practices [WCF], application design
- Windows Communication Foundation, best practices
- WCF, best practices
- Windows Communication Foundation, guidelines
ms.assetid: 5098ba46-6e8d-4e02-b0c5-d737f9fdad84
ms.openlocfilehash: 37e014aad44cf15e04ed3aa03a8367f5a44ceb96
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319801"
---
# <a name="guidelines-and-best-practices"></a><span data-ttu-id="72977-102">指南与最佳做法</span><span class="sxs-lookup"><span data-stu-id="72977-102">Guidelines and Best Practices</span></span>
<span data-ttu-id="72977-103">本部分包含的主题提供了有关创建 Windows Communication Foundation （WCF）应用程序的准则。</span><span class="sxs-lookup"><span data-stu-id="72977-103">This section contains topics that provide guidelines for creating Windows Communication Foundation (WCF) applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72977-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="72977-104">In This Section</span></span>  
 [<span data-ttu-id="72977-105">最佳做法：数据协定版本控制</span><span class="sxs-lookup"><span data-stu-id="72977-105">Best Practices: Data Contract Versioning</span></span>](best-practices-data-contract-versioning.md)  
 <span data-ttu-id="72977-106">说明如何以及何时创建数据协定，使其在更高版本被创建之后不会失效。</span><span class="sxs-lookup"><span data-stu-id="72977-106">Explains how and when to create data contracts that do not break when future versions are created.</span></span>  
  
 [<span data-ttu-id="72977-107">服务版本控制</span><span class="sxs-lookup"><span data-stu-id="72977-107">Service Versioning</span></span>](service-versioning.md)  
 <span data-ttu-id="72977-108">说明如何在 WCF 中考虑版本控制。</span><span class="sxs-lookup"><span data-stu-id="72977-108">Explains how to consider versioning in WCF.</span></span> <span data-ttu-id="72977-109">服务（及其公开的终结点）部署之后，可能需要进行更改以达到某些要求，例如，满足不断变化的业务需求或 IT 需求，或者解决问题。</span><span class="sxs-lookup"><span data-stu-id="72977-109">After deployment, services (and the endpoints they expose) might need to be changed, for example, to satisfy changing business requirements or IT requirements, or to fix issues.</span></span> <span data-ttu-id="72977-110">每次更改都会引入服务的一个新版本。</span><span class="sxs-lookup"><span data-stu-id="72977-110">Each change introduces a new version of the service.</span></span>  
  
 [<span data-ttu-id="72977-111">负载均衡</span><span class="sxs-lookup"><span data-stu-id="72977-111">Load Balancing</span></span>](load-balancing.md)  
 <span data-ttu-id="72977-112">列出使用网络场实现负载平衡的准则。</span><span class="sxs-lookup"><span data-stu-id="72977-112">Lists guidelines for load balancing with a Web farm.</span></span>  
  
 [<span data-ttu-id="72977-113">控制资源消耗并提升性能</span><span class="sxs-lookup"><span data-stu-id="72977-113">Controlling Resource Consumption and Improving Performance</span></span>](controlling-resource-consumption-and-improving-performance.md)  
 <span data-ttu-id="72977-114">描述专门用于帮助防止过度消耗资源和提高安全性的属性，并提供指向有关其用法的更详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="72977-114">Describes the properties that are designed to help prevent undue resource consumption and improve security and points to more complete information about their use.</span></span>  
  
 [<span data-ttu-id="72977-115">使用 ClickOnce 部署 WCF 应用程序</span><span class="sxs-lookup"><span data-stu-id="72977-115">Deploying WCF Applications with ClickOnce</span></span>](deploying-wcf-applications-with-clickonce.md)  
 <span data-ttu-id="72977-116">描述使用 ClickOnce 功能时的注意事项。</span><span class="sxs-lookup"><span data-stu-id="72977-116">Describes the considerations to be made when using the ClickOnce feature.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="72977-117">参考</span><span class="sxs-lookup"><span data-stu-id="72977-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="72977-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="72977-118">Related Sections</span></span>  
 [<span data-ttu-id="72977-119">概念性概述</span><span class="sxs-lookup"><span data-stu-id="72977-119">Conceptual Overview</span></span>](conceptual-overview.md)  
  
 [<span data-ttu-id="72977-120">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="72977-120">Basic WCF Programming</span></span>](basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="72977-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="72977-121">See also</span></span>

- [<span data-ttu-id="72977-122">什么是 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="72977-122">What Is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="72977-123">Windows Communication Foundation （WCF）示例</span><span class="sxs-lookup"><span data-stu-id="72977-123">Windows Communication Foundation (WCF) samples</span></span>](./samples/index.md)
- [<span data-ttu-id="72977-124">概念性概述</span><span class="sxs-lookup"><span data-stu-id="72977-124">Conceptual Overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="72977-125">生成客户端</span><span class="sxs-lookup"><span data-stu-id="72977-125">Building Clients</span></span>](building-clients.md)
