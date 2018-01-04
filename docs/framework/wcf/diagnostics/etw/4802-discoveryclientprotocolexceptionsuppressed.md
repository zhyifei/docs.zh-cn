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
ms.workload: dotnet
ms.openlocfilehash: ecb147e35b830322240f69f533de7a588064e9d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="4802---discoveryclientprotocolexceptionsuppressed"></a><span data-ttu-id="21c85-102">4802 - DiscoveryClientProtocolExceptionSuppressed</span><span class="sxs-lookup"><span data-stu-id="21c85-102">4802 - DiscoveryClientProtocolExceptionSuppressed</span></span>
## <a name="properties"></a><span data-ttu-id="21c85-103">属性</span><span class="sxs-lookup"><span data-stu-id="21c85-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21c85-104">ID</span><span class="sxs-lookup"><span data-stu-id="21c85-104">ID</span></span>|<span data-ttu-id="21c85-105">4802</span><span class="sxs-lookup"><span data-stu-id="21c85-105">4802</span></span>|  
|<span data-ttu-id="21c85-106">关键字</span><span class="sxs-lookup"><span data-stu-id="21c85-106">Keywords</span></span>|<span data-ttu-id="21c85-107">发现</span><span class="sxs-lookup"><span data-stu-id="21c85-107">Discovery</span></span>|  
|<span data-ttu-id="21c85-108">级别</span><span class="sxs-lookup"><span data-stu-id="21c85-108">Level</span></span>|<span data-ttu-id="21c85-109">信息</span><span class="sxs-lookup"><span data-stu-id="21c85-109">Information</span></span>|  
|<span data-ttu-id="21c85-110">通道</span><span class="sxs-lookup"><span data-stu-id="21c85-110">Channel</span></span>|<span data-ttu-id="21c85-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="21c85-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="21c85-112">描述</span><span class="sxs-lookup"><span data-stu-id="21c85-112">Description</span></span>  
 <span data-ttu-id="21c85-113">当关闭 DiscoveryClient 时，ProtocolException 被禁止，此时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="21c85-113">This event is emitted when the a ProtocolException was suppressed while closing the DiscoveryClient.</span></span>  
  
## <a name="message"></a><span data-ttu-id="21c85-114">消息</span><span class="sxs-lookup"><span data-stu-id="21c85-114">Message</span></span>  
 <span data-ttu-id="21c85-115">关闭 DiscoveryClient 时，ProtocolException 被禁止。</span><span class="sxs-lookup"><span data-stu-id="21c85-115">A ProtocolException was suppressed while closing the DiscoveryClient.</span></span> <span data-ttu-id="21c85-116">这可能是由于 DiscoveryService 仍在尝试向 DiscoveryClient 发送响应。</span><span class="sxs-lookup"><span data-stu-id="21c85-116">This could be because a DiscoveryService is still trying to send response to the DiscoveryClient.</span></span>  
  
## <a name="details"></a><span data-ttu-id="21c85-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="21c85-117">Details</span></span>
