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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d54660ed7f278b1f82fac81c31b8a30e20a2e7d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="e0534-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="e0534-102">4202 - StartSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="e0534-103">属性</span><span class="sxs-lookup"><span data-stu-id="e0534-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0534-104">ID</span><span class="sxs-lookup"><span data-stu-id="e0534-104">ID</span></span>|<span data-ttu-id="e0534-105">4202</span><span class="sxs-lookup"><span data-stu-id="e0534-105">4202</span></span>|  
|<span data-ttu-id="e0534-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e0534-106">Keywords</span></span>|<span data-ttu-id="e0534-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="e0534-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="e0534-108">级别</span><span class="sxs-lookup"><span data-stu-id="e0534-108">Level</span></span>|<span data-ttu-id="e0534-109">详细</span><span class="sxs-lookup"><span data-stu-id="e0534-109">Verbose</span></span>|  
|<span data-ttu-id="e0534-110">通道</span><span class="sxs-lookup"><span data-stu-id="e0534-110">Channel</span></span>|<span data-ttu-id="e0534-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="e0534-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0534-112">描述</span><span class="sxs-lookup"><span data-stu-id="e0534-112">Description</span></span>  
 <span data-ttu-id="e0534-113">指示 SQL 命令正在执行。</span><span class="sxs-lookup"><span data-stu-id="e0534-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0534-114">消息</span><span class="sxs-lookup"><span data-stu-id="e0534-114">Message</span></span>  
 <span data-ttu-id="e0534-115">正在开始 SQL 命令执行: %1</span><span class="sxs-lookup"><span data-stu-id="e0534-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0534-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e0534-116">Details</span></span>  
  
|<span data-ttu-id="e0534-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e0534-117">Data Item Name</span></span>|<span data-ttu-id="e0534-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e0534-118">Data Item Type</span></span>|<span data-ttu-id="e0534-119">描述</span><span class="sxs-lookup"><span data-stu-id="e0534-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e0534-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="e0534-120">SqlCommand</span></span>|<span data-ttu-id="e0534-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0534-121">xs:string</span></span>|<span data-ttu-id="e0534-122">已执行的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="e0534-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="e0534-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e0534-123">AppDomain</span></span>|<span data-ttu-id="e0534-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0534-124">xs:string</span></span>|<span data-ttu-id="e0534-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e0534-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
