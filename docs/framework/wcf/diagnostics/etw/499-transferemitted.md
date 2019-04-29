---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: b1ade828ee6519288165e272e7d9f36fd6aca9ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774928"
---
# <a name="499---transferemitted"></a><span data-ttu-id="f614f-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="f614f-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="f614f-103">属性</span><span class="sxs-lookup"><span data-stu-id="f614f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f614f-104">Id</span><span class="sxs-lookup"><span data-stu-id="f614f-104">ID</span></span>|<span data-ttu-id="f614f-105">499</span><span class="sxs-lookup"><span data-stu-id="f614f-105">499</span></span>|  
|<span data-ttu-id="f614f-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f614f-106">Keywords</span></span>|<span data-ttu-id="f614f-107">疑难解答，UserEvents，EndToEndMonitoring，ServiceModel，WFTracking，ServiceHost，WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="f614f-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="f614f-108">级别</span><span class="sxs-lookup"><span data-stu-id="f614f-108">Level</span></span>|<span data-ttu-id="f614f-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="f614f-109">LogAlways</span></span>|  
|<span data-ttu-id="f614f-110">通道</span><span class="sxs-lookup"><span data-stu-id="f614f-110">Channel</span></span>|<span data-ttu-id="f614f-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="f614f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f614f-112">描述</span><span class="sxs-lookup"><span data-stu-id="f614f-112">Description</span></span>  
 <span data-ttu-id="f614f-113">此事件在发生传输事件时发出。</span><span class="sxs-lookup"><span data-stu-id="f614f-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f614f-114">消息</span><span class="sxs-lookup"><span data-stu-id="f614f-114">Message</span></span>  
 <span data-ttu-id="f614f-115">发出了传输事件。</span><span class="sxs-lookup"><span data-stu-id="f614f-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f614f-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="f614f-116">Details</span></span>  
  
|<span data-ttu-id="f614f-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f614f-117">Data Item Name</span></span>|<span data-ttu-id="f614f-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f614f-118">Data Item Type</span></span>|<span data-ttu-id="f614f-119">描述</span><span class="sxs-lookup"><span data-stu-id="f614f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f614f-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="f614f-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="f614f-121">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="f614f-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f614f-122">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="f614f-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f614f-123">示例:默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="f614f-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f614f-124">应用程序域</span><span class="sxs-lookup"><span data-stu-id="f614f-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f614f-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f614f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
