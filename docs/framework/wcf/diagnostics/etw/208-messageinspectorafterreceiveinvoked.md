---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 3499131fcb52f0a0ab6d0e78e165522b7092612f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458893"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="10ad7-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="10ad7-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="10ad7-103">属性</span><span class="sxs-lookup"><span data-stu-id="10ad7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10ad7-104">ID</span><span class="sxs-lookup"><span data-stu-id="10ad7-104">ID</span></span>|<span data-ttu-id="10ad7-105">208</span><span class="sxs-lookup"><span data-stu-id="10ad7-105">208</span></span>|  
|<span data-ttu-id="10ad7-106">关键字</span><span class="sxs-lookup"><span data-stu-id="10ad7-106">Keywords</span></span>|<span data-ttu-id="10ad7-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="10ad7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="10ad7-108">级别</span><span class="sxs-lookup"><span data-stu-id="10ad7-108">Level</span></span>|<span data-ttu-id="10ad7-109">信息</span><span class="sxs-lookup"><span data-stu-id="10ad7-109">Information</span></span>|  
|<span data-ttu-id="10ad7-110">通道</span><span class="sxs-lookup"><span data-stu-id="10ad7-110">Channel</span></span>|<span data-ttu-id="10ad7-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="10ad7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="10ad7-112">描述</span><span class="sxs-lookup"><span data-stu-id="10ad7-112">Description</span></span>  
 <span data-ttu-id="10ad7-113">服务模型对消息检查器调用 `AfterReceive` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="10ad7-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="10ad7-114">消息</span><span class="sxs-lookup"><span data-stu-id="10ad7-114">Message</span></span>  
 <span data-ttu-id="10ad7-115">调度程序对“%1”类型的 MessageInspector 调用了“AfterReceiveReply”。</span><span class="sxs-lookup"><span data-stu-id="10ad7-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="10ad7-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="10ad7-116">Details</span></span>  
  
|<span data-ttu-id="10ad7-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="10ad7-117">Data Item Name</span></span>|<span data-ttu-id="10ad7-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="10ad7-118">Data Item Type</span></span>|<span data-ttu-id="10ad7-119">描述</span><span class="sxs-lookup"><span data-stu-id="10ad7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="10ad7-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="10ad7-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="10ad7-121">所调用 `MessageInspector` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="10ad7-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="10ad7-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="10ad7-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="10ad7-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="10ad7-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="10ad7-124">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="10ad7-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="10ad7-125">示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="10ad7-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="10ad7-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="10ad7-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="10ad7-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="10ad7-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
