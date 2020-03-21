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
ms.openlocfilehash: ed28ae4a52085cbfa781b4baf2ee1eafbeff6eb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154824"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="d1750-102">\<模块>元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="d1750-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="d1750-103">向应用程序添加新的代理模块。</span><span class="sxs-lookup"><span data-stu-id="d1750-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="d1750-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d1750-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d1750-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d1750-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="d1750-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<默认代理>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d1750-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="d1750-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<模块>**</span><span class="sxs-lookup"><span data-stu-id="d1750-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d1750-108">语法</span><span class="sxs-lookup"><span data-stu-id="d1750-108">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1750-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d1750-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d1750-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d1750-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1750-111">属性</span><span class="sxs-lookup"><span data-stu-id="d1750-111">Attributes</span></span>  
  
|<span data-ttu-id="d1750-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="d1750-112">**Attribute**</span></span>|<span data-ttu-id="d1750-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1750-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="d1750-114">完全限定的类型名称（由<xref:System.Type.FullName%2A>属性指示）和程序集名称（由<xref:System.Reflection.Assembly.FullName%2A>属性表示），由逗号分隔，实现代理。</span><span class="sxs-lookup"><span data-stu-id="d1750-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1750-115">子元素</span><span class="sxs-lookup"><span data-stu-id="d1750-115">Child Elements</span></span>  
 <span data-ttu-id="d1750-116">无。</span><span class="sxs-lookup"><span data-stu-id="d1750-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1750-117">父元素</span><span class="sxs-lookup"><span data-stu-id="d1750-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d1750-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="d1750-118">**Element**</span></span>|<span data-ttu-id="d1750-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1750-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d1750-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="d1750-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="d1750-121">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="d1750-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1750-122">备注</span><span class="sxs-lookup"><span data-stu-id="d1750-122">Remarks</span></span>  
 <span data-ttu-id="d1750-123">元素`module`注册实现接口的<xref:System.Net.IWebProxy>代理类。</span><span class="sxs-lookup"><span data-stu-id="d1750-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="d1750-124">在注册代理类之后，该 `module` 可用于通过所支持的代理请求信息。</span><span class="sxs-lookup"><span data-stu-id="d1750-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="d1750-125">`type`属性的值应是模块的类名及其相应的动态链接库 （DLL） 的名称。</span><span class="sxs-lookup"><span data-stu-id="d1750-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d1750-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="d1750-126">Configuration Files</span></span>  
 <span data-ttu-id="d1750-127">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="d1750-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1750-128">示例</span><span class="sxs-lookup"><span data-stu-id="d1750-128">Example</span></span>  
 <span data-ttu-id="d1750-129">下面的示例注册自定义代理类。</span><span class="sxs-lookup"><span data-stu-id="d1750-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d1750-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1750-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="d1750-131">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="d1750-131">Network Settings Schema</span></span>](index.md)
