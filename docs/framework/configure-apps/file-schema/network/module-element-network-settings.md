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
ms.openlocfilehash: 78f6418160b80096214c6e37268a5a90498d6d4d
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089239"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="62c9c-102">\<module > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="62c9c-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="62c9c-103">向应用程序添加新的代理模块。</span><span class="sxs-lookup"><span data-stu-id="62c9c-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="62c9c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="62c9c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="62c9c-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="62c9c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="62c9c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="62c9c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="62c9c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<模块 >**</span><span class="sxs-lookup"><span data-stu-id="62c9c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="62c9c-108">语法</span><span class="sxs-lookup"><span data-stu-id="62c9c-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62c9c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="62c9c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="62c9c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="62c9c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62c9c-111">特性</span><span class="sxs-lookup"><span data-stu-id="62c9c-111">Attributes</span></span>  
  
|<span data-ttu-id="62c9c-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="62c9c-112">**Attribute**</span></span>|<span data-ttu-id="62c9c-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="62c9c-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="62c9c-114">实现代理的由逗号分隔的完全限定的类型名称（由 <xref:System.Type.FullName%2A> 属性指示）和程序集名称（由 <xref:System.Reflection.Assembly.FullName%2A> 属性指示）。</span><span class="sxs-lookup"><span data-stu-id="62c9c-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62c9c-115">子元素</span><span class="sxs-lookup"><span data-stu-id="62c9c-115">Child Elements</span></span>  
 <span data-ttu-id="62c9c-116">无。</span><span class="sxs-lookup"><span data-stu-id="62c9c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62c9c-117">父元素</span><span class="sxs-lookup"><span data-stu-id="62c9c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="62c9c-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="62c9c-118">**Element**</span></span>|<span data-ttu-id="62c9c-119">**描述**</span><span class="sxs-lookup"><span data-stu-id="62c9c-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="62c9c-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="62c9c-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="62c9c-121">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="62c9c-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62c9c-122">备注</span><span class="sxs-lookup"><span data-stu-id="62c9c-122">Remarks</span></span>  
 <span data-ttu-id="62c9c-123">`module` 元素注册实现 <xref:System.Net.IWebProxy> 接口的代理类。</span><span class="sxs-lookup"><span data-stu-id="62c9c-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="62c9c-124">在注册代理类之后，该 `module` 可用于通过所支持的代理请求信息。</span><span class="sxs-lookup"><span data-stu-id="62c9c-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="62c9c-125">`type` 属性的值应为模块的类名称及其对应的动态链接库（DLL）的名称。</span><span class="sxs-lookup"><span data-stu-id="62c9c-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="62c9c-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="62c9c-126">Configuration Files</span></span>  
 <span data-ttu-id="62c9c-127">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="62c9c-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62c9c-128">示例</span><span class="sxs-lookup"><span data-stu-id="62c9c-128">Example</span></span>  
 <span data-ttu-id="62c9c-129">下面的示例注册自定义代理类。</span><span class="sxs-lookup"><span data-stu-id="62c9c-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62c9c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="62c9c-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="62c9c-131">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="62c9c-131">Network Settings Schema</span></span>](index.md)
