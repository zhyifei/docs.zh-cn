---
title: '&lt;添加&gt;authenticationModules （网络设置） 的元素'
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 471e36bb584164b851e7a06c0e682ba9872f7910
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742895"
---
# <a name="ltaddgt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="4c287-102">&lt;添加&gt;authenticationModules （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="4c287-102">&lt;add&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="4c287-103">向应用程序添加身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="4c287-103">Adds an authentication module to the application.</span></span>  
  
 <span data-ttu-id="4c287-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4c287-104">\<configuration></span></span>  
<span data-ttu-id="4c287-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4c287-105">\<system.net></span></span>  
<span data-ttu-id="4c287-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="4c287-106">\<authenticationModules></span></span>  
<span data-ttu-id="4c287-107">\<add></span><span class="sxs-lookup"><span data-stu-id="4c287-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c287-108">语法</span><span class="sxs-lookup"><span data-stu-id="4c287-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c287-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4c287-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4c287-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4c287-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c287-111">特性</span><span class="sxs-lookup"><span data-stu-id="4c287-111">Attributes</span></span>  
  
|<span data-ttu-id="4c287-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="4c287-112">**Attribute**</span></span>|<span data-ttu-id="4c287-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="4c287-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="4c287-114">完全限定的类型名称 (由<xref:System.Type.FullName%2A>属性) 和程序集名称 (由<xref:System.Reflection.Assembly.FullName%2A>属性)，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="4c287-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c287-115">子元素</span><span class="sxs-lookup"><span data-stu-id="4c287-115">Child Elements</span></span>  
 <span data-ttu-id="4c287-116">无。</span><span class="sxs-lookup"><span data-stu-id="4c287-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c287-117">父元素</span><span class="sxs-lookup"><span data-stu-id="4c287-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4c287-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="4c287-118">**Element**</span></span>|<span data-ttu-id="4c287-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4c287-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4c287-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="4c287-120">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="4c287-121">指定用来验证网络请求的模块。</span><span class="sxs-lookup"><span data-stu-id="4c287-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c287-122">备注</span><span class="sxs-lookup"><span data-stu-id="4c287-122">Remarks</span></span>  
 <span data-ttu-id="4c287-123">`add` 元素会在已注册的身份验证模块列表末尾添加一个身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="4c287-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="4c287-124">添加到列表的顺序在称为身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="4c287-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="4c287-125">值`type`属性应为有效类型名称和相应的程序集名称，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="4c287-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4c287-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="4c287-126">Configuration Files</span></span>  
 <span data-ttu-id="4c287-127">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="4c287-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c287-128">示例</span><span class="sxs-lookup"><span data-stu-id="4c287-128">Example</span></span>  
 <span data-ttu-id="4c287-129">以下示例启用默认身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="4c287-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="4c287-130">版本和 PublicKeyToken 提供值应替换为指定的模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="4c287-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c287-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c287-131">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="4c287-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="4c287-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
