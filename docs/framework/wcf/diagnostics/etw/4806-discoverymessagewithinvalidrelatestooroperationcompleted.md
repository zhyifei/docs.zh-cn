---
title: 4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted
ms.date: 03/30/2017
ms.assetid: 19e9a660-25f3-4332-b716-a12a59f2cbbb
ms.openlocfilehash: 3d0d8d426b0b8b7e5a1e890847ae36957e62f028
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33467101"
---
# <a name="4806---discoverymessagewithinvalidrelatestooroperationcompleted"></a><span data-ttu-id="97c9d-102">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="97c9d-102">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="97c9d-103">属性</span><span class="sxs-lookup"><span data-stu-id="97c9d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97c9d-104">ID</span><span class="sxs-lookup"><span data-stu-id="97c9d-104">ID</span></span>|<span data-ttu-id="97c9d-105">4806</span><span class="sxs-lookup"><span data-stu-id="97c9d-105">4806</span></span>|  
|<span data-ttu-id="97c9d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="97c9d-106">Keywords</span></span>|<span data-ttu-id="97c9d-107">发现</span><span class="sxs-lookup"><span data-stu-id="97c9d-107">Discovery</span></span>|  
|<span data-ttu-id="97c9d-108">级别</span><span class="sxs-lookup"><span data-stu-id="97c9d-108">Level</span></span>|<span data-ttu-id="97c9d-109">警告</span><span class="sxs-lookup"><span data-stu-id="97c9d-109">Warning</span></span>|  
|<span data-ttu-id="97c9d-110">通道</span><span class="sxs-lookup"><span data-stu-id="97c9d-110">Channel</span></span>|<span data-ttu-id="97c9d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="97c9d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="97c9d-112">描述</span><span class="sxs-lookup"><span data-stu-id="97c9d-112">Description</span></span>  
 <span data-ttu-id="97c9d-113">当因为相应的操作已完成或 relatesTo 值无效而导致发现消息已被 DiscoveryClient 丢弃时，发出此事件。</span><span class="sxs-lookup"><span data-stu-id="97c9d-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because either the corresponding operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="message"></a><span data-ttu-id="97c9d-114">消息</span><span class="sxs-lookup"><span data-stu-id="97c9d-114">Message</span></span>  
 <span data-ttu-id="97c9d-115">messageId 为“%2”且 relatesTo 为“%3”的 %1 消息已被 DiscoveryClient 丢弃，因为相应的 %4 操作已完成或 relatesTo 值无效。</span><span class="sxs-lookup"><span data-stu-id="97c9d-115">A %1 message with messageId='%2' and relatesTo='%3' was dropped by the DiscoveryClient because either the corresponding %4 operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="details"></a><span data-ttu-id="97c9d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="97c9d-116">Details</span></span>
