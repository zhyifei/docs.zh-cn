---
title: 4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19e9a660-25f3-4332-b716-a12a59f2cbbb
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c55d45936a001df2c5da519e4ab79e7f8a2d470
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4806---discoverymessagewithinvalidrelatestooroperationcompleted"></a><span data-ttu-id="535da-102">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="535da-102">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="535da-103">属性</span><span class="sxs-lookup"><span data-stu-id="535da-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="535da-104">ID</span><span class="sxs-lookup"><span data-stu-id="535da-104">ID</span></span>|<span data-ttu-id="535da-105">4806</span><span class="sxs-lookup"><span data-stu-id="535da-105">4806</span></span>|  
|<span data-ttu-id="535da-106">关键字</span><span class="sxs-lookup"><span data-stu-id="535da-106">Keywords</span></span>|<span data-ttu-id="535da-107">发现</span><span class="sxs-lookup"><span data-stu-id="535da-107">Discovery</span></span>|  
|<span data-ttu-id="535da-108">级别</span><span class="sxs-lookup"><span data-stu-id="535da-108">Level</span></span>|<span data-ttu-id="535da-109">警告</span><span class="sxs-lookup"><span data-stu-id="535da-109">Warning</span></span>|  
|<span data-ttu-id="535da-110">通道</span><span class="sxs-lookup"><span data-stu-id="535da-110">Channel</span></span>|<span data-ttu-id="535da-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="535da-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="535da-112">描述</span><span class="sxs-lookup"><span data-stu-id="535da-112">Description</span></span>  
 <span data-ttu-id="535da-113">当因为相应的操作已完成或 relatesTo 值无效而导致发现消息已被 DiscoveryClient 丢弃时，发出此事件。</span><span class="sxs-lookup"><span data-stu-id="535da-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because either the corresponding operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="message"></a><span data-ttu-id="535da-114">消息</span><span class="sxs-lookup"><span data-stu-id="535da-114">Message</span></span>  
 <span data-ttu-id="535da-115">messageId 为“%2”且 relatesTo 为“%3”的 %1 消息已被 DiscoveryClient 丢弃，因为相应的 %4 操作已完成或 relatesTo 值无效。</span><span class="sxs-lookup"><span data-stu-id="535da-115">A %1 message with messageId='%2' and relatesTo='%3' was dropped by the DiscoveryClient because either the corresponding %4 operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="details"></a><span data-ttu-id="535da-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="535da-116">Details</span></span>
