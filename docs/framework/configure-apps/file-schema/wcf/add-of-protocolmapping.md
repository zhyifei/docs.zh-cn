---
title: <add> 的 <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: df69b5f8a79489b722c1074f118b9c6f6e8e363d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926672"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="021ad-102">\<添加 protocolMapping > \<的 ></span><span class="sxs-lookup"><span data-stu-id="021ad-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="021ad-103">表示传输协议方案 (例如, http、net.tcp、net.pipe 等) 与 Windows Communication Foundation (WCF) 绑定之间的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="021ad-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="021ad-104">在运行时创建默认终结点时, WCF 会查看已配置的映射, 并决定要将哪个绑定用于特定的地址。</span><span class="sxs-lookup"><span data-stu-id="021ad-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="021ad-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="021ad-105">\<system.serviceModel></span></span>  
<span data-ttu-id="021ad-106">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="021ad-106">\<protocolMapping></span></span>  
<span data-ttu-id="021ad-107">\<add></span><span class="sxs-lookup"><span data-stu-id="021ad-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="021ad-108">语法</span><span class="sxs-lookup"><span data-stu-id="021ad-108">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="021ad-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="021ad-109">Attributes and Elements</span></span>  
 <span data-ttu-id="021ad-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="021ad-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="021ad-111">特性</span><span class="sxs-lookup"><span data-stu-id="021ad-111">Attributes</span></span>  
  
|<span data-ttu-id="021ad-112">元素</span><span class="sxs-lookup"><span data-stu-id="021ad-112">Element</span></span>|<span data-ttu-id="021ad-113">描述</span><span class="sxs-lookup"><span data-stu-id="021ad-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="021ad-114">绑定</span><span class="sxs-lookup"><span data-stu-id="021ad-114">binding</span></span>|<span data-ttu-id="021ad-115">一个字符串，指定在创建默认终结点时要用于终结点的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="021ad-115">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="021ad-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="021ad-116">bindingConfiguration</span></span>|<span data-ttu-id="021ad-117">一个字符串，指定要引用的绑定配置节的名称。</span><span class="sxs-lookup"><span data-stu-id="021ad-117">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="021ad-118">scheme</span><span class="sxs-lookup"><span data-stu-id="021ad-118">scheme</span></span>|<span data-ttu-id="021ad-119">要用于默认终结点的传输协议方案。</span><span class="sxs-lookup"><span data-stu-id="021ad-119">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="021ad-120">子元素</span><span class="sxs-lookup"><span data-stu-id="021ad-120">Child Elements</span></span>  
 <span data-ttu-id="021ad-121">无。</span><span class="sxs-lookup"><span data-stu-id="021ad-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="021ad-122">父元素</span><span class="sxs-lookup"><span data-stu-id="021ad-122">Parent Elements</span></span>  
  
|<span data-ttu-id="021ad-123">元素</span><span class="sxs-lookup"><span data-stu-id="021ad-123">Element</span></span>|<span data-ttu-id="021ad-124">描述</span><span class="sxs-lookup"><span data-stu-id="021ad-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="021ad-125">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="021ad-125">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="021ad-126">表示用于定义传输协议方案 (例如, http、net.tcp、net.pipe 等) 与 Windows Communication Foundation (WCF) 绑定之间的默认协议映射的配置节。</span><span class="sxs-lookup"><span data-stu-id="021ad-126">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="021ad-127">示例</span><span class="sxs-lookup"><span data-stu-id="021ad-127">Example</span></span>  
 <span data-ttu-id="021ad-128">下面的配置示例演示 machine.config 文件中的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="021ad-128">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="021ad-129">您可以通过修改 machine.config 文件在计算机级别重写此默认映射。</span><span class="sxs-lookup"><span data-stu-id="021ad-129">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="021ad-130">或者，如果您只希望在应用程序范围内重写此映射，则可以在应用程序配置文件中重写此节，并为单独的协议方案更改映射。</span><span class="sxs-lookup"><span data-stu-id="021ad-130">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="021ad-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="021ad-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
