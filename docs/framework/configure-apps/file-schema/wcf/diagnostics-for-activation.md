---
title: 激活的 &lt;diagnostics&gt;
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 4e5332eed87ded51cebcd614f45cbc8e80e570fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="e7abd-102">激活的 &lt;diagnostics&gt;</span><span class="sxs-lookup"><span data-stu-id="e7abd-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="e7abd-103">配置 Windows Communication Foundation (WCF) 侦听器的诊断功能。</span><span class="sxs-lookup"><span data-stu-id="e7abd-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="e7abd-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="e7abd-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="e7abd-105">\<诊断 ></span><span class="sxs-lookup"><span data-stu-id="e7abd-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7abd-106">语法</span><span class="sxs-lookup"><span data-stu-id="e7abd-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="e7abd-107">类型</span><span class="sxs-lookup"><span data-stu-id="e7abd-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7abd-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e7abd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e7abd-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e7abd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7abd-110">特性</span><span class="sxs-lookup"><span data-stu-id="e7abd-110">Attributes</span></span>  
  
|<span data-ttu-id="e7abd-111">特性</span><span class="sxs-lookup"><span data-stu-id="e7abd-111">Attribute</span></span>|<span data-ttu-id="e7abd-112">描述</span><span class="sxs-lookup"><span data-stu-id="e7abd-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="e7abd-113">一个布尔值，指示是否启用用于诊断目的的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="e7abd-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7abd-114">子元素</span><span class="sxs-lookup"><span data-stu-id="e7abd-114">Child Elements</span></span>  
 <span data-ttu-id="e7abd-115">无。</span><span class="sxs-lookup"><span data-stu-id="e7abd-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7abd-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e7abd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e7abd-117">元素</span><span class="sxs-lookup"><span data-stu-id="e7abd-117">Element</span></span>|<span data-ttu-id="e7abd-118">描述</span><span class="sxs-lookup"><span data-stu-id="e7abd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7abd-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="e7abd-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="e7abd-120">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="e7abd-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7abd-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7abd-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
