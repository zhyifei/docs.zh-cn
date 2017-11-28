---
title: '&lt;protocolMapping&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 769ca7b96c3671fdd1b154c99516778f7cbd542e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltprotocolmappinggt"></a><span data-ttu-id="27c40-102">&lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="27c40-102">&lt;protocolMapping&gt;</span></span>
<span data-ttu-id="27c40-103">表示一个配置节，用于定义一组的传输协议方案 （例如，http、 net.tcp、 net.pipe 等） 和 WCF 绑定之间的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="27c40-103">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="27c40-104">当在运行时创建默认终结点时，[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 将查看已配置的映射，并确定要用于基于特定内容的地址的绑定。</span><span class="sxs-lookup"><span data-stu-id="27c40-104">When creating default endpoints at runtime, [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="27c40-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="27c40-105">\<system.serviceModel></span></span>  
<span data-ttu-id="27c40-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="27c40-106">\<protocolMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c40-107">语法</span><span class="sxs-lookup"><span data-stu-id="27c40-107">Syntax</span></span>  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="27c40-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="27c40-108">Attributes and Elements</span></span>  
 <span data-ttu-id="27c40-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="27c40-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27c40-110">特性</span><span class="sxs-lookup"><span data-stu-id="27c40-110">Attributes</span></span>  
 <span data-ttu-id="27c40-111">无。</span><span class="sxs-lookup"><span data-stu-id="27c40-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="27c40-112">子元素</span><span class="sxs-lookup"><span data-stu-id="27c40-112">Child Elements</span></span>  
  
|<span data-ttu-id="27c40-113">元素</span><span class="sxs-lookup"><span data-stu-id="27c40-113">Element</span></span>|<span data-ttu-id="27c40-114">描述</span><span class="sxs-lookup"><span data-stu-id="27c40-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27c40-115">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="27c40-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="27c40-116">包含传输协议方案 （例如，http、 net.tcp、 net.pipe 等） 和 WCF 绑定之间的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="27c40-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27c40-117">父元素</span><span class="sxs-lookup"><span data-stu-id="27c40-117">Parent Elements</span></span>  
  
|<span data-ttu-id="27c40-118">元素</span><span class="sxs-lookup"><span data-stu-id="27c40-118">Element</span></span>|<span data-ttu-id="27c40-119">描述</span><span class="sxs-lookup"><span data-stu-id="27c40-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27c40-120">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="27c40-120">system.ServiceModel</span></span>|<span data-ttu-id="27c40-121">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="27c40-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27c40-122">示例</span><span class="sxs-lookup"><span data-stu-id="27c40-122">Example</span></span>  
 <span data-ttu-id="27c40-123">下面的配置示例演示 machine.config 文件中的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="27c40-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="27c40-124">您可以通过修改 machine.config 文件在计算机级别重写此默认映射。</span><span class="sxs-lookup"><span data-stu-id="27c40-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="27c40-125">或者，如果您只希望在应用程序范围内重写此映射，则可以在应用程序配置文件中重写此节，并为单独的协议方案更改映射。</span><span class="sxs-lookup"><span data-stu-id="27c40-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27c40-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27c40-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
