---
title: <diagnostics> 用于激活
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704253"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="c11f1-102">\<诊断 > 激活</span><span class="sxs-lookup"><span data-stu-id="c11f1-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="c11f1-103">配置 Windows Communication Foundation (WCF) 侦听器的诊断功能。</span><span class="sxs-lookup"><span data-stu-id="c11f1-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="c11f1-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="c11f1-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="c11f1-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="c11f1-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c11f1-106">语法</span><span class="sxs-lookup"><span data-stu-id="c11f1-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="c11f1-107">类型</span><span class="sxs-lookup"><span data-stu-id="c11f1-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c11f1-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c11f1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c11f1-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c11f1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c11f1-110">特性</span><span class="sxs-lookup"><span data-stu-id="c11f1-110">Attributes</span></span>  
  
|<span data-ttu-id="c11f1-111">特性</span><span class="sxs-lookup"><span data-stu-id="c11f1-111">Attribute</span></span>|<span data-ttu-id="c11f1-112">描述</span><span class="sxs-lookup"><span data-stu-id="c11f1-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="c11f1-113">一个布尔值，指示是否启用用于诊断目的的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c11f1-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c11f1-114">子元素</span><span class="sxs-lookup"><span data-stu-id="c11f1-114">Child Elements</span></span>  
 <span data-ttu-id="c11f1-115">无。</span><span class="sxs-lookup"><span data-stu-id="c11f1-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c11f1-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c11f1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c11f1-117">元素</span><span class="sxs-lookup"><span data-stu-id="c11f1-117">Element</span></span>|<span data-ttu-id="c11f1-118">描述</span><span class="sxs-lookup"><span data-stu-id="c11f1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c11f1-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="c11f1-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="c11f1-120">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="c11f1-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c11f1-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c11f1-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
