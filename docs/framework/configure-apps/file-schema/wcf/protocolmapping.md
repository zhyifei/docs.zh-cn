---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400023"
---
# <a name="protocolmapping"></a><span data-ttu-id="1a885-101">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="1a885-101">\<protocolMapping></span></span>
<span data-ttu-id="1a885-102">表示用于定义传输协议方案（例如，http、net.tcp、net.pipe 等）和 WCF 绑定之间的一组默认协议映射的配置节。</span><span class="sxs-lookup"><span data-stu-id="1a885-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="1a885-103">在运行时创建默认终结点时，Windows Communication Foundation （WCF）将查看已配置的映射，并决定要将哪个绑定用于特定的地址。</span><span class="sxs-lookup"><span data-stu-id="1a885-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="1a885-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a885-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1a885-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1a885-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1a885-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<protocolMapping >**</span><span class="sxs-lookup"><span data-stu-id="1a885-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a885-107">语法</span><span class="sxs-lookup"><span data-stu-id="1a885-107">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a885-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1a885-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1a885-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1a885-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a885-110">特性</span><span class="sxs-lookup"><span data-stu-id="1a885-110">Attributes</span></span>  
 <span data-ttu-id="1a885-111">无。</span><span class="sxs-lookup"><span data-stu-id="1a885-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1a885-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1a885-112">Child Elements</span></span>  
  
|<span data-ttu-id="1a885-113">元素</span><span class="sxs-lookup"><span data-stu-id="1a885-113">Element</span></span>|<span data-ttu-id="1a885-114">描述</span><span class="sxs-lookup"><span data-stu-id="1a885-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a885-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="1a885-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="1a885-116">包含传输协议方案（例如，http、net.tcp、net.pipe 等）与 WCF 绑定之间的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="1a885-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a885-117">父元素</span><span class="sxs-lookup"><span data-stu-id="1a885-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1a885-118">元素</span><span class="sxs-lookup"><span data-stu-id="1a885-118">Element</span></span>|<span data-ttu-id="1a885-119">描述</span><span class="sxs-lookup"><span data-stu-id="1a885-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a885-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1a885-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="1a885-121">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="1a885-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1a885-122">示例</span><span class="sxs-lookup"><span data-stu-id="1a885-122">Example</span></span>  
 <span data-ttu-id="1a885-123">下面的配置示例演示 machine.config 文件中的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="1a885-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="1a885-124">您可以通过修改 machine.config 文件在计算机级别重写此默认映射。</span><span class="sxs-lookup"><span data-stu-id="1a885-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="1a885-125">或者，如果您只希望在应用程序范围内重写此映射，则可以在应用程序配置文件中重写此节，并为单独的协议方案更改映射。</span><span class="sxs-lookup"><span data-stu-id="1a885-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="1a885-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a885-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
