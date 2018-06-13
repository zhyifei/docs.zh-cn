---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 714a98a300426d80c3b494d701ae1bd53a49592f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512289"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="192fe-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="192fe-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="192fe-103">属性</span><span class="sxs-lookup"><span data-stu-id="192fe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="192fe-104">ID</span><span class="sxs-lookup"><span data-stu-id="192fe-104">ID</span></span>|<span data-ttu-id="192fe-105">1126</span><span class="sxs-lookup"><span data-stu-id="192fe-105">1126</span></span>|  
|<span data-ttu-id="192fe-106">关键字</span><span class="sxs-lookup"><span data-stu-id="192fe-106">Keywords</span></span>|<span data-ttu-id="192fe-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="192fe-107">WFRuntime</span></span>|  
|<span data-ttu-id="192fe-108">级别</span><span class="sxs-lookup"><span data-stu-id="192fe-108">Level</span></span>|<span data-ttu-id="192fe-109">信息</span><span class="sxs-lookup"><span data-stu-id="192fe-109">Information</span></span>|  
|<span data-ttu-id="192fe-110">通道</span><span class="sxs-lookup"><span data-stu-id="192fe-110">Channel</span></span>|<span data-ttu-id="192fe-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="192fe-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="192fe-112">描述</span><span class="sxs-lookup"><span data-stu-id="192fe-112">Description</span></span>  
 <span data-ttu-id="192fe-113">指示 InvokeMethod 活动调用的方法引发了异常。</span><span class="sxs-lookup"><span data-stu-id="192fe-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="192fe-114">消息</span><span class="sxs-lookup"><span data-stu-id="192fe-114">Message</span></span>  
 <span data-ttu-id="192fe-115">在活动“%1”调用的方法中，引发了异常。</span><span class="sxs-lookup"><span data-stu-id="192fe-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="192fe-116">%2</span><span class="sxs-lookup"><span data-stu-id="192fe-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="192fe-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="192fe-117">Details</span></span>  
  
|<span data-ttu-id="192fe-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="192fe-118">Data Item Name</span></span>|<span data-ttu-id="192fe-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="192fe-119">Data Item Type</span></span>|<span data-ttu-id="192fe-120">描述</span><span class="sxs-lookup"><span data-stu-id="192fe-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="192fe-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="192fe-121">InvokeMethod</span></span>|<span data-ttu-id="192fe-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="192fe-122">xs:string</span></span>|<span data-ttu-id="192fe-123">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="192fe-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="192fe-124">例外</span><span class="sxs-lookup"><span data-stu-id="192fe-124">Exception</span></span>|<span data-ttu-id="192fe-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="192fe-125">xs:string</span></span>|<span data-ttu-id="192fe-126">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="192fe-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="192fe-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="192fe-127">AppDomain</span></span>|<span data-ttu-id="192fe-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="192fe-128">xs:string</span></span>|<span data-ttu-id="192fe-129">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="192fe-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
