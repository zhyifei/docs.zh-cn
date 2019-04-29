---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 75c1cdd10aca6b177911bd9d2f51468016eb9e15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774356"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="c6d96-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="c6d96-102">4201 - EndSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="c6d96-103">属性</span><span class="sxs-lookup"><span data-stu-id="c6d96-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6d96-104">Id</span><span class="sxs-lookup"><span data-stu-id="c6d96-104">ID</span></span>|<span data-ttu-id="c6d96-105">4201</span><span class="sxs-lookup"><span data-stu-id="c6d96-105">4201</span></span>|  
|<span data-ttu-id="c6d96-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c6d96-106">Keywords</span></span>|<span data-ttu-id="c6d96-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c6d96-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c6d96-108">级别</span><span class="sxs-lookup"><span data-stu-id="c6d96-108">Level</span></span>|<span data-ttu-id="c6d96-109">详细</span><span class="sxs-lookup"><span data-stu-id="c6d96-109">Verbose</span></span>|  
|<span data-ttu-id="c6d96-110">通道</span><span class="sxs-lookup"><span data-stu-id="c6d96-110">Channel</span></span>|<span data-ttu-id="c6d96-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c6d96-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c6d96-112">描述</span><span class="sxs-lookup"><span data-stu-id="c6d96-112">Description</span></span>  
 <span data-ttu-id="c6d96-113">指示 SQL 命令已完成执行。</span><span class="sxs-lookup"><span data-stu-id="c6d96-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c6d96-114">消息</span><span class="sxs-lookup"><span data-stu-id="c6d96-114">Message</span></span>  
 <span data-ttu-id="c6d96-115">结束 SQL 命令执行: %1</span><span class="sxs-lookup"><span data-stu-id="c6d96-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="c6d96-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="c6d96-116">Details</span></span>  
  
|<span data-ttu-id="c6d96-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c6d96-117">Data Item Name</span></span>|<span data-ttu-id="c6d96-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c6d96-118">Data Item Type</span></span>|<span data-ttu-id="c6d96-119">描述</span><span class="sxs-lookup"><span data-stu-id="c6d96-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c6d96-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="c6d96-120">SqlCommand</span></span>|<span data-ttu-id="c6d96-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c6d96-121">xs:string</span></span>|<span data-ttu-id="c6d96-122">已执行的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="c6d96-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="c6d96-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="c6d96-123">AppDomain</span></span>|<span data-ttu-id="c6d96-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c6d96-124">xs:string</span></span>|<span data-ttu-id="c6d96-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c6d96-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
