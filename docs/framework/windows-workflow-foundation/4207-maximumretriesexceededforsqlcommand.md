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
ms.workload: dotnet
ms.openlocfilehash: 30a1fc01ab308950d0cce60cead2dcd17d9e1096
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="4207---maximumretriesexceededforsqlcommand"></a><span data-ttu-id="fd465-102">4207 - MaximumRetriesExceededForSqlCommand</span><span class="sxs-lookup"><span data-stu-id="fd465-102">4207 - MaximumRetriesExceededForSqlCommand</span></span>
## <a name="properties"></a><span data-ttu-id="fd465-103">属性</span><span class="sxs-lookup"><span data-stu-id="fd465-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd465-104">ID</span><span class="sxs-lookup"><span data-stu-id="fd465-104">ID</span></span>|<span data-ttu-id="fd465-105">4207</span><span class="sxs-lookup"><span data-stu-id="fd465-105">4207</span></span>|  
|<span data-ttu-id="fd465-106">关键字</span><span class="sxs-lookup"><span data-stu-id="fd465-106">Keywords</span></span>|<span data-ttu-id="fd465-107">配额，FInstanceStore</span><span class="sxs-lookup"><span data-stu-id="fd465-107">Quota, WFInstanceStore</span></span>|  
|<span data-ttu-id="fd465-108">级别</span><span class="sxs-lookup"><span data-stu-id="fd465-108">Level</span></span>|<span data-ttu-id="fd465-109">信息</span><span class="sxs-lookup"><span data-stu-id="fd465-109">Information</span></span>|  
|<span data-ttu-id="fd465-110">通道</span><span class="sxs-lookup"><span data-stu-id="fd465-110">Channel</span></span>|<span data-ttu-id="fd465-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="fd465-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fd465-112">描述</span><span class="sxs-lookup"><span data-stu-id="fd465-112">Description</span></span>  
 <span data-ttu-id="fd465-113">指示 SQL 提供程序正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="fd465-113">Indicates SQL provider is giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fd465-114">消息</span><span class="sxs-lookup"><span data-stu-id="fd465-114">Message</span></span>  
 <span data-ttu-id="fd465-115">正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="fd465-115">Giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fd465-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="fd465-116">Details</span></span>  
  
|<span data-ttu-id="fd465-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="fd465-117">Data Item Name</span></span>|<span data-ttu-id="fd465-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="fd465-118">Data Item Type</span></span>|<span data-ttu-id="fd465-119">描述</span><span class="sxs-lookup"><span data-stu-id="fd465-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fd465-120">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fd465-120">AppDomain</span></span>|<span data-ttu-id="fd465-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd465-121">xs:string</span></span>|<span data-ttu-id="fd465-122">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="fd465-122">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
