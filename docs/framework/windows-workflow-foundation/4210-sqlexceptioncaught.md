---
title: 4210 - SqlExceptionCaught
ms.date: 03/30/2017
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
ms.openlocfilehash: 2493014e80e79ac2935c1bcc685147a74e48fb47
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774252"
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="75dea-102">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="75dea-102">4210 - SqlExceptionCaught</span></span>
## <a name="properties"></a><span data-ttu-id="75dea-103">属性</span><span class="sxs-lookup"><span data-stu-id="75dea-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75dea-104">Id</span><span class="sxs-lookup"><span data-stu-id="75dea-104">ID</span></span>|<span data-ttu-id="75dea-105">4210</span><span class="sxs-lookup"><span data-stu-id="75dea-105">4210</span></span>|  
|<span data-ttu-id="75dea-106">关键字</span><span class="sxs-lookup"><span data-stu-id="75dea-106">Keywords</span></span>|<span data-ttu-id="75dea-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="75dea-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="75dea-108">级别</span><span class="sxs-lookup"><span data-stu-id="75dea-108">Level</span></span>|<span data-ttu-id="75dea-109">警告</span><span class="sxs-lookup"><span data-stu-id="75dea-109">Warning</span></span>|  
|<span data-ttu-id="75dea-110">通道</span><span class="sxs-lookup"><span data-stu-id="75dea-110">Channel</span></span>|<span data-ttu-id="75dea-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="75dea-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="75dea-112">描述</span><span class="sxs-lookup"><span data-stu-id="75dea-112">Description</span></span>  
 <span data-ttu-id="75dea-113">指示捕获了 SQL 异常。</span><span class="sxs-lookup"><span data-stu-id="75dea-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="75dea-114">消息</span><span class="sxs-lookup"><span data-stu-id="75dea-114">Message</span></span>  
 <span data-ttu-id="75dea-115">已捕获 SQL 异常编号为 %1 的消息 %2。</span><span class="sxs-lookup"><span data-stu-id="75dea-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="75dea-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="75dea-116">Details</span></span>  
  
|<span data-ttu-id="75dea-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="75dea-117">Data Item Name</span></span>|<span data-ttu-id="75dea-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="75dea-118">Data Item Type</span></span>|<span data-ttu-id="75dea-119">描述</span><span class="sxs-lookup"><span data-stu-id="75dea-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="75dea-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="75dea-120">ErrorNumber</span></span>|<span data-ttu-id="75dea-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="75dea-121">xs:string</span></span>|<span data-ttu-id="75dea-122">SQL 错误号。</span><span class="sxs-lookup"><span data-stu-id="75dea-122">The SQL error number.</span></span>|  
|<span data-ttu-id="75dea-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="75dea-123">ExceptionMessage</span></span>|<span data-ttu-id="75dea-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="75dea-124">xs:string</span></span>|<span data-ttu-id="75dea-125">来自 SQL 异常的消息。</span><span class="sxs-lookup"><span data-stu-id="75dea-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="75dea-126">应用程序域</span><span class="sxs-lookup"><span data-stu-id="75dea-126">AppDomain</span></span>|<span data-ttu-id="75dea-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="75dea-127">xs:string</span></span>|<span data-ttu-id="75dea-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="75dea-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
