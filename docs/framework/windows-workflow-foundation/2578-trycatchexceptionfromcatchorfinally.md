---
title: 2578 - TryCatchExceptionFromCatchOrFinally
ms.date: 03/30/2017
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
ms.openlocfilehash: 46fb52e665d49ed7a0336dbeeb6ed07f0d479fb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755605"
---
# <a name="2578---trycatchexceptionfromcatchorfinally"></a><span data-ttu-id="c80e2-102">2578 - TryCatchExceptionFromCatchOrFinally</span><span class="sxs-lookup"><span data-stu-id="c80e2-102">2578 - TryCatchExceptionFromCatchOrFinally</span></span>
## <a name="properties"></a><span data-ttu-id="c80e2-103">属性</span><span class="sxs-lookup"><span data-stu-id="c80e2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c80e2-104">Id</span><span class="sxs-lookup"><span data-stu-id="c80e2-104">ID</span></span>|<span data-ttu-id="c80e2-105">2578</span><span class="sxs-lookup"><span data-stu-id="c80e2-105">2578</span></span>|  
|<span data-ttu-id="c80e2-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c80e2-106">Keywords</span></span>|<span data-ttu-id="c80e2-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="c80e2-107">WFActivities</span></span>|  
|<span data-ttu-id="c80e2-108">级别</span><span class="sxs-lookup"><span data-stu-id="c80e2-108">Level</span></span>|<span data-ttu-id="c80e2-109">警告</span><span class="sxs-lookup"><span data-stu-id="c80e2-109">Warning</span></span>|  
|<span data-ttu-id="c80e2-110">通道</span><span class="sxs-lookup"><span data-stu-id="c80e2-110">Channel</span></span>|<span data-ttu-id="c80e2-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c80e2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c80e2-112">描述</span><span class="sxs-lookup"><span data-stu-id="c80e2-112">Description</span></span>  
 <span data-ttu-id="c80e2-113">指示 Catch 或 Finally 活动引发了异常。</span><span class="sxs-lookup"><span data-stu-id="c80e2-113">Indicates a Catch or Finally activity has thrown an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c80e2-114">消息</span><span class="sxs-lookup"><span data-stu-id="c80e2-114">Message</span></span>  
 <span data-ttu-id="c80e2-115">与 TryCatch 活动“%1”关联的 Catch 或 Finally 活动引发了异常。</span><span class="sxs-lookup"><span data-stu-id="c80e2-115">A Catch or Finally activity that is associated with the TryCatch activity '%1' has thrown an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c80e2-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="c80e2-116">Details</span></span>  
  
|<span data-ttu-id="c80e2-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c80e2-117">Data Item Name</span></span>|<span data-ttu-id="c80e2-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c80e2-118">Data Item Type</span></span>|<span data-ttu-id="c80e2-119">描述</span><span class="sxs-lookup"><span data-stu-id="c80e2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c80e2-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c80e2-120">DisplayName</span></span>|<span data-ttu-id="c80e2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c80e2-121">xs:string</span></span>|<span data-ttu-id="c80e2-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c80e2-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="c80e2-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="c80e2-123">AppDomain</span></span>|<span data-ttu-id="c80e2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c80e2-124">xs:string</span></span>|<span data-ttu-id="c80e2-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c80e2-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
