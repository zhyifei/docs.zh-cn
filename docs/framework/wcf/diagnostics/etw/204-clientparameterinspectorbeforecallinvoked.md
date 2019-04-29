---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: eb060cfa79b75452deae67705126a24b7ca9ffef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782026"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="9a163-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="9a163-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="9a163-103">属性</span><span class="sxs-lookup"><span data-stu-id="9a163-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a163-104">Id</span><span class="sxs-lookup"><span data-stu-id="9a163-104">ID</span></span>|<span data-ttu-id="9a163-105">204</span><span class="sxs-lookup"><span data-stu-id="9a163-105">204</span></span>|  
|<span data-ttu-id="9a163-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9a163-106">Keywords</span></span>|<span data-ttu-id="9a163-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9a163-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9a163-108">级别</span><span class="sxs-lookup"><span data-stu-id="9a163-108">Level</span></span>|<span data-ttu-id="9a163-109">信息</span><span class="sxs-lookup"><span data-stu-id="9a163-109">Information</span></span>|  
|<span data-ttu-id="9a163-110">通道</span><span class="sxs-lookup"><span data-stu-id="9a163-110">Channel</span></span>|<span data-ttu-id="9a163-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="9a163-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9a163-112">描述</span><span class="sxs-lookup"><span data-stu-id="9a163-112">Description</span></span>  
 <span data-ttu-id="9a163-113">服务模型在客户端参数检查器上调用 `BeforeCall` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="9a163-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9a163-114">消息</span><span class="sxs-lookup"><span data-stu-id="9a163-114">Message</span></span>  
 <span data-ttu-id="9a163-115">调度程序对“%1”类型的 ClientParameterInspector 调用了“BeforeCall”。</span><span class="sxs-lookup"><span data-stu-id="9a163-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9a163-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="9a163-116">Details</span></span>  
  
|<span data-ttu-id="9a163-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9a163-117">Data Item Name</span></span>|<span data-ttu-id="9a163-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9a163-118">Data Item Type</span></span>|<span data-ttu-id="9a163-119">描述</span><span class="sxs-lookup"><span data-stu-id="9a163-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9a163-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="9a163-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="9a163-121">所调用检查器的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="9a163-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="9a163-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="9a163-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="9a163-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="9a163-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9a163-124">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="9a163-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9a163-125">示例:默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="9a163-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9a163-126">应用程序域</span><span class="sxs-lookup"><span data-stu-id="9a163-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9a163-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9a163-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
