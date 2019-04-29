---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774265"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="f2dcd-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="f2dcd-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="f2dcd-103">属性</span><span class="sxs-lookup"><span data-stu-id="f2dcd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2dcd-104">Id</span><span class="sxs-lookup"><span data-stu-id="f2dcd-104">ID</span></span>|<span data-ttu-id="f2dcd-105">4209</span><span class="sxs-lookup"><span data-stu-id="f2dcd-105">4209</span></span>|  
|<span data-ttu-id="f2dcd-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f2dcd-106">Keywords</span></span>|<span data-ttu-id="f2dcd-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f2dcd-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f2dcd-108">级别</span><span class="sxs-lookup"><span data-stu-id="f2dcd-108">Level</span></span>|<span data-ttu-id="f2dcd-109">Error</span><span class="sxs-lookup"><span data-stu-id="f2dcd-109">Error</span></span>|  
|<span data-ttu-id="f2dcd-110">通道</span><span class="sxs-lookup"><span data-stu-id="f2dcd-110">Channel</span></span>|<span data-ttu-id="f2dcd-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="f2dcd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f2dcd-112">描述</span><span class="sxs-lookup"><span data-stu-id="f2dcd-112">Description</span></span>  
 <span data-ttu-id="f2dcd-113">指示在尝试打开 SQL 连接时遇到了超时。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f2dcd-114">消息</span><span class="sxs-lookup"><span data-stu-id="f2dcd-114">Message</span></span>  
 <span data-ttu-id="f2dcd-115">尝试打开 SQL 连接时超时。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="f2dcd-116">操作在分配的超时 %1 内没有完成。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="f2dcd-117">分配给此操作的时间可能是更长超时的一部分。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f2dcd-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="f2dcd-118">Details</span></span>  
  
|<span data-ttu-id="f2dcd-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f2dcd-119">Data Item Name</span></span>|<span data-ttu-id="f2dcd-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f2dcd-120">Data Item Type</span></span>|<span data-ttu-id="f2dcd-121">描述</span><span class="sxs-lookup"><span data-stu-id="f2dcd-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f2dcd-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="f2dcd-122">Timeout</span></span>|<span data-ttu-id="f2dcd-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2dcd-123">xs:string</span></span>|<span data-ttu-id="f2dcd-124">用于打开 SQL 连接的超时值。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="f2dcd-125">应用程序域</span><span class="sxs-lookup"><span data-stu-id="f2dcd-125">AppDomain</span></span>|<span data-ttu-id="f2dcd-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2dcd-126">xs:string</span></span>|<span data-ttu-id="f2dcd-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
