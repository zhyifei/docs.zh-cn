---
title: "激活的 &lt;diagnostics&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 29f2e56dd18da9dc3ce3206f5c3c80f4a47a7ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="db90c-102">激活的 &lt;diagnostics&gt;</span><span class="sxs-lookup"><span data-stu-id="db90c-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="db90c-103">配置 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 侦听器的诊断功能。</span><span class="sxs-lookup"><span data-stu-id="db90c-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="db90c-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="db90c-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="db90c-105">\<诊断 ></span><span class="sxs-lookup"><span data-stu-id="db90c-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db90c-106">语法</span><span class="sxs-lookup"><span data-stu-id="db90c-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="db90c-107">类型</span><span class="sxs-lookup"><span data-stu-id="db90c-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db90c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="db90c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="db90c-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="db90c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db90c-110">特性</span><span class="sxs-lookup"><span data-stu-id="db90c-110">Attributes</span></span>  
  
|<span data-ttu-id="db90c-111">特性</span><span class="sxs-lookup"><span data-stu-id="db90c-111">Attribute</span></span>|<span data-ttu-id="db90c-112">描述</span><span class="sxs-lookup"><span data-stu-id="db90c-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="db90c-113">一个布尔值，指示是否启用用于诊断目的的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="db90c-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db90c-114">子元素</span><span class="sxs-lookup"><span data-stu-id="db90c-114">Child Elements</span></span>  
 <span data-ttu-id="db90c-115">无。</span><span class="sxs-lookup"><span data-stu-id="db90c-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db90c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="db90c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="db90c-117">元素</span><span class="sxs-lookup"><span data-stu-id="db90c-117">Element</span></span>|<span data-ttu-id="db90c-118">描述</span><span class="sxs-lookup"><span data-stu-id="db90c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db90c-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="db90c-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="db90c-120">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="db90c-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db90c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db90c-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
