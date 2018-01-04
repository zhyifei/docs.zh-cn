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
ms.workload: dotnet
ms.openlocfilehash: 5810a30fa8b797a5a8ed533ea6baca3c85d42c0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="1c841-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="1c841-102">4202 - StartSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="1c841-103">属性</span><span class="sxs-lookup"><span data-stu-id="1c841-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c841-104">ID</span><span class="sxs-lookup"><span data-stu-id="1c841-104">ID</span></span>|<span data-ttu-id="1c841-105">4202</span><span class="sxs-lookup"><span data-stu-id="1c841-105">4202</span></span>|  
|<span data-ttu-id="1c841-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1c841-106">Keywords</span></span>|<span data-ttu-id="1c841-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="1c841-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="1c841-108">级别</span><span class="sxs-lookup"><span data-stu-id="1c841-108">Level</span></span>|<span data-ttu-id="1c841-109">详细</span><span class="sxs-lookup"><span data-stu-id="1c841-109">Verbose</span></span>|  
|<span data-ttu-id="1c841-110">通道</span><span class="sxs-lookup"><span data-stu-id="1c841-110">Channel</span></span>|<span data-ttu-id="1c841-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1c841-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1c841-112">描述</span><span class="sxs-lookup"><span data-stu-id="1c841-112">Description</span></span>  
 <span data-ttu-id="1c841-113">指示 SQL 命令正在执行。</span><span class="sxs-lookup"><span data-stu-id="1c841-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1c841-114">消息</span><span class="sxs-lookup"><span data-stu-id="1c841-114">Message</span></span>  
 <span data-ttu-id="1c841-115">正在开始 SQL 命令执行: %1</span><span class="sxs-lookup"><span data-stu-id="1c841-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="1c841-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="1c841-116">Details</span></span>  
  
|<span data-ttu-id="1c841-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1c841-117">Data Item Name</span></span>|<span data-ttu-id="1c841-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1c841-118">Data Item Type</span></span>|<span data-ttu-id="1c841-119">描述</span><span class="sxs-lookup"><span data-stu-id="1c841-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1c841-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="1c841-120">SqlCommand</span></span>|<span data-ttu-id="1c841-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c841-121">xs:string</span></span>|<span data-ttu-id="1c841-122">已执行的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="1c841-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="1c841-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1c841-123">AppDomain</span></span>|<span data-ttu-id="1c841-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c841-124">xs:string</span></span>|<span data-ttu-id="1c841-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1c841-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
