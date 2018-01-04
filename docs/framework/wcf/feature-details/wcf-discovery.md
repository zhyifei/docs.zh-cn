---
title: WCF Discovery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c11daa14a3897b05947dd6f8c3f3be99eb69c377
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-discovery"></a><span data-ttu-id="7f51a-102">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="7f51a-102">WCF Discovery</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="7f51a-103"> 提供了相关支持，使您能够通过使用 WS-Discovery 协议以互操作方式在运行时发现服务。</span><span class="sxs-lookup"><span data-stu-id="7f51a-103"> provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7f51a-104"> 服务可以使用多播消息将自己的可用性公告到网络，也可以公告到发现代理服务器。</span><span class="sxs-lookup"><span data-stu-id="7f51a-104"> services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="7f51a-105">客户端应用程序可以搜索网络或发现代理服务器来查找满足一组条件的服务。</span><span class="sxs-lookup"><span data-stu-id="7f51a-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="7f51a-106">本节中的主题分别概述和详细介绍了此功能的编程模型。</span><span class="sxs-lookup"><span data-stu-id="7f51a-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f51a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="7f51a-107">In This Section</span></span>  
 [<span data-ttu-id="7f51a-108">WCF 发现概述</span><span class="sxs-lookup"><span data-stu-id="7f51a-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="7f51a-109">概述由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的 WS-Discovery 支持。</span><span class="sxs-lookup"><span data-stu-id="7f51a-109">Provides an overview of WS-Discovery support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="7f51a-110">WCF 发现对象模型</span><span class="sxs-lookup"><span data-stu-id="7f51a-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="7f51a-111">描述对象模型中的类和 WS-Discovery 支持的扩展性。</span><span class="sxs-lookup"><span data-stu-id="7f51a-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="7f51a-112">如何：以编程方式向 WCF 服务和客户端添加可发现性</span><span class="sxs-lookup"><span data-stu-id="7f51a-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="7f51a-113">演示如何检测到 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="7f51a-113">Shows how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span>  
  
 [<span data-ttu-id="7f51a-114">实现发现代理</span><span class="sxs-lookup"><span data-stu-id="7f51a-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="7f51a-115">描述一些必需步骤，这些步骤用于实现发现代理、注册到发现代理的可检测服务以及使用发现代理查找可检测服务的客户端。</span><span class="sxs-lookup"><span data-stu-id="7f51a-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="7f51a-116">发现版本控制</span><span class="sxs-lookup"><span data-stu-id="7f51a-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="7f51a-117">简要概述了一些新发现功能的原型实现，</span><span class="sxs-lookup"><span data-stu-id="7f51a-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="7f51a-118">还概述了如何选择要使用的发现版本。</span><span class="sxs-lookup"><span data-stu-id="7f51a-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="7f51a-119">在配置文件中配置发现</span><span class="sxs-lookup"><span data-stu-id="7f51a-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="7f51a-120">演示如何在配置中配置 Discovery。</span><span class="sxs-lookup"><span data-stu-id="7f51a-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="7f51a-121">使用发现客户端通道</span><span class="sxs-lookup"><span data-stu-id="7f51a-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="7f51a-122">演示在编写 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端应用程序时如何使用 Discovery 客户端通道。</span><span class="sxs-lookup"><span data-stu-id="7f51a-122">Shows how to use a Discovery Client Channel when writing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span>
