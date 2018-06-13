---
title: '&lt;protocolMapping&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 4552cc030a88841d4fb80c097ba089d1c6a0066c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349005"
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a><span data-ttu-id="dcd68-102">&lt;protocolMapping&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="dcd68-102">&lt;add&gt; of &lt;protocolMapping&gt;</span></span>
<span data-ttu-id="dcd68-103">表示传输协议方案 （例如，http、 net.tcp、 net.pipe 等） 和 Windows Communication Foundation (WCF) 绑定之间的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="dcd68-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="dcd68-104">当在运行时创建默认终结点，WCF 查看配置的映射，并确定要用于特定的绑定基于的地址。</span><span class="sxs-lookup"><span data-stu-id="dcd68-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="dcd68-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dcd68-105">\<system.serviceModel></span></span>  
<span data-ttu-id="dcd68-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="dcd68-106">\<protocolMapping></span></span>  
<span data-ttu-id="dcd68-107">\<add></span><span class="sxs-lookup"><span data-stu-id="dcd68-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcd68-108">语法</span><span class="sxs-lookup"><span data-stu-id="dcd68-108">Syntax</span></span>  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dcd68-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dcd68-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dcd68-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dcd68-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcd68-111">特性</span><span class="sxs-lookup"><span data-stu-id="dcd68-111">Attributes</span></span>  
  
|<span data-ttu-id="dcd68-112">元素</span><span class="sxs-lookup"><span data-stu-id="dcd68-112">Element</span></span>|<span data-ttu-id="dcd68-113">描述</span><span class="sxs-lookup"><span data-stu-id="dcd68-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dcd68-114">绑定</span><span class="sxs-lookup"><span data-stu-id="dcd68-114">binding</span></span>|<span data-ttu-id="dcd68-115">一个字符串，指定在创建默认终结点时要用于终结点的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="dcd68-115">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="dcd68-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="dcd68-116">bindingConfiguration</span></span>|<span data-ttu-id="dcd68-117">一个字符串，指定要引用的绑定配置节的名称。</span><span class="sxs-lookup"><span data-stu-id="dcd68-117">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="dcd68-118">scheme</span><span class="sxs-lookup"><span data-stu-id="dcd68-118">scheme</span></span>|<span data-ttu-id="dcd68-119">要用于默认终结点的传输协议方案。</span><span class="sxs-lookup"><span data-stu-id="dcd68-119">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dcd68-120">子元素</span><span class="sxs-lookup"><span data-stu-id="dcd68-120">Child Elements</span></span>  
 <span data-ttu-id="dcd68-121">无。</span><span class="sxs-lookup"><span data-stu-id="dcd68-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dcd68-122">父元素</span><span class="sxs-lookup"><span data-stu-id="dcd68-122">Parent Elements</span></span>  
  
|<span data-ttu-id="dcd68-123">元素</span><span class="sxs-lookup"><span data-stu-id="dcd68-123">Element</span></span>|<span data-ttu-id="dcd68-124">描述</span><span class="sxs-lookup"><span data-stu-id="dcd68-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcd68-125">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="dcd68-125">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="dcd68-126">表示一个配置节，用于定义传输协议方案 （例如，http、 net.tcp、 net.pipe 等） 和 Windows Communication Foundation (WCF) 的绑定之间的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="dcd68-126">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dcd68-127">示例</span><span class="sxs-lookup"><span data-stu-id="dcd68-127">Example</span></span>  
 <span data-ttu-id="dcd68-128">下面的配置示例演示 machine.config 文件中的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="dcd68-128">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="dcd68-129">您可以通过修改 machine.config 文件在计算机级别重写此默认映射。</span><span class="sxs-lookup"><span data-stu-id="dcd68-129">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="dcd68-130">或者，如果您只希望在应用程序范围内重写此映射，则可以在应用程序配置文件中重写此节，并为单独的协议方案更改映射。</span><span class="sxs-lookup"><span data-stu-id="dcd68-130">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcd68-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcd68-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
