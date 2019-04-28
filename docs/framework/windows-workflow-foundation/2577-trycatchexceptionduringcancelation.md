---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: c272dd91249dfc90e6f4c38a7339919a5a6446e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755618"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="87f2a-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="87f2a-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="87f2a-103">属性</span><span class="sxs-lookup"><span data-stu-id="87f2a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87f2a-104">Id</span><span class="sxs-lookup"><span data-stu-id="87f2a-104">ID</span></span>|<span data-ttu-id="87f2a-105">2577</span><span class="sxs-lookup"><span data-stu-id="87f2a-105">2577</span></span>|  
|<span data-ttu-id="87f2a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="87f2a-106">Keywords</span></span>|<span data-ttu-id="87f2a-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="87f2a-107">WFActivities</span></span>|  
|<span data-ttu-id="87f2a-108">级别</span><span class="sxs-lookup"><span data-stu-id="87f2a-108">Level</span></span>|<span data-ttu-id="87f2a-109">警告</span><span class="sxs-lookup"><span data-stu-id="87f2a-109">Warning</span></span>|  
|<span data-ttu-id="87f2a-110">通道</span><span class="sxs-lookup"><span data-stu-id="87f2a-110">Channel</span></span>|<span data-ttu-id="87f2a-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="87f2a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="87f2a-112">描述</span><span class="sxs-lookup"><span data-stu-id="87f2a-112">Description</span></span>  
 <span data-ttu-id="87f2a-113">支持 TryCatch 活动的子活动在取消过程中引发了异常。</span><span class="sxs-lookup"><span data-stu-id="87f2a-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="87f2a-114">消息</span><span class="sxs-lookup"><span data-stu-id="87f2a-114">Message</span></span>  
 <span data-ttu-id="87f2a-115">TryCatch 活动“%1”的子活动在取消过程中引发了异常。</span><span class="sxs-lookup"><span data-stu-id="87f2a-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="87f2a-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="87f2a-116">Details</span></span>  
  
|<span data-ttu-id="87f2a-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="87f2a-117">Data Item Name</span></span>|<span data-ttu-id="87f2a-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="87f2a-118">Data Item Type</span></span>|<span data-ttu-id="87f2a-119">描述</span><span class="sxs-lookup"><span data-stu-id="87f2a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="87f2a-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="87f2a-120">DisplayName</span></span>|<span data-ttu-id="87f2a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="87f2a-121">xs:string</span></span>|<span data-ttu-id="87f2a-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="87f2a-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="87f2a-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="87f2a-123">AppDomain</span></span>|<span data-ttu-id="87f2a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="87f2a-124">xs:string</span></span>|<span data-ttu-id="87f2a-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="87f2a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
