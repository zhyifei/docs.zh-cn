---
title: 4210 - SqlExceptionCaught
ms.date: 03/30/2017
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
ms.openlocfilehash: 2493014e80e79ac2935c1bcc685147a74e48fb47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="6348b-102">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="6348b-102">4210 - SqlExceptionCaught</span></span>
## <a name="properties"></a><span data-ttu-id="6348b-103">属性</span><span class="sxs-lookup"><span data-stu-id="6348b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6348b-104">ID</span><span class="sxs-lookup"><span data-stu-id="6348b-104">ID</span></span>|<span data-ttu-id="6348b-105">4210</span><span class="sxs-lookup"><span data-stu-id="6348b-105">4210</span></span>|  
|<span data-ttu-id="6348b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="6348b-106">Keywords</span></span>|<span data-ttu-id="6348b-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="6348b-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="6348b-108">级别</span><span class="sxs-lookup"><span data-stu-id="6348b-108">Level</span></span>|<span data-ttu-id="6348b-109">警告</span><span class="sxs-lookup"><span data-stu-id="6348b-109">Warning</span></span>|  
|<span data-ttu-id="6348b-110">通道</span><span class="sxs-lookup"><span data-stu-id="6348b-110">Channel</span></span>|<span data-ttu-id="6348b-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="6348b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6348b-112">描述</span><span class="sxs-lookup"><span data-stu-id="6348b-112">Description</span></span>  
 <span data-ttu-id="6348b-113">指示捕获了 SQL 异常。</span><span class="sxs-lookup"><span data-stu-id="6348b-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6348b-114">消息</span><span class="sxs-lookup"><span data-stu-id="6348b-114">Message</span></span>  
 <span data-ttu-id="6348b-115">已捕获 SQL 异常编号为 %1 的消息 %2。</span><span class="sxs-lookup"><span data-stu-id="6348b-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6348b-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="6348b-116">Details</span></span>  
  
|<span data-ttu-id="6348b-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="6348b-117">Data Item Name</span></span>|<span data-ttu-id="6348b-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="6348b-118">Data Item Type</span></span>|<span data-ttu-id="6348b-119">描述</span><span class="sxs-lookup"><span data-stu-id="6348b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6348b-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="6348b-120">ErrorNumber</span></span>|<span data-ttu-id="6348b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6348b-121">xs:string</span></span>|<span data-ttu-id="6348b-122">SQL 错误号。</span><span class="sxs-lookup"><span data-stu-id="6348b-122">The SQL error number.</span></span>|  
|<span data-ttu-id="6348b-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="6348b-123">ExceptionMessage</span></span>|<span data-ttu-id="6348b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6348b-124">xs:string</span></span>|<span data-ttu-id="6348b-125">来自 SQL 异常的消息。</span><span class="sxs-lookup"><span data-stu-id="6348b-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="6348b-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6348b-126">AppDomain</span></span>|<span data-ttu-id="6348b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6348b-127">xs:string</span></span>|<span data-ttu-id="6348b-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="6348b-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
