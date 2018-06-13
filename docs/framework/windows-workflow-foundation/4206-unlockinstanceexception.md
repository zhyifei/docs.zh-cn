---
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 3c981888b491f2797a431c2103ba3f5f0bd17046
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511168"
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="5a257-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="5a257-102">4206 - UnlockInstanceException</span></span>
## <a name="properties"></a><span data-ttu-id="5a257-103">属性</span><span class="sxs-lookup"><span data-stu-id="5a257-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a257-104">ID</span><span class="sxs-lookup"><span data-stu-id="5a257-104">ID</span></span>|<span data-ttu-id="5a257-105">4206</span><span class="sxs-lookup"><span data-stu-id="5a257-105">4206</span></span>|  
|<span data-ttu-id="5a257-106">关键字</span><span class="sxs-lookup"><span data-stu-id="5a257-106">Keywords</span></span>|<span data-ttu-id="5a257-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5a257-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="5a257-108">级别</span><span class="sxs-lookup"><span data-stu-id="5a257-108">Level</span></span>|<span data-ttu-id="5a257-109">错误</span><span class="sxs-lookup"><span data-stu-id="5a257-109">Error</span></span>|  
|<span data-ttu-id="5a257-110">通道</span><span class="sxs-lookup"><span data-stu-id="5a257-110">Channel</span></span>|<span data-ttu-id="5a257-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="5a257-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5a257-112">描述</span><span class="sxs-lookup"><span data-stu-id="5a257-112">Description</span></span>  
 <span data-ttu-id="5a257-113">指示在尝试解锁某一实例时遇到了异常。</span><span class="sxs-lookup"><span data-stu-id="5a257-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5a257-114">消息</span><span class="sxs-lookup"><span data-stu-id="5a257-114">Message</span></span>  
 <span data-ttu-id="5a257-115">尝试解除实例锁定时遇到异常 %1。</span><span class="sxs-lookup"><span data-stu-id="5a257-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5a257-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="5a257-116">Details</span></span>  
  
|<span data-ttu-id="5a257-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="5a257-117">Data Item Name</span></span>|<span data-ttu-id="5a257-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="5a257-118">Data Item Type</span></span>|<span data-ttu-id="5a257-119">描述</span><span class="sxs-lookup"><span data-stu-id="5a257-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5a257-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="5a257-120">ExceptionMessage</span></span>|<span data-ttu-id="5a257-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5a257-121">xs:string</span></span>|<span data-ttu-id="5a257-122">来自 SQL 异常的消息。</span><span class="sxs-lookup"><span data-stu-id="5a257-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="5a257-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5a257-123">AppDomain</span></span>|<span data-ttu-id="5a257-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5a257-124">xs:string</span></span>|<span data-ttu-id="5a257-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="5a257-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
