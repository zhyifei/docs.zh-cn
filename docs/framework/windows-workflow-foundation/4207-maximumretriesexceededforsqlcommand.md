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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97a2f68ed921ccc251e1dc316d633d2520efc643
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4207---maximumretriesexceededforsqlcommand"></a><span data-ttu-id="1f504-102">4207 - MaximumRetriesExceededForSqlCommand</span><span class="sxs-lookup"><span data-stu-id="1f504-102">4207 - MaximumRetriesExceededForSqlCommand</span></span>
## <a name="properties"></a><span data-ttu-id="1f504-103">属性</span><span class="sxs-lookup"><span data-stu-id="1f504-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1f504-104">ID</span><span class="sxs-lookup"><span data-stu-id="1f504-104">ID</span></span>|<span data-ttu-id="1f504-105">4207</span><span class="sxs-lookup"><span data-stu-id="1f504-105">4207</span></span>|  
|<span data-ttu-id="1f504-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1f504-106">Keywords</span></span>|<span data-ttu-id="1f504-107">配额，FInstanceStore</span><span class="sxs-lookup"><span data-stu-id="1f504-107">Quota, WFInstanceStore</span></span>|  
|<span data-ttu-id="1f504-108">级别</span><span class="sxs-lookup"><span data-stu-id="1f504-108">Level</span></span>|<span data-ttu-id="1f504-109">信息</span><span class="sxs-lookup"><span data-stu-id="1f504-109">Information</span></span>|  
|<span data-ttu-id="1f504-110">通道</span><span class="sxs-lookup"><span data-stu-id="1f504-110">Channel</span></span>|<span data-ttu-id="1f504-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1f504-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1f504-112">描述</span><span class="sxs-lookup"><span data-stu-id="1f504-112">Description</span></span>  
 <span data-ttu-id="1f504-113">指示 SQL 提供程序正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="1f504-113">Indicates SQL provider is giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1f504-114">消息</span><span class="sxs-lookup"><span data-stu-id="1f504-114">Message</span></span>  
 <span data-ttu-id="1f504-115">正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。</span><span class="sxs-lookup"><span data-stu-id="1f504-115">Giving up retrying a SQL command as the maximum number of retries have been performed.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1f504-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="1f504-116">Details</span></span>  
  
|<span data-ttu-id="1f504-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1f504-117">Data Item Name</span></span>|<span data-ttu-id="1f504-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1f504-118">Data Item Type</span></span>|<span data-ttu-id="1f504-119">描述</span><span class="sxs-lookup"><span data-stu-id="1f504-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1f504-120">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1f504-120">AppDomain</span></span>|<span data-ttu-id="1f504-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f504-121">xs:string</span></span>|<span data-ttu-id="1f504-122">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1f504-122">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
