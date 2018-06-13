---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 40a92d77c57728249569a854eab8767ff371bca2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458814"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="b90b0-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="b90b0-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="b90b0-103">属性</span><span class="sxs-lookup"><span data-stu-id="b90b0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b90b0-104">Id</span><span class="sxs-lookup"><span data-stu-id="b90b0-104">ID</span></span>|<span data-ttu-id="b90b0-105">206</span><span class="sxs-lookup"><span data-stu-id="b90b0-105">206</span></span>|  
|<span data-ttu-id="b90b0-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b90b0-106">Keywords</span></span>|<span data-ttu-id="b90b0-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b90b0-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b90b0-108">级别</span><span class="sxs-lookup"><span data-stu-id="b90b0-108">Level</span></span>|<span data-ttu-id="b90b0-109">信息</span><span class="sxs-lookup"><span data-stu-id="b90b0-109">Information</span></span>|  
|<span data-ttu-id="b90b0-110">通道</span><span class="sxs-lookup"><span data-stu-id="b90b0-110">Channel</span></span>|<span data-ttu-id="b90b0-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="b90b0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b90b0-112">描述</span><span class="sxs-lookup"><span data-stu-id="b90b0-112">Description</span></span>  
 <span data-ttu-id="b90b0-113">当 `ErrorHandler` 有机会处理在服务操作中发生的异常后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="b90b0-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b90b0-114">消息</span><span class="sxs-lookup"><span data-stu-id="b90b0-114">Message</span></span>  
 <span data-ttu-id="b90b0-115">调度程序调用类型 '%1' 的类型"%3"的异常 errorhandler 来的处理。</span><span class="sxs-lookup"><span data-stu-id="b90b0-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="b90b0-116">ErrorHandled 为“%2”。</span><span class="sxs-lookup"><span data-stu-id="b90b0-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b90b0-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="b90b0-117">Details</span></span>  
  
|<span data-ttu-id="b90b0-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b90b0-118">Data Item Name</span></span>|<span data-ttu-id="b90b0-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b90b0-119">Data Item Type</span></span>|<span data-ttu-id="b90b0-120">描述</span><span class="sxs-lookup"><span data-stu-id="b90b0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b90b0-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="b90b0-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="b90b0-122">所调用 `ErrorHandler` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="b90b0-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="b90b0-123">Handled</span><span class="sxs-lookup"><span data-stu-id="b90b0-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="b90b0-124">如果错误处理程序已处理错误，则为 `true`；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b90b0-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="b90b0-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="b90b0-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="b90b0-126">待处理异常的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="b90b0-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="b90b0-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="b90b0-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="b90b0-128">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="b90b0-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b90b0-129">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="b90b0-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b90b0-130">示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="b90b0-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b90b0-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b90b0-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b90b0-132">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b90b0-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
