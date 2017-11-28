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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fda50f14d9003b81f93840571b8b27f874f7730b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-discovery"></a><span data-ttu-id="93374-102">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="93374-102">WCF Discovery</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="93374-103"> 提供了相关支持，使您能够通过使用 WS-Discovery 协议以互操作方式在运行时发现服务。</span><span class="sxs-lookup"><span data-stu-id="93374-103"> provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="93374-104"> 服务可以使用多播消息将自己的可用性公告到网络，也可以公告到发现代理服务器。</span><span class="sxs-lookup"><span data-stu-id="93374-104"> services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="93374-105">客户端应用程序可以搜索网络或发现代理服务器来查找满足一组条件的服务。</span><span class="sxs-lookup"><span data-stu-id="93374-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="93374-106">本节中的主题分别概述和详细介绍了此功能的编程模型。</span><span class="sxs-lookup"><span data-stu-id="93374-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93374-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="93374-107">In This Section</span></span>  
 [<span data-ttu-id="93374-108">WCF Discovery 概述</span><span class="sxs-lookup"><span data-stu-id="93374-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="93374-109">概述由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的 WS-Discovery 支持。</span><span class="sxs-lookup"><span data-stu-id="93374-109">Provides an overview of WS-Discovery support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="93374-110">WCF Discovery 对象模型</span><span class="sxs-lookup"><span data-stu-id="93374-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="93374-111">描述对象模型中的类和 WS-Discovery 支持的扩展性。</span><span class="sxs-lookup"><span data-stu-id="93374-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="93374-112">如何： 以编程方式向 WCF 服务和客户端添加可发现性</span><span class="sxs-lookup"><span data-stu-id="93374-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="93374-113">演示如何检测到 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="93374-113">Shows how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span>  
  
 [<span data-ttu-id="93374-114">实现发现代理</span><span class="sxs-lookup"><span data-stu-id="93374-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="93374-115">描述一些必需步骤，这些步骤用于实现发现代理、注册到发现代理的可检测服务以及使用发现代理查找可检测服务的客户端。</span><span class="sxs-lookup"><span data-stu-id="93374-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="93374-116">发现版本控制</span><span class="sxs-lookup"><span data-stu-id="93374-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="93374-117">简要概述了一些新发现功能的原型实现，</span><span class="sxs-lookup"><span data-stu-id="93374-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="93374-118">还概述了如何选择要使用的发现版本。</span><span class="sxs-lookup"><span data-stu-id="93374-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="93374-119">在配置文件中配置发现</span><span class="sxs-lookup"><span data-stu-id="93374-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="93374-120">演示如何在配置中配置 Discovery。</span><span class="sxs-lookup"><span data-stu-id="93374-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="93374-121">使用 Discovery 客户端通道</span><span class="sxs-lookup"><span data-stu-id="93374-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="93374-122">演示在编写 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端应用程序时如何使用 Discovery 客户端通道。</span><span class="sxs-lookup"><span data-stu-id="93374-122">Shows how to use a Discovery Client Channel when writing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span>
