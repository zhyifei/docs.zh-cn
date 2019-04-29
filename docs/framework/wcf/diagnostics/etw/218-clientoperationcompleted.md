---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: 83f39be84a8d62962b85652b0e39b537c92e612c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781755"
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="d1efe-102">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="d1efe-102">218 - ClientOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="d1efe-103">属性</span><span class="sxs-lookup"><span data-stu-id="d1efe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1efe-104">Id</span><span class="sxs-lookup"><span data-stu-id="d1efe-104">ID</span></span>|<span data-ttu-id="d1efe-105">218</span><span class="sxs-lookup"><span data-stu-id="d1efe-105">218</span></span>|  
|<span data-ttu-id="d1efe-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d1efe-106">Keywords</span></span>|<span data-ttu-id="d1efe-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d1efe-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d1efe-108">级别</span><span class="sxs-lookup"><span data-stu-id="d1efe-108">Level</span></span>|<span data-ttu-id="d1efe-109">信息</span><span class="sxs-lookup"><span data-stu-id="d1efe-109">Information</span></span>|  
|<span data-ttu-id="d1efe-110">通道</span><span class="sxs-lookup"><span data-stu-id="d1efe-110">Channel</span></span>|<span data-ttu-id="d1efe-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="d1efe-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d1efe-112">描述</span><span class="sxs-lookup"><span data-stu-id="d1efe-112">Description</span></span>  
 <span data-ttu-id="d1efe-113">此事件恰好在操作完成之后由客户端发出。</span><span class="sxs-lookup"><span data-stu-id="d1efe-113">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="d1efe-114">对于单向操作，此事件恰好在成功发送消息之后发送。</span><span class="sxs-lookup"><span data-stu-id="d1efe-114">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="d1efe-115">对于请求-响应操作，此事件在接收响应之后发送。</span><span class="sxs-lookup"><span data-stu-id="d1efe-115">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d1efe-116">消息</span><span class="sxs-lookup"><span data-stu-id="d1efe-116">Message</span></span>  
 <span data-ttu-id="d1efe-117">客户端已执行完与协定“%2”相关联的操作“%1”。</span><span class="sxs-lookup"><span data-stu-id="d1efe-117">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="d1efe-118">消息已发送到“%3”。</span><span class="sxs-lookup"><span data-stu-id="d1efe-118">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d1efe-119">详细信息</span><span class="sxs-lookup"><span data-stu-id="d1efe-119">Details</span></span>  
  
|<span data-ttu-id="d1efe-120">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d1efe-120">Data Item Name</span></span>|<span data-ttu-id="d1efe-121">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d1efe-121">Data Item Type</span></span>|<span data-ttu-id="d1efe-122">描述</span><span class="sxs-lookup"><span data-stu-id="d1efe-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d1efe-123">操作</span><span class="sxs-lookup"><span data-stu-id="d1efe-123">Action</span></span>|<span data-ttu-id="d1efe-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d1efe-124">xs:string</span></span>|<span data-ttu-id="d1efe-125">传出消息的 SOAP 操作标头。</span><span class="sxs-lookup"><span data-stu-id="d1efe-125">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="d1efe-126">协定名称</span><span class="sxs-lookup"><span data-stu-id="d1efe-126">Contract Name</span></span>|`xs:string`|<span data-ttu-id="d1efe-127">协定的名称。</span><span class="sxs-lookup"><span data-stu-id="d1efe-127">The name of the contract.</span></span> <span data-ttu-id="d1efe-128">示例:ICalculator。</span><span class="sxs-lookup"><span data-stu-id="d1efe-128">Example: ICalculator.</span></span>|  
|<span data-ttu-id="d1efe-129">目标</span><span class="sxs-lookup"><span data-stu-id="d1efe-129">Destination</span></span>|`xs:string`|<span data-ttu-id="d1efe-130">消息已发送到的服务终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="d1efe-130">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="d1efe-131">HostReference</span><span class="sxs-lookup"><span data-stu-id="d1efe-131">HostReference</span></span>|`xs:string`|<span data-ttu-id="d1efe-132">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="d1efe-132">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d1efe-133">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="d1efe-133">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d1efe-134">示例:默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="d1efe-134">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d1efe-135">应用程序域</span><span class="sxs-lookup"><span data-stu-id="d1efe-135">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d1efe-136">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d1efe-136">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
