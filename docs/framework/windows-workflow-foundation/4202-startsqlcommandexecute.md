---
title: 4202 - StartSqlCommandExecute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 79cffedf85c840f57a7b57d082ab1dece4375b71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="cfebe-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="cfebe-102">4202 - StartSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="cfebe-103">属性</span><span class="sxs-lookup"><span data-stu-id="cfebe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfebe-104">ID</span><span class="sxs-lookup"><span data-stu-id="cfebe-104">ID</span></span>|<span data-ttu-id="cfebe-105">4202</span><span class="sxs-lookup"><span data-stu-id="cfebe-105">4202</span></span>|  
|<span data-ttu-id="cfebe-106">关键字</span><span class="sxs-lookup"><span data-stu-id="cfebe-106">Keywords</span></span>|<span data-ttu-id="cfebe-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="cfebe-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="cfebe-108">级别</span><span class="sxs-lookup"><span data-stu-id="cfebe-108">Level</span></span>|<span data-ttu-id="cfebe-109">详细</span><span class="sxs-lookup"><span data-stu-id="cfebe-109">Verbose</span></span>|  
|<span data-ttu-id="cfebe-110">通道</span><span class="sxs-lookup"><span data-stu-id="cfebe-110">Channel</span></span>|<span data-ttu-id="cfebe-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="cfebe-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cfebe-112">描述</span><span class="sxs-lookup"><span data-stu-id="cfebe-112">Description</span></span>  
 <span data-ttu-id="cfebe-113">指示 SQL 命令正在执行。</span><span class="sxs-lookup"><span data-stu-id="cfebe-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cfebe-114">消息</span><span class="sxs-lookup"><span data-stu-id="cfebe-114">Message</span></span>  
 <span data-ttu-id="cfebe-115">正在开始 SQL 命令执行: %1</span><span class="sxs-lookup"><span data-stu-id="cfebe-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="cfebe-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="cfebe-116">Details</span></span>  
  
|<span data-ttu-id="cfebe-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="cfebe-117">Data Item Name</span></span>|<span data-ttu-id="cfebe-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="cfebe-118">Data Item Type</span></span>|<span data-ttu-id="cfebe-119">描述</span><span class="sxs-lookup"><span data-stu-id="cfebe-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cfebe-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="cfebe-120">SqlCommand</span></span>|<span data-ttu-id="cfebe-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="cfebe-121">xs:string</span></span>|<span data-ttu-id="cfebe-122">已执行的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="cfebe-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="cfebe-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cfebe-123">AppDomain</span></span>|<span data-ttu-id="cfebe-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cfebe-124">xs:string</span></span>|<span data-ttu-id="cfebe-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="cfebe-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
