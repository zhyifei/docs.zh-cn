---
title: 4207 - MaximumRetriesExceededForSqlCommand
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c8bee26-9ad4-4e01-bd16-0e1fd510fb6b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1708cba44a4afc22635a039f7868a9ffbf41fc37
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4207---maximumretriesexceededforsqlcommand"></a><span data-ttu-id="4d7ab-102">4207 - MaximumRetriesExceededForSqlCommand</span><span class="sxs-lookup"><span data-stu-id="4d7ab-102">4207 - MaximumRetriesExceededForSqlCommand</span></span>
## <a name="properties"></a><span data-ttu-id="4d7ab-103">属性</span><span class="sxs-lookup"><span data-stu-id="4d7ab-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d7ab-104">ID</span><span class="sxs-lookup"><span data-stu-id="4d7ab-104">ID</span></span>|<span data-ttu-id="4d7ab-105">4207</span><span class="sxs-lookup"><span data-stu-id="4d7ab-105">4207</span></span>|  
|<span data-ttu-id="4d7ab-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4d7ab-106">Keywords</span></span>|<span data-ttu-id="4d7ab-107">配额，FInstanceStore</span><span class="sxs-lookup"><span data-stu-id="4d7ab-107">Quota, WFInstanceStore</span></span>|  
|<span data-ttu-id="4d7ab-108">级别</span><span class="sxs-lookup"><span data-stu-id="4d7ab-108">Level</span></span>|<span data-ttu-id="4d7ab-109">信息</span><span class="sxs-lookup"><span data-stu-id="4d7ab-109">Information</span></span>|  
|<span data-ttu-id="4d7ab-110">通道</span><span class="sxs-lookup"><span data-stu-id="4d7ab-110">Channel</span></span>|<span data-ttu-id="4d7ab-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="4d7ab-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4d7ab-112">描述</span><span class="sxs-lookup"><span data-stu-id="4d7ab-112">Description</span></span>  
 <span data-ttu-id="4d7ab-113">指示 SQL 提供程序正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-113">Indicates SQL provider is giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4d7ab-114">消息</span><span class="sxs-lookup"><span data-stu-id="4d7ab-114">Message</span></span>  
 <span data-ttu-id="4d7ab-115">正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-115">Giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4d7ab-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="4d7ab-116">Details</span></span>  
  
|<span data-ttu-id="4d7ab-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4d7ab-117">Data Item Name</span></span>|<span data-ttu-id="4d7ab-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4d7ab-118">Data Item Type</span></span>|<span data-ttu-id="4d7ab-119">描述</span><span class="sxs-lookup"><span data-stu-id="4d7ab-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4d7ab-120">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4d7ab-120">AppDomain</span></span>|<span data-ttu-id="4d7ab-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d7ab-121">xs:string</span></span>|<span data-ttu-id="4d7ab-122">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4d7ab-122">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
