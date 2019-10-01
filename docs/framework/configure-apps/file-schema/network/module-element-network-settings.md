---
title: <module> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 15f4d10a70dc3c6abd32869f5b7b0006a799b4bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698035"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="04232-102">\<module > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="04232-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="04232-103">向应用程序添加新的代理模块。</span><span class="sxs-lookup"><span data-stu-id="04232-103">Adds a new proxy module to the application.</span></span>  
  
[<span data-ttu-id="04232-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="04232-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="04232-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="04232-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="04232-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="04232-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="04232-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<module >**</span><span class="sxs-lookup"><span data-stu-id="04232-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04232-108">语法</span><span class="sxs-lookup"><span data-stu-id="04232-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04232-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="04232-109">Attributes and Elements</span></span>  
 <span data-ttu-id="04232-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="04232-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04232-111">特性</span><span class="sxs-lookup"><span data-stu-id="04232-111">Attributes</span></span>  
  
|<span data-ttu-id="04232-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="04232-112">**Attribute**</span></span>|<span data-ttu-id="04232-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="04232-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="04232-114">实现代理的由逗号分隔的完全限定的类型名称（由 <xref:System.Type.FullName%2A> 属性指示）和程序集名称（由 <xref:System.Reflection.Assembly.FullName%2A> 属性指示）。</span><span class="sxs-lookup"><span data-stu-id="04232-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04232-115">子元素</span><span class="sxs-lookup"><span data-stu-id="04232-115">Child Elements</span></span>  
 <span data-ttu-id="04232-116">无。</span><span class="sxs-lookup"><span data-stu-id="04232-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04232-117">父元素</span><span class="sxs-lookup"><span data-stu-id="04232-117">Parent Elements</span></span>  
  
|<span data-ttu-id="04232-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="04232-118">**Element**</span></span>|<span data-ttu-id="04232-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="04232-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="04232-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="04232-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="04232-121">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="04232-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04232-122">备注</span><span class="sxs-lookup"><span data-stu-id="04232-122">Remarks</span></span>  
 <span data-ttu-id="04232-123">@No__t-0 元素注册实现 <xref:System.Net.IWebProxy> 接口的代理类。</span><span class="sxs-lookup"><span data-stu-id="04232-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="04232-124">在注册代理类之后，该 `module` 可用于通过所支持的代理请求信息。</span><span class="sxs-lookup"><span data-stu-id="04232-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="04232-125">@No__t-0 属性的值应为模块的类名称及其对应的动态链接库（DLL）的名称。</span><span class="sxs-lookup"><span data-stu-id="04232-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="04232-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="04232-126">Configuration Files</span></span>  
 <span data-ttu-id="04232-127">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="04232-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04232-128">示例</span><span class="sxs-lookup"><span data-stu-id="04232-128">Example</span></span>  
 <span data-ttu-id="04232-129">下面的示例注册自定义代理类。</span><span class="sxs-lookup"><span data-stu-id="04232-129">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="04232-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="04232-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="04232-131">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="04232-131">Network Settings Schema</span></span>](index.md)
