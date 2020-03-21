---
title: authenticationModules 的 <add> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: 4181a045079bdb455a63ebda722dd6b0daf33c4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155110"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="0a045-102">\<添加>元素以进行身份验证模块（网络设置）</span><span class="sxs-lookup"><span data-stu-id="0a045-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="0a045-103">向应用程序添加身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="0a045-103">Adds an authentication module to the application.</span></span>  

<span data-ttu-id="0a045-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0a045-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0a045-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0a045-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="0a045-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份验证模块>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0a045-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="0a045-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<添加>**</span><span class="sxs-lookup"><span data-stu-id="0a045-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0a045-108">语法</span><span class="sxs-lookup"><span data-stu-id="0a045-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a045-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0a045-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0a045-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0a045-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a045-111">属性</span><span class="sxs-lookup"><span data-stu-id="0a045-111">Attributes</span></span>  
  
|<span data-ttu-id="0a045-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="0a045-112">**Attribute**</span></span>|<span data-ttu-id="0a045-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="0a045-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="0a045-114">完全限定的类型名称（由<xref:System.Type.FullName%2A>属性指示）和程序集名称（由<xref:System.Reflection.Assembly.FullName%2A>属性指示），用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="0a045-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a045-115">子元素</span><span class="sxs-lookup"><span data-stu-id="0a045-115">Child Elements</span></span>  
 <span data-ttu-id="0a045-116">无。</span><span class="sxs-lookup"><span data-stu-id="0a045-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a045-117">父元素</span><span class="sxs-lookup"><span data-stu-id="0a045-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0a045-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="0a045-118">**Element**</span></span>|<span data-ttu-id="0a045-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="0a045-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0a045-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="0a045-120">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="0a045-121">指定用于验证网络请求的模块。</span><span class="sxs-lookup"><span data-stu-id="0a045-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a045-122">备注</span><span class="sxs-lookup"><span data-stu-id="0a045-122">Remarks</span></span>  
 <span data-ttu-id="0a045-123">`add` 元素会在已注册的身份验证模块列表末尾添加一个身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="0a045-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="0a045-124">身份验证模块按添加到列表的顺序调用。</span><span class="sxs-lookup"><span data-stu-id="0a045-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="0a045-125">`type`属性的值应是有效的类型名称和相应的程序集名称，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="0a045-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0a045-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="0a045-126">Configuration Files</span></span>  
 <span data-ttu-id="0a045-127">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="0a045-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a045-128">示例</span><span class="sxs-lookup"><span data-stu-id="0a045-128">Example</span></span>  
 <span data-ttu-id="0a045-129">以下示例启用默认身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="0a045-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="0a045-130">应将版本和 PublicKeyToken 的值替换为指定模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="0a045-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a045-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a045-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="0a045-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="0a045-132">Network Settings Schema</span></span>](index.md)
