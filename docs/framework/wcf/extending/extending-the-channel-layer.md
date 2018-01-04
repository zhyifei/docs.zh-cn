---
title: "扩展通道层"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending channels [WCF]
ms.assetid: 4238db74-2fb6-4dc8-a326-f58527230810
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a1a1bb0b1f2c5e6b42ee793f18f5ad442b1fe8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-channel-layer"></a><span data-ttu-id="fff14-102">扩展通道层</span><span class="sxs-lookup"><span data-stu-id="fff14-102">Extending the Channel Layer</span></span>
<span data-ttu-id="fff14-103">通道层负责在客户端和服务之间交换消息。</span><span class="sxs-lookup"><span data-stu-id="fff14-103">The channel layer is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="fff14-104">通道扩展可以实现新的协议功能（例如安全性）或传输功能（例如实现新的网络传输来传送 SOAP 消息）。</span><span class="sxs-lookup"><span data-stu-id="fff14-104">Channel extensions can implement new protocol functionality, such as security, or transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fff14-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="fff14-105">In This Section</span></span>  
 [<span data-ttu-id="fff14-106">通道模型概述</span><span class="sxs-lookup"><span data-stu-id="fff14-106">Channel Model Overview</span></span>](../../../../docs/framework/wcf/extending/channel-model-overview.md)  
 <span data-ttu-id="fff14-107">在较高层面概述了什么是通道、通道提供的功能以及通道在服务和客户端应用程序中的工作方式。</span><span class="sxs-lookup"><span data-stu-id="fff14-107">Provides a high-level overview of what channels are, the features that they provide and how they work both in a service and a client application.</span></span>  
  
 [<span data-ttu-id="fff14-108">开发通道</span><span class="sxs-lookup"><span data-stu-id="fff14-108">Developing Channels</span></span>](../../../../docs/framework/wcf/extending/developing-channels.md)  
 <span data-ttu-id="fff14-109">深入描述各种通道基础结构类型所起的作用、状态引擎和状态生命周期的工作方式、如何处理异常和错误、如何实现元数据支持以及通道如何使用消息编码器。</span><span class="sxs-lookup"><span data-stu-id="fff14-109">Describes in depth the roles that the various channel infrastructure types play, how the state engine and state lifecycle works, how to handle exceptions and faults, how to implement metadata support, and how channels work with message encoders.</span></span>  
  
 [<span data-ttu-id="fff14-110">自定义编码器</span><span class="sxs-lookup"><span data-stu-id="fff14-110">Custom Encoders</span></span>](../../../../docs/framework/wcf/extending/custom-encoders.md)  
 <span data-ttu-id="fff14-111">描述消息编码器在通道中所起的作用以及如何生成消息编码器。</span><span class="sxs-lookup"><span data-stu-id="fff14-111">Describes the role that message encoders play in channels and how to build one.</span></span>  
  
 [<span data-ttu-id="fff14-112">自定义流升级</span><span class="sxs-lookup"><span data-stu-id="fff14-112">Custom Stream Upgrades</span></span>](../../../../docs/framework/wcf/extending/custom-stream-upgrades.md)  
 <span data-ttu-id="fff14-113">描述由面向流的传输所提供的流的升级过程。</span><span class="sxs-lookup"><span data-stu-id="fff14-113">Describes the process of upgrading the streams provided by stream-oriented transports.</span></span>
