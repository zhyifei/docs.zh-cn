---
title: <diagnostics> 用于激活
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203803"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="12986-102">\<诊断 > 激活</span><span class="sxs-lookup"><span data-stu-id="12986-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="12986-103">配置 Windows Communication Foundation (WCF) 侦听器的诊断功能。</span><span class="sxs-lookup"><span data-stu-id="12986-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="12986-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="12986-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="12986-105">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="12986-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12986-106">语法</span><span class="sxs-lookup"><span data-stu-id="12986-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="12986-107">类型</span><span class="sxs-lookup"><span data-stu-id="12986-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12986-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="12986-108">Attributes and Elements</span></span>  
 <span data-ttu-id="12986-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="12986-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12986-110">特性</span><span class="sxs-lookup"><span data-stu-id="12986-110">Attributes</span></span>  
  
|<span data-ttu-id="12986-111">特性</span><span class="sxs-lookup"><span data-stu-id="12986-111">Attribute</span></span>|<span data-ttu-id="12986-112">描述</span><span class="sxs-lookup"><span data-stu-id="12986-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="12986-113">一个布尔值，指示是否启用用于诊断目的的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="12986-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12986-114">子元素</span><span class="sxs-lookup"><span data-stu-id="12986-114">Child Elements</span></span>  
 <span data-ttu-id="12986-115">无。</span><span class="sxs-lookup"><span data-stu-id="12986-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12986-116">父元素</span><span class="sxs-lookup"><span data-stu-id="12986-116">Parent Elements</span></span>  
  
|<span data-ttu-id="12986-117">元素</span><span class="sxs-lookup"><span data-stu-id="12986-117">Element</span></span>|<span data-ttu-id="12986-118">描述</span><span class="sxs-lookup"><span data-stu-id="12986-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12986-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="12986-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="12986-120">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="12986-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12986-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="12986-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
