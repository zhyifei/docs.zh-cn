---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: 5979cd8ffe0e05b61af01d2aa98c4a2c63fd432c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781754"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="64d15-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="64d15-102">217 - ClientOperationPrepared</span></span>
## <a name="properties"></a><span data-ttu-id="64d15-103">属性</span><span class="sxs-lookup"><span data-stu-id="64d15-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64d15-104">Id</span><span class="sxs-lookup"><span data-stu-id="64d15-104">ID</span></span>|<span data-ttu-id="64d15-105">217</span><span class="sxs-lookup"><span data-stu-id="64d15-105">217</span></span>|  
|<span data-ttu-id="64d15-106">关键字</span><span class="sxs-lookup"><span data-stu-id="64d15-106">Keywords</span></span>|<span data-ttu-id="64d15-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="64d15-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="64d15-108">级别</span><span class="sxs-lookup"><span data-stu-id="64d15-108">Level</span></span>|<span data-ttu-id="64d15-109">信息</span><span class="sxs-lookup"><span data-stu-id="64d15-109">Information</span></span>|  
|<span data-ttu-id="64d15-110">通道</span><span class="sxs-lookup"><span data-stu-id="64d15-110">Channel</span></span>|<span data-ttu-id="64d15-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="64d15-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="64d15-112">描述</span><span class="sxs-lookup"><span data-stu-id="64d15-112">Description</span></span>  
 <span data-ttu-id="64d15-113">此事件恰好在将操作发送到服务之前由客户端发出。</span><span class="sxs-lookup"><span data-stu-id="64d15-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="64d15-114">消息</span><span class="sxs-lookup"><span data-stu-id="64d15-114">Message</span></span>  
 <span data-ttu-id="64d15-115">客户端正在执行与协定“%2”相关联的操作“%1”。</span><span class="sxs-lookup"><span data-stu-id="64d15-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="64d15-116">消息将发送到“%3”。</span><span class="sxs-lookup"><span data-stu-id="64d15-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="64d15-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="64d15-117">Details</span></span>  
  
|<span data-ttu-id="64d15-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="64d15-118">Data Item Name</span></span>|<span data-ttu-id="64d15-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="64d15-119">Data Item Type</span></span>|<span data-ttu-id="64d15-120">描述</span><span class="sxs-lookup"><span data-stu-id="64d15-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="64d15-121">操作</span><span class="sxs-lookup"><span data-stu-id="64d15-121">Action</span></span>|`xs:string`|<span data-ttu-id="64d15-122">传出消息的 SOAP 操作标头。</span><span class="sxs-lookup"><span data-stu-id="64d15-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="64d15-123">协定名称</span><span class="sxs-lookup"><span data-stu-id="64d15-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="64d15-124">协定的名称。</span><span class="sxs-lookup"><span data-stu-id="64d15-124">The name of the contract.</span></span> <span data-ttu-id="64d15-125">示例:ICalculator。</span><span class="sxs-lookup"><span data-stu-id="64d15-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="64d15-126">目标</span><span class="sxs-lookup"><span data-stu-id="64d15-126">Destination</span></span>|`xs:string`|<span data-ttu-id="64d15-127">消息发送到的服务终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="64d15-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="64d15-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="64d15-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="64d15-129">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="64d15-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="64d15-130">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="64d15-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="64d15-131">示例:默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="64d15-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="64d15-132">应用程序域</span><span class="sxs-lookup"><span data-stu-id="64d15-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="64d15-133">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="64d15-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
