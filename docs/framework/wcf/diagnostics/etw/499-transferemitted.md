---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: b1ade828ee6519288165e272e7d9f36fd6aca9ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33469503"
---
# <a name="499---transferemitted"></a><span data-ttu-id="da543-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="da543-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="da543-103">属性</span><span class="sxs-lookup"><span data-stu-id="da543-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da543-104">Id</span><span class="sxs-lookup"><span data-stu-id="da543-104">ID</span></span>|<span data-ttu-id="da543-105">499</span><span class="sxs-lookup"><span data-stu-id="da543-105">499</span></span>|  
|<span data-ttu-id="da543-106">关键字</span><span class="sxs-lookup"><span data-stu-id="da543-106">Keywords</span></span>|<span data-ttu-id="da543-107">疑难解答，UserEvents，EndToEndMonitoring，ServiceModel，WFTracking，ServiceHost，WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="da543-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="da543-108">级别</span><span class="sxs-lookup"><span data-stu-id="da543-108">Level</span></span>|<span data-ttu-id="da543-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="da543-109">LogAlways</span></span>|  
|<span data-ttu-id="da543-110">通道</span><span class="sxs-lookup"><span data-stu-id="da543-110">Channel</span></span>|<span data-ttu-id="da543-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="da543-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da543-112">描述</span><span class="sxs-lookup"><span data-stu-id="da543-112">Description</span></span>  
 <span data-ttu-id="da543-113">此事件在发生传输事件时发出。</span><span class="sxs-lookup"><span data-stu-id="da543-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da543-114">消息</span><span class="sxs-lookup"><span data-stu-id="da543-114">Message</span></span>  
 <span data-ttu-id="da543-115">发出了传输事件。</span><span class="sxs-lookup"><span data-stu-id="da543-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da543-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="da543-116">Details</span></span>  
  
|<span data-ttu-id="da543-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="da543-117">Data Item Name</span></span>|<span data-ttu-id="da543-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="da543-118">Data Item Type</span></span>|<span data-ttu-id="da543-119">描述</span><span class="sxs-lookup"><span data-stu-id="da543-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da543-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="da543-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="da543-121">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="da543-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="da543-122">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="da543-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="da543-123">示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="da543-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="da543-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="da543-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="da543-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="da543-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
