---
title: 4201 - EndSqlCommandExecute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0214339ad02f708dcefe411ae1786df31faff86
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="98a71-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="98a71-102">4201 - EndSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="98a71-103">属性</span><span class="sxs-lookup"><span data-stu-id="98a71-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98a71-104">ID</span><span class="sxs-lookup"><span data-stu-id="98a71-104">ID</span></span>|<span data-ttu-id="98a71-105">4201</span><span class="sxs-lookup"><span data-stu-id="98a71-105">4201</span></span>|  
|<span data-ttu-id="98a71-106">关键字</span><span class="sxs-lookup"><span data-stu-id="98a71-106">Keywords</span></span>|<span data-ttu-id="98a71-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="98a71-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="98a71-108">级别</span><span class="sxs-lookup"><span data-stu-id="98a71-108">Level</span></span>|<span data-ttu-id="98a71-109">详细</span><span class="sxs-lookup"><span data-stu-id="98a71-109">Verbose</span></span>|  
|<span data-ttu-id="98a71-110">通道</span><span class="sxs-lookup"><span data-stu-id="98a71-110">Channel</span></span>|<span data-ttu-id="98a71-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="98a71-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="98a71-112">描述</span><span class="sxs-lookup"><span data-stu-id="98a71-112">Description</span></span>  
 <span data-ttu-id="98a71-113">指示 SQL 命令已完成执行。</span><span class="sxs-lookup"><span data-stu-id="98a71-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="98a71-114">消息</span><span class="sxs-lookup"><span data-stu-id="98a71-114">Message</span></span>  
 <span data-ttu-id="98a71-115">结束 SQL 命令执行: %1</span><span class="sxs-lookup"><span data-stu-id="98a71-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="98a71-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="98a71-116">Details</span></span>  
  
|<span data-ttu-id="98a71-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="98a71-117">Data Item Name</span></span>|<span data-ttu-id="98a71-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="98a71-118">Data Item Type</span></span>|<span data-ttu-id="98a71-119">描述</span><span class="sxs-lookup"><span data-stu-id="98a71-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="98a71-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="98a71-120">SqlCommand</span></span>|<span data-ttu-id="98a71-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="98a71-121">xs:string</span></span>|<span data-ttu-id="98a71-122">已执行的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="98a71-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="98a71-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="98a71-123">AppDomain</span></span>|<span data-ttu-id="98a71-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="98a71-124">xs:string</span></span>|<span data-ttu-id="98a71-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="98a71-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
