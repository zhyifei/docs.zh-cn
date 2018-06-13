---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 75c1cdd10aca6b177911bd9d2f51468016eb9e15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510216"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="e2f24-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="e2f24-102">4201 - EndSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="e2f24-103">属性</span><span class="sxs-lookup"><span data-stu-id="e2f24-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2f24-104">ID</span><span class="sxs-lookup"><span data-stu-id="e2f24-104">ID</span></span>|<span data-ttu-id="e2f24-105">4201</span><span class="sxs-lookup"><span data-stu-id="e2f24-105">4201</span></span>|  
|<span data-ttu-id="e2f24-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e2f24-106">Keywords</span></span>|<span data-ttu-id="e2f24-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="e2f24-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="e2f24-108">级别</span><span class="sxs-lookup"><span data-stu-id="e2f24-108">Level</span></span>|<span data-ttu-id="e2f24-109">详细</span><span class="sxs-lookup"><span data-stu-id="e2f24-109">Verbose</span></span>|  
|<span data-ttu-id="e2f24-110">通道</span><span class="sxs-lookup"><span data-stu-id="e2f24-110">Channel</span></span>|<span data-ttu-id="e2f24-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="e2f24-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e2f24-112">描述</span><span class="sxs-lookup"><span data-stu-id="e2f24-112">Description</span></span>  
 <span data-ttu-id="e2f24-113">指示 SQL 命令已完成执行。</span><span class="sxs-lookup"><span data-stu-id="e2f24-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e2f24-114">消息</span><span class="sxs-lookup"><span data-stu-id="e2f24-114">Message</span></span>  
 <span data-ttu-id="e2f24-115">结束 SQL 命令执行: %1</span><span class="sxs-lookup"><span data-stu-id="e2f24-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="e2f24-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e2f24-116">Details</span></span>  
  
|<span data-ttu-id="e2f24-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e2f24-117">Data Item Name</span></span>|<span data-ttu-id="e2f24-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e2f24-118">Data Item Type</span></span>|<span data-ttu-id="e2f24-119">描述</span><span class="sxs-lookup"><span data-stu-id="e2f24-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e2f24-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="e2f24-120">SqlCommand</span></span>|<span data-ttu-id="e2f24-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e2f24-121">xs:string</span></span>|<span data-ttu-id="e2f24-122">已执行的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="e2f24-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="e2f24-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e2f24-123">AppDomain</span></span>|<span data-ttu-id="e2f24-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e2f24-124">xs:string</span></span>|<span data-ttu-id="e2f24-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e2f24-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
