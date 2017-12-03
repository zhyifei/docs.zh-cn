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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1610c77125d2820e3adc06b3c37177058c85abdd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="cb0af-102">激活的 &lt;diagnostics&gt;</span><span class="sxs-lookup"><span data-stu-id="cb0af-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="cb0af-103">配置 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 侦听器的诊断功能。</span><span class="sxs-lookup"><span data-stu-id="cb0af-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="cb0af-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="cb0af-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="cb0af-105">\<诊断 ></span><span class="sxs-lookup"><span data-stu-id="cb0af-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb0af-106">语法</span><span class="sxs-lookup"><span data-stu-id="cb0af-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="cb0af-107">类型</span><span class="sxs-lookup"><span data-stu-id="cb0af-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb0af-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cb0af-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cb0af-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cb0af-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb0af-110">特性</span><span class="sxs-lookup"><span data-stu-id="cb0af-110">Attributes</span></span>  
  
|<span data-ttu-id="cb0af-111">特性</span><span class="sxs-lookup"><span data-stu-id="cb0af-111">Attribute</span></span>|<span data-ttu-id="cb0af-112">描述</span><span class="sxs-lookup"><span data-stu-id="cb0af-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="cb0af-113">一个布尔值，指示是否启用用于诊断目的的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="cb0af-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb0af-114">子元素</span><span class="sxs-lookup"><span data-stu-id="cb0af-114">Child Elements</span></span>  
 <span data-ttu-id="cb0af-115">无。</span><span class="sxs-lookup"><span data-stu-id="cb0af-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb0af-116">父元素</span><span class="sxs-lookup"><span data-stu-id="cb0af-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cb0af-117">元素</span><span class="sxs-lookup"><span data-stu-id="cb0af-117">Element</span></span>|<span data-ttu-id="cb0af-118">描述</span><span class="sxs-lookup"><span data-stu-id="cb0af-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb0af-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="cb0af-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="cb0af-120">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="cb0af-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb0af-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb0af-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
