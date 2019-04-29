---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: 09e079864369115c773c58c451fc5e0a33a3ae9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774369"
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="1dadf-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="1dadf-102">4202 - StartSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="1dadf-103">属性</span><span class="sxs-lookup"><span data-stu-id="1dadf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1dadf-104">Id</span><span class="sxs-lookup"><span data-stu-id="1dadf-104">ID</span></span>|<span data-ttu-id="1dadf-105">4202</span><span class="sxs-lookup"><span data-stu-id="1dadf-105">4202</span></span>|  
|<span data-ttu-id="1dadf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1dadf-106">Keywords</span></span>|<span data-ttu-id="1dadf-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="1dadf-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="1dadf-108">级别</span><span class="sxs-lookup"><span data-stu-id="1dadf-108">Level</span></span>|<span data-ttu-id="1dadf-109">详细</span><span class="sxs-lookup"><span data-stu-id="1dadf-109">Verbose</span></span>|  
|<span data-ttu-id="1dadf-110">通道</span><span class="sxs-lookup"><span data-stu-id="1dadf-110">Channel</span></span>|<span data-ttu-id="1dadf-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1dadf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1dadf-112">描述</span><span class="sxs-lookup"><span data-stu-id="1dadf-112">Description</span></span>  
 <span data-ttu-id="1dadf-113">指示 SQL 命令正在执行。</span><span class="sxs-lookup"><span data-stu-id="1dadf-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1dadf-114">消息</span><span class="sxs-lookup"><span data-stu-id="1dadf-114">Message</span></span>  
 <span data-ttu-id="1dadf-115">正在开始 SQL 命令执行: %1</span><span class="sxs-lookup"><span data-stu-id="1dadf-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="1dadf-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="1dadf-116">Details</span></span>  
  
|<span data-ttu-id="1dadf-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1dadf-117">Data Item Name</span></span>|<span data-ttu-id="1dadf-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1dadf-118">Data Item Type</span></span>|<span data-ttu-id="1dadf-119">描述</span><span class="sxs-lookup"><span data-stu-id="1dadf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1dadf-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="1dadf-120">SqlCommand</span></span>|<span data-ttu-id="1dadf-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1dadf-121">xs:string</span></span>|<span data-ttu-id="1dadf-122">已执行的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="1dadf-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="1dadf-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="1dadf-123">AppDomain</span></span>|<span data-ttu-id="1dadf-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1dadf-124">xs:string</span></span>|<span data-ttu-id="1dadf-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1dadf-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
