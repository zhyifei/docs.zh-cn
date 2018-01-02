---
title: "&lt;authenticationModules&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: e7fcaee557884d0c24b7bb15f2424a9e0a413439
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltauthenticationmodulesgt-element-network-settings"></a><span data-ttu-id="83326-102">&lt;authenticationModules&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="83326-102">&lt;authenticationModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="83326-103">指定用来验证网络请求的模块。</span><span class="sxs-lookup"><span data-stu-id="83326-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="83326-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="83326-104">\<configuration></span></span>  
<span data-ttu-id="83326-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="83326-105">\<system.net></span></span>  
<span data-ttu-id="83326-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="83326-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83326-107">语法</span><span class="sxs-lookup"><span data-stu-id="83326-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83326-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="83326-108">Attributes and Elements</span></span>  
 <span data-ttu-id="83326-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="83326-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83326-110">特性</span><span class="sxs-lookup"><span data-stu-id="83326-110">Attributes</span></span>  
 <span data-ttu-id="83326-111">无。</span><span class="sxs-lookup"><span data-stu-id="83326-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="83326-112">子元素</span><span class="sxs-lookup"><span data-stu-id="83326-112">Child Elements</span></span>  
  
|<span data-ttu-id="83326-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="83326-113">**Element**</span></span>|<span data-ttu-id="83326-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="83326-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="83326-115">add</span><span class="sxs-lookup"><span data-stu-id="83326-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="83326-116">向应用程序添加身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="83326-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="83326-117">clear</span><span class="sxs-lookup"><span data-stu-id="83326-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="83326-118">清除从应用程序的所有身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="83326-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="83326-119">remove</span><span class="sxs-lookup"><span data-stu-id="83326-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="83326-120">从应用程序中移除一个身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="83326-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83326-121">父元素</span><span class="sxs-lookup"><span data-stu-id="83326-121">Parent Elements</span></span>  
  
|<span data-ttu-id="83326-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="83326-122">**Element**</span></span>|<span data-ttu-id="83326-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="83326-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="83326-124">system.net</span><span class="sxs-lookup"><span data-stu-id="83326-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="83326-125">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="83326-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83326-126">备注</span><span class="sxs-lookup"><span data-stu-id="83326-126">Remarks</span></span>  
 <span data-ttu-id="83326-127">`authenticationModule`元素指定执行身份验证过程与服务器的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="83326-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="83326-128">身份验证模块必须实现<xref:System.Net.IAuthenticationModule>接口。</span><span class="sxs-lookup"><span data-stu-id="83326-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="83326-129">配置文件</span><span class="sxs-lookup"><span data-stu-id="83326-129">Configuration Files</span></span>  
 <span data-ttu-id="83326-130">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="83326-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83326-131">示例</span><span class="sxs-lookup"><span data-stu-id="83326-131">Example</span></span>  
 <span data-ttu-id="83326-132">以下示例启用一个身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="83326-132">The following example enables an authentication module.</span></span> <span data-ttu-id="83326-133">版本和 PublicKeyToken 提供值应替换为指定的模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="83326-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83326-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="83326-134">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="83326-135">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="83326-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
