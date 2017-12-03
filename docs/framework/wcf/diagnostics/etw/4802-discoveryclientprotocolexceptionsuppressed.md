---
title: 4802 - DiscoveryClientProtocolExceptionSuppressed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 568212f7-1060-4f5c-a7a0-1352c7cc743b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f2b5832b93db61ac42834569c5269e7a6933cc2f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4802---discoveryclientprotocolexceptionsuppressed"></a><span data-ttu-id="3bc9d-102">4802 - DiscoveryClientProtocolExceptionSuppressed</span><span class="sxs-lookup"><span data-stu-id="3bc9d-102">4802 - DiscoveryClientProtocolExceptionSuppressed</span></span>
## <a name="properties"></a><span data-ttu-id="3bc9d-103">属性</span><span class="sxs-lookup"><span data-stu-id="3bc9d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3bc9d-104">ID</span><span class="sxs-lookup"><span data-stu-id="3bc9d-104">ID</span></span>|<span data-ttu-id="3bc9d-105">4802</span><span class="sxs-lookup"><span data-stu-id="3bc9d-105">4802</span></span>|  
|<span data-ttu-id="3bc9d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="3bc9d-106">Keywords</span></span>|<span data-ttu-id="3bc9d-107">发现</span><span class="sxs-lookup"><span data-stu-id="3bc9d-107">Discovery</span></span>|  
|<span data-ttu-id="3bc9d-108">级别</span><span class="sxs-lookup"><span data-stu-id="3bc9d-108">Level</span></span>|<span data-ttu-id="3bc9d-109">信息</span><span class="sxs-lookup"><span data-stu-id="3bc9d-109">Information</span></span>|  
|<span data-ttu-id="3bc9d-110">通道</span><span class="sxs-lookup"><span data-stu-id="3bc9d-110">Channel</span></span>|<span data-ttu-id="3bc9d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="3bc9d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3bc9d-112">描述</span><span class="sxs-lookup"><span data-stu-id="3bc9d-112">Description</span></span>  
 <span data-ttu-id="3bc9d-113">当关闭 DiscoveryClient 时，ProtocolException 被禁止，此时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="3bc9d-113">This event is emitted when the a ProtocolException was suppressed while closing the DiscoveryClient.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3bc9d-114">消息</span><span class="sxs-lookup"><span data-stu-id="3bc9d-114">Message</span></span>  
 <span data-ttu-id="3bc9d-115">关闭 DiscoveryClient 时，ProtocolException 被禁止。</span><span class="sxs-lookup"><span data-stu-id="3bc9d-115">A ProtocolException was suppressed while closing the DiscoveryClient.</span></span> <span data-ttu-id="3bc9d-116">这可能是由于 DiscoveryService 仍在尝试向 DiscoveryClient 发送响应。</span><span class="sxs-lookup"><span data-stu-id="3bc9d-116">This could be because a DiscoveryService is still trying to send response to the DiscoveryClient.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3bc9d-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="3bc9d-117">Details</span></span>
