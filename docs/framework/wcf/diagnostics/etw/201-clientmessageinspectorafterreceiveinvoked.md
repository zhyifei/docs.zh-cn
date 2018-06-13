---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: 96ca318c141d49e2ac5594d5ee101658a2aa8f21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459019"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="e4aa4-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="e4aa4-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="e4aa4-103">属性</span><span class="sxs-lookup"><span data-stu-id="e4aa4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4aa4-104">Id</span><span class="sxs-lookup"><span data-stu-id="e4aa4-104">ID</span></span>|<span data-ttu-id="e4aa4-105">201</span><span class="sxs-lookup"><span data-stu-id="e4aa4-105">201</span></span>|  
|<span data-ttu-id="e4aa4-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e4aa4-106">Keywords</span></span>|<span data-ttu-id="e4aa4-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e4aa4-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e4aa4-108">级别</span><span class="sxs-lookup"><span data-stu-id="e4aa4-108">Level</span></span>|<span data-ttu-id="e4aa4-109">信息</span><span class="sxs-lookup"><span data-stu-id="e4aa4-109">Information</span></span>|  
|<span data-ttu-id="e4aa4-110">通道</span><span class="sxs-lookup"><span data-stu-id="e4aa4-110">Channel</span></span>|<span data-ttu-id="e4aa4-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="e4aa4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e4aa4-112">描述</span><span class="sxs-lookup"><span data-stu-id="e4aa4-112">Description</span></span>  
 <span data-ttu-id="e4aa4-113">服务模型在客户端消息检查器上调用 `AfterReceiveReply` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e4aa4-114">消息</span><span class="sxs-lookup"><span data-stu-id="e4aa4-114">Message</span></span>  
 <span data-ttu-id="e4aa4-115">调度程序对“%1”类型的 ClientMessageInspector 调用了“AfterReceiveReply”。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e4aa4-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e4aa4-116">Details</span></span>  
  
|<span data-ttu-id="e4aa4-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e4aa4-117">Data Item Name</span></span>|<span data-ttu-id="e4aa4-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e4aa4-118">Data Item Type</span></span>|<span data-ttu-id="e4aa4-119">描述</span><span class="sxs-lookup"><span data-stu-id="e4aa4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e4aa4-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="e4aa4-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="e4aa4-121">所调用检查器的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="e4aa4-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="e4aa4-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="e4aa4-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e4aa4-124">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e4aa4-125">示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e4aa4-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e4aa4-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e4aa4-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e4aa4-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
