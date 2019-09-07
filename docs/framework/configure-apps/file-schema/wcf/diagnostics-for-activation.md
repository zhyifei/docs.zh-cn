---
title: <diagnostics>用于激活
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400413"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="b5796-102">\<用于激活的诊断 ></span><span class="sxs-lookup"><span data-stu-id="b5796-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="b5796-103">配置 Windows Communication Foundation （WCF）侦听器的诊断功能。</span><span class="sxs-lookup"><span data-stu-id="b5796-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
<span data-ttu-id="b5796-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b5796-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b5796-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="b5796-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="b5796-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<诊断 >**</span><span class="sxs-lookup"><span data-stu-id="b5796-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5796-107">语法</span><span class="sxs-lookup"><span data-stu-id="b5796-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="b5796-108">类型</span><span class="sxs-lookup"><span data-stu-id="b5796-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5796-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b5796-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b5796-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b5796-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5796-111">特性</span><span class="sxs-lookup"><span data-stu-id="b5796-111">Attributes</span></span>  
  
|<span data-ttu-id="b5796-112">特性</span><span class="sxs-lookup"><span data-stu-id="b5796-112">Attribute</span></span>|<span data-ttu-id="b5796-113">描述</span><span class="sxs-lookup"><span data-stu-id="b5796-113">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="b5796-114">一个布尔值，指示是否启用用于诊断目的的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="b5796-114">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5796-115">子元素</span><span class="sxs-lookup"><span data-stu-id="b5796-115">Child Elements</span></span>  
 <span data-ttu-id="b5796-116">无。</span><span class="sxs-lookup"><span data-stu-id="b5796-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b5796-117">父元素</span><span class="sxs-lookup"><span data-stu-id="b5796-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b5796-118">元素</span><span class="sxs-lookup"><span data-stu-id="b5796-118">Element</span></span>|<span data-ttu-id="b5796-119">描述</span><span class="sxs-lookup"><span data-stu-id="b5796-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5796-120">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="b5796-120">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="b5796-121">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="b5796-121">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5796-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5796-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
