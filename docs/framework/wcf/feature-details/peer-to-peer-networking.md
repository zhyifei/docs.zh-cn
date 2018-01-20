---
title: "对等网络"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a26f10a323b44e7954245ab90a02f62745e84e87
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="aa708-102">对等网络</span><span class="sxs-lookup"><span data-stu-id="aa708-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="aa708-103">对等通道是 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的一种多方对等 (P2P) 通信技术。</span><span class="sxs-lookup"><span data-stu-id="aa708-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="aa708-104">它为应用程序开发人员提供了基于消息的、安全且可伸缩的 P2P 信道。</span><span class="sxs-lookup"><span data-stu-id="aa708-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="aa708-105">可从对等通道中获益的多方应用程序的一个常见示例是协作应用程序，例如聊天应用程序，其中一组人以对等方式（无需服务器）相互聊天。</span><span class="sxs-lookup"><span data-stu-id="aa708-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="aa708-106">对等通道可为消费者和企业方案启用 P2P 协作、内容分发、负载平衡和分布式处理。</span><span class="sxs-lookup"><span data-stu-id="aa708-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="aa708-107">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上默认启用对等通道，所有 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 也是如此。</span><span class="sxs-lookup"><span data-stu-id="aa708-107">Peer Channel is enabled by default on [!INCLUDE[wv](../../../../includes/wv-md.md)], as is all of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="aa708-108">若要访问对等通道类，请在项目中添加对 System.ServiceModel.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="aa708-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="aa708-109">以下各节包含有关对等网络以及使用对等通道类来创建启用对等的网络应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="aa708-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa708-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="aa708-110">In This Section</span></span>  
 <span data-ttu-id="aa708-111">[对等通道方案](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md)： 介绍支持的对等通道 Api，开发方案，如发布/订阅消息传递、 协作，分布式处理和游戏。</span><span class="sxs-lookup"><span data-stu-id="aa708-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="aa708-112">[对等通道概念](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)： 介绍对等网格、 对等节点、 对等通道安全和对等解析程序。</span><span class="sxs-lookup"><span data-stu-id="aa708-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="aa708-113">[生成对等通道应用程序](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)： 提供有关开发对等通道应用程序的指导。</span><span class="sxs-lookup"><span data-stu-id="aa708-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="aa708-114">对等通道代码示例</span><span class="sxs-lookup"><span data-stu-id="aa708-114">Peer Channel Code Examples</span></span>  
 [<span data-ttu-id="aa708-115">对等通道自定义对等解析程序</span><span class="sxs-lookup"><span data-stu-id="aa708-115">Peer Channel Custom Peer Resolver</span></span>](http://msdn.microsoft.com/library/5b75a2bb-7ff1-4a14-abe7-3debf0537d23)  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="aa708-116">对等通道团队博客</span><span class="sxs-lookup"><span data-stu-id="aa708-116">Peer Channel Team blog</span></span>  
 <span data-ttu-id="aa708-117">[对等通道团队博客](http://go.microsoft.com/fwlink/?LinkID=114530)(http://go.microsoft.com/fwlink/?LinkID=114530)</span><span class="sxs-lookup"><span data-stu-id="aa708-117">[Peer Channel Team Blog](http://go.microsoft.com/fwlink/?LinkID=114530) (http://go.microsoft.com/fwlink/?LinkID=114530)</span></span>
