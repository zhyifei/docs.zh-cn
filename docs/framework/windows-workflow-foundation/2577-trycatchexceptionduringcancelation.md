---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: c272dd91249dfc90e6f4c38a7339919a5a6446e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510715"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="1ca75-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="1ca75-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="1ca75-103">属性</span><span class="sxs-lookup"><span data-stu-id="1ca75-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ca75-104">ID</span><span class="sxs-lookup"><span data-stu-id="1ca75-104">ID</span></span>|<span data-ttu-id="1ca75-105">2577</span><span class="sxs-lookup"><span data-stu-id="1ca75-105">2577</span></span>|  
|<span data-ttu-id="1ca75-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1ca75-106">Keywords</span></span>|<span data-ttu-id="1ca75-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="1ca75-107">WFActivities</span></span>|  
|<span data-ttu-id="1ca75-108">级别</span><span class="sxs-lookup"><span data-stu-id="1ca75-108">Level</span></span>|<span data-ttu-id="1ca75-109">警告</span><span class="sxs-lookup"><span data-stu-id="1ca75-109">Warning</span></span>|  
|<span data-ttu-id="1ca75-110">通道</span><span class="sxs-lookup"><span data-stu-id="1ca75-110">Channel</span></span>|<span data-ttu-id="1ca75-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1ca75-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1ca75-112">描述</span><span class="sxs-lookup"><span data-stu-id="1ca75-112">Description</span></span>  
 <span data-ttu-id="1ca75-113">支持 TryCatch 活动的子活动在取消过程中引发了异常。</span><span class="sxs-lookup"><span data-stu-id="1ca75-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1ca75-114">消息</span><span class="sxs-lookup"><span data-stu-id="1ca75-114">Message</span></span>  
 <span data-ttu-id="1ca75-115">TryCatch 活动“%1”的子活动在取消过程中引发了异常。</span><span class="sxs-lookup"><span data-stu-id="1ca75-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1ca75-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="1ca75-116">Details</span></span>  
  
|<span data-ttu-id="1ca75-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1ca75-117">Data Item Name</span></span>|<span data-ttu-id="1ca75-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1ca75-118">Data Item Type</span></span>|<span data-ttu-id="1ca75-119">描述</span><span class="sxs-lookup"><span data-stu-id="1ca75-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1ca75-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1ca75-120">DisplayName</span></span>|<span data-ttu-id="1ca75-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ca75-121">xs:string</span></span>|<span data-ttu-id="1ca75-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1ca75-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="1ca75-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1ca75-123">AppDomain</span></span>|<span data-ttu-id="1ca75-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ca75-124">xs:string</span></span>|<span data-ttu-id="1ca75-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1ca75-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
