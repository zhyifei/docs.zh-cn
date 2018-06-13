---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512179"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="ec0e7-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="ec0e7-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="ec0e7-103">属性</span><span class="sxs-lookup"><span data-stu-id="ec0e7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec0e7-104">ID</span><span class="sxs-lookup"><span data-stu-id="ec0e7-104">ID</span></span>|<span data-ttu-id="ec0e7-105">3508</span><span class="sxs-lookup"><span data-stu-id="ec0e7-105">3508</span></span>|  
|<span data-ttu-id="ec0e7-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ec0e7-106">Keywords</span></span>|<span data-ttu-id="ec0e7-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ec0e7-107">WFServices</span></span>|  
|<span data-ttu-id="ec0e7-108">级别</span><span class="sxs-lookup"><span data-stu-id="ec0e7-108">Level</span></span>|<span data-ttu-id="ec0e7-109">详细</span><span class="sxs-lookup"><span data-stu-id="ec0e7-109">Verbose</span></span>|  
|<span data-ttu-id="ec0e7-110">通道</span><span class="sxs-lookup"><span data-stu-id="ec0e7-110">Channel</span></span>|<span data-ttu-id="ec0e7-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="ec0e7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ec0e7-112">描述</span><span class="sxs-lookup"><span data-stu-id="ec0e7-112">Description</span></span>  
 <span data-ttu-id="ec0e7-113">指示在配置文件中找不到 TrackingProfile，或 ActivityDefinitionId 与配置文件不匹配。</span><span class="sxs-lookup"><span data-stu-id="ec0e7-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ec0e7-114">消息</span><span class="sxs-lookup"><span data-stu-id="ec0e7-114">Message</span></span>  
 <span data-ttu-id="ec0e7-115">未找到 ActivityDefinitionId“%2”的 TrackingProfile“%1”。</span><span class="sxs-lookup"><span data-stu-id="ec0e7-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="ec0e7-116">在配置文件中找不到 TrackingProfile，或 ActivityDefinitionId 不匹配。</span><span class="sxs-lookup"><span data-stu-id="ec0e7-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ec0e7-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="ec0e7-117">Details</span></span>  
  
|<span data-ttu-id="ec0e7-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ec0e7-118">Data Item Name</span></span>|<span data-ttu-id="ec0e7-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ec0e7-119">Data Item Type</span></span>|<span data-ttu-id="ec0e7-120">描述</span><span class="sxs-lookup"><span data-stu-id="ec0e7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ec0e7-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="ec0e7-121">TrackingProfile</span></span>|<span data-ttu-id="ec0e7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec0e7-122">xs:string</span></span>|<span data-ttu-id="ec0e7-123">跟踪配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ec0e7-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="ec0e7-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="ec0e7-124">ActivityDefinitionId</span></span>|<span data-ttu-id="ec0e7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec0e7-125">xs:string</span></span>|<span data-ttu-id="ec0e7-126">活动定义 ID。</span><span class="sxs-lookup"><span data-stu-id="ec0e7-126">The activity definition id.</span></span>|  
|<span data-ttu-id="ec0e7-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ec0e7-127">AppDomain</span></span>|<span data-ttu-id="ec0e7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec0e7-128">xs:string</span></span>|<span data-ttu-id="ec0e7-129">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec0e7-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
