---
title: WCF Discovery
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 175f79096d2bbda81a602d38e027d5a6d871fa12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768688"
---
# <a name="wcf-discovery"></a><span data-ttu-id="7c2f4-102">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="7c2f4-102">WCF Discovery</span></span>
<span data-ttu-id="7c2f4-103">Windows Communication Foundation (WCF) 提供支持，以使服务可以使用 Ws-discovery 协议以互操作方式是在运行时发现。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="7c2f4-104">WCF 服务可以公告其可用性，到使用多播的消息的网络或发现代理服务器。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="7c2f4-105">客户端应用程序可以搜索网络或发现代理服务器来查找满足一组条件的服务。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="7c2f4-106">本节中的主题分别概述和详细介绍了此功能的编程模型。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c2f4-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="7c2f4-107">In This Section</span></span>  
 [<span data-ttu-id="7c2f4-108">WCF 发现概述</span><span class="sxs-lookup"><span data-stu-id="7c2f4-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="7c2f4-109">提供了 WCF 提供的 Ws-discovery 支持的概述。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="7c2f4-110">WCF 发现对象模型</span><span class="sxs-lookup"><span data-stu-id="7c2f4-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="7c2f4-111">描述对象模型中的类和 WS-Discovery 支持的扩展性。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="7c2f4-112">如何：以编程方式向 WCF 服务和客户端添加可发现性</span><span class="sxs-lookup"><span data-stu-id="7c2f4-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="7c2f4-113">演示如何使 Windows Communication Foundation (WCF) 服务可发现。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="7c2f4-114">实现发现代理</span><span class="sxs-lookup"><span data-stu-id="7c2f4-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="7c2f4-115">描述一些必需步骤，这些步骤用于实现发现代理、注册到发现代理的可检测服务以及使用发现代理查找可检测服务的客户端。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="7c2f4-116">发现版本控制</span><span class="sxs-lookup"><span data-stu-id="7c2f4-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="7c2f4-117">简要概述了一些新发现功能的原型实现，</span><span class="sxs-lookup"><span data-stu-id="7c2f4-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="7c2f4-118">还概述了如何选择要使用的发现版本。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="7c2f4-119">在配置文件中配置发现</span><span class="sxs-lookup"><span data-stu-id="7c2f4-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="7c2f4-120">演示如何在配置中配置 Discovery。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="7c2f4-121">使用发现客户端通道</span><span class="sxs-lookup"><span data-stu-id="7c2f4-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="7c2f4-122">演示如何编写 WCF 客户端应用程序时使用 Discovery 客户端通道。</span><span class="sxs-lookup"><span data-stu-id="7c2f4-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
