---
title: 4214 - InstanceLocksRecoveryError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d28fb2d5-bf15-4648-8d20-8141ad16f04b
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a613afcf0f86b14fca55aa2a4df73e80dd60068a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4214---instancelocksrecoveryerror"></a><span data-ttu-id="8c3c7-102">4214 - InstanceLocksRecoveryError</span><span class="sxs-lookup"><span data-stu-id="8c3c7-102">4214 - InstanceLocksRecoveryError</span></span>
## <a name="properties"></a><span data-ttu-id="8c3c7-103">属性</span><span class="sxs-lookup"><span data-stu-id="8c3c7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c3c7-104">ID</span><span class="sxs-lookup"><span data-stu-id="8c3c7-104">ID</span></span>|<span data-ttu-id="8c3c7-105">4214</span><span class="sxs-lookup"><span data-stu-id="8c3c7-105">4214</span></span>|  
|<span data-ttu-id="8c3c7-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8c3c7-106">Keywords</span></span>|<span data-ttu-id="8c3c7-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="8c3c7-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="8c3c7-108">级别</span><span class="sxs-lookup"><span data-stu-id="8c3c7-108">Level</span></span>|<span data-ttu-id="8c3c7-109">错误</span><span class="sxs-lookup"><span data-stu-id="8c3c7-109">Error</span></span>|  
|<span data-ttu-id="8c3c7-110">通道</span><span class="sxs-lookup"><span data-stu-id="8c3c7-110">Channel</span></span>|<span data-ttu-id="8c3c7-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="8c3c7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8c3c7-112">描述</span><span class="sxs-lookup"><span data-stu-id="8c3c7-112">Description</span></span>  
 <span data-ttu-id="8c3c7-113">由于异常，导致实例锁恢复失败。</span><span class="sxs-lookup"><span data-stu-id="8c3c7-113">Recovering instance locks failed due to an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8c3c7-114">消息</span><span class="sxs-lookup"><span data-stu-id="8c3c7-114">Message</span></span>  
 <span data-ttu-id="8c3c7-115">由于下列异常，导致实例锁恢复失败</span><span class="sxs-lookup"><span data-stu-id="8c3c7-115">Recovering instance locks failed due to the following exception</span></span>  
  
## <a name="details"></a><span data-ttu-id="8c3c7-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="8c3c7-116">Details</span></span>  
  
|<span data-ttu-id="8c3c7-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8c3c7-117">Data Item Name</span></span>|<span data-ttu-id="8c3c7-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8c3c7-118">Data Item Type</span></span>|<span data-ttu-id="8c3c7-119">描述</span><span class="sxs-lookup"><span data-stu-id="8c3c7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8c3c7-120">例外</span><span class="sxs-lookup"><span data-stu-id="8c3c7-120">Exception</span></span>|<span data-ttu-id="8c3c7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8c3c7-121">xs:string</span></span>|<span data-ttu-id="8c3c7-122">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="8c3c7-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="8c3c7-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8c3c7-123">AppDomain</span></span>|<span data-ttu-id="8c3c7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8c3c7-124">xs:string</span></span>|<span data-ttu-id="8c3c7-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8c3c7-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
