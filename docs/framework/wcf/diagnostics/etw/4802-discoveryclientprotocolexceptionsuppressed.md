---
title: 4802 - DiscoveryClientProtocolExceptionSuppressed
ms.date: 03/30/2017
ms.assetid: 568212f7-1060-4f5c-a7a0-1352c7cc743b
ms.openlocfilehash: 5bb7772d668a6b635130c899ada9879c9c1f69a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33468200"
---
# <a name="4802---discoveryclientprotocolexceptionsuppressed"></a><span data-ttu-id="b73e1-102">4802 - DiscoveryClientProtocolExceptionSuppressed</span><span class="sxs-lookup"><span data-stu-id="b73e1-102">4802 - DiscoveryClientProtocolExceptionSuppressed</span></span>
## <a name="properties"></a><span data-ttu-id="b73e1-103">属性</span><span class="sxs-lookup"><span data-stu-id="b73e1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b73e1-104">ID</span><span class="sxs-lookup"><span data-stu-id="b73e1-104">ID</span></span>|<span data-ttu-id="b73e1-105">4802</span><span class="sxs-lookup"><span data-stu-id="b73e1-105">4802</span></span>|  
|<span data-ttu-id="b73e1-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b73e1-106">Keywords</span></span>|<span data-ttu-id="b73e1-107">发现</span><span class="sxs-lookup"><span data-stu-id="b73e1-107">Discovery</span></span>|  
|<span data-ttu-id="b73e1-108">级别</span><span class="sxs-lookup"><span data-stu-id="b73e1-108">Level</span></span>|<span data-ttu-id="b73e1-109">信息</span><span class="sxs-lookup"><span data-stu-id="b73e1-109">Information</span></span>|  
|<span data-ttu-id="b73e1-110">通道</span><span class="sxs-lookup"><span data-stu-id="b73e1-110">Channel</span></span>|<span data-ttu-id="b73e1-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="b73e1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b73e1-112">描述</span><span class="sxs-lookup"><span data-stu-id="b73e1-112">Description</span></span>  
 <span data-ttu-id="b73e1-113">当关闭 DiscoveryClient 时，ProtocolException 被禁止，此时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="b73e1-113">This event is emitted when the a ProtocolException was suppressed while closing the DiscoveryClient.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b73e1-114">消息</span><span class="sxs-lookup"><span data-stu-id="b73e1-114">Message</span></span>  
 <span data-ttu-id="b73e1-115">关闭 DiscoveryClient 时，ProtocolException 被禁止。</span><span class="sxs-lookup"><span data-stu-id="b73e1-115">A ProtocolException was suppressed while closing the DiscoveryClient.</span></span> <span data-ttu-id="b73e1-116">这可能是由于 DiscoveryService 仍在尝试向 DiscoveryClient 发送响应。</span><span class="sxs-lookup"><span data-stu-id="b73e1-116">This could be because a DiscoveryService is still trying to send response to the DiscoveryClient.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b73e1-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="b73e1-117">Details</span></span>
