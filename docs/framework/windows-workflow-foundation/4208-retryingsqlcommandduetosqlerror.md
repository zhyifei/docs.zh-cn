---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01db76802b96bd32e8a01cf86b1e682defe97a06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="4da11-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="4da11-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="4da11-103">属性</span><span class="sxs-lookup"><span data-stu-id="4da11-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4da11-104">ID</span><span class="sxs-lookup"><span data-stu-id="4da11-104">ID</span></span>|<span data-ttu-id="4da11-105">4208</span><span class="sxs-lookup"><span data-stu-id="4da11-105">4208</span></span>|  
|<span data-ttu-id="4da11-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4da11-106">Keywords</span></span>|<span data-ttu-id="4da11-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="4da11-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="4da11-108">级别</span><span class="sxs-lookup"><span data-stu-id="4da11-108">Level</span></span>|<span data-ttu-id="4da11-109">信息</span><span class="sxs-lookup"><span data-stu-id="4da11-109">Information</span></span>|  
|<span data-ttu-id="4da11-110">通道</span><span class="sxs-lookup"><span data-stu-id="4da11-110">Channel</span></span>|<span data-ttu-id="4da11-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="4da11-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4da11-112">描述</span><span class="sxs-lookup"><span data-stu-id="4da11-112">Description</span></span>  
 <span data-ttu-id="4da11-113">指示 SQL 提供程序由于 SQL 错误正在重试 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="4da11-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4da11-114">消息</span><span class="sxs-lookup"><span data-stu-id="4da11-114">Message</span></span>  
 <span data-ttu-id="4da11-115">因 SQL 错误号 %1，正在重试 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="4da11-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4da11-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="4da11-116">Details</span></span>  
  
|<span data-ttu-id="4da11-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4da11-117">Data Item Name</span></span>|<span data-ttu-id="4da11-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4da11-118">Data Item Type</span></span>|<span data-ttu-id="4da11-119">描述</span><span class="sxs-lookup"><span data-stu-id="4da11-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4da11-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="4da11-120">ErrorNumber</span></span>|<span data-ttu-id="4da11-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4da11-121">xs:string</span></span>|<span data-ttu-id="4da11-122">SQL 错误号。</span><span class="sxs-lookup"><span data-stu-id="4da11-122">The SQL error number.</span></span>|  
|<span data-ttu-id="4da11-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4da11-123">AppDomain</span></span>|<span data-ttu-id="4da11-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4da11-124">xs:string</span></span>|<span data-ttu-id="4da11-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4da11-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
