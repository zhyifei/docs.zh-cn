---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 02d4a4ed1e96983e132a1943dd39f9f885e5596a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781844"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="29502-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="29502-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="29502-103">属性</span><span class="sxs-lookup"><span data-stu-id="29502-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29502-104">Id</span><span class="sxs-lookup"><span data-stu-id="29502-104">ID</span></span>|<span data-ttu-id="29502-105">212</span><span class="sxs-lookup"><span data-stu-id="29502-105">212</span></span>|  
|<span data-ttu-id="29502-106">关键字</span><span class="sxs-lookup"><span data-stu-id="29502-106">Keywords</span></span>|<span data-ttu-id="29502-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="29502-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="29502-108">级别</span><span class="sxs-lookup"><span data-stu-id="29502-108">Level</span></span>|<span data-ttu-id="29502-109">信息</span><span class="sxs-lookup"><span data-stu-id="29502-109">Information</span></span>|  
|<span data-ttu-id="29502-110">通道</span><span class="sxs-lookup"><span data-stu-id="29502-110">Channel</span></span>|<span data-ttu-id="29502-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="29502-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="29502-112">描述</span><span class="sxs-lookup"><span data-stu-id="29502-112">Description</span></span>  
 <span data-ttu-id="29502-113">服务模型对 `BeforeCall` 调用 `ParameterInspector` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="29502-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="29502-114">消息</span><span class="sxs-lookup"><span data-stu-id="29502-114">Message</span></span>  
 <span data-ttu-id="29502-115">调度程序对“%1”类型的 ParameterInspector 调用了“BeforeCall”。</span><span class="sxs-lookup"><span data-stu-id="29502-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="29502-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="29502-116">Details</span></span>  
  
|<span data-ttu-id="29502-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="29502-117">Data Item Name</span></span>|<span data-ttu-id="29502-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="29502-118">Data Item Type</span></span>|<span data-ttu-id="29502-119">描述</span><span class="sxs-lookup"><span data-stu-id="29502-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="29502-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="29502-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="29502-121">所调用检查器的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="29502-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="29502-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="29502-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="29502-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="29502-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="29502-124">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="29502-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="29502-125">示例:默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="29502-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="29502-126">应用程序域</span><span class="sxs-lookup"><span data-stu-id="29502-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="29502-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="29502-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
