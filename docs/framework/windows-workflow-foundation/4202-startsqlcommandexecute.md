---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: 09e079864369115c773c58c451fc5e0a33a3ae9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510346"
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="51827-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="51827-102">4202 - StartSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="51827-103">属性</span><span class="sxs-lookup"><span data-stu-id="51827-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="51827-104">ID</span><span class="sxs-lookup"><span data-stu-id="51827-104">ID</span></span>|<span data-ttu-id="51827-105">4202</span><span class="sxs-lookup"><span data-stu-id="51827-105">4202</span></span>|  
|<span data-ttu-id="51827-106">关键字</span><span class="sxs-lookup"><span data-stu-id="51827-106">Keywords</span></span>|<span data-ttu-id="51827-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="51827-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="51827-108">级别</span><span class="sxs-lookup"><span data-stu-id="51827-108">Level</span></span>|<span data-ttu-id="51827-109">详细</span><span class="sxs-lookup"><span data-stu-id="51827-109">Verbose</span></span>|  
|<span data-ttu-id="51827-110">通道</span><span class="sxs-lookup"><span data-stu-id="51827-110">Channel</span></span>|<span data-ttu-id="51827-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="51827-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="51827-112">描述</span><span class="sxs-lookup"><span data-stu-id="51827-112">Description</span></span>  
 <span data-ttu-id="51827-113">指示 SQL 命令正在执行。</span><span class="sxs-lookup"><span data-stu-id="51827-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="51827-114">消息</span><span class="sxs-lookup"><span data-stu-id="51827-114">Message</span></span>  
 <span data-ttu-id="51827-115">正在开始 SQL 命令执行: %1</span><span class="sxs-lookup"><span data-stu-id="51827-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="51827-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="51827-116">Details</span></span>  
  
|<span data-ttu-id="51827-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="51827-117">Data Item Name</span></span>|<span data-ttu-id="51827-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="51827-118">Data Item Type</span></span>|<span data-ttu-id="51827-119">描述</span><span class="sxs-lookup"><span data-stu-id="51827-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="51827-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="51827-120">SqlCommand</span></span>|<span data-ttu-id="51827-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="51827-121">xs:string</span></span>|<span data-ttu-id="51827-122">已执行的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="51827-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="51827-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="51827-123">AppDomain</span></span>|<span data-ttu-id="51827-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="51827-124">xs:string</span></span>|<span data-ttu-id="51827-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="51827-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
