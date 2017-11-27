---
title: "&lt;删除&gt;authenticationModules （网络设置） 的元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: eb8490241d4ec8a34a76aa6087c1f4d27d5cebb4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="1ac5b-102">&lt;删除&gt;authenticationModules （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="1ac5b-102">&lt;remove&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="1ac5b-103">从应用程序中移除一个身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="1ac5b-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="1ac5b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1ac5b-104">\<configuration></span></span>  
<span data-ttu-id="1ac5b-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="1ac5b-105">\<system.net></span></span>  
<span data-ttu-id="1ac5b-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="1ac5b-106">\<authenticationModules></span></span>  
<span data-ttu-id="1ac5b-107">\<删除 ></span><span class="sxs-lookup"><span data-stu-id="1ac5b-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ac5b-108">语法</span><span class="sxs-lookup"><span data-stu-id="1ac5b-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ac5b-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1ac5b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1ac5b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1ac5b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ac5b-111">特性</span><span class="sxs-lookup"><span data-stu-id="1ac5b-111">Attributes</span></span>  
  
|<span data-ttu-id="1ac5b-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="1ac5b-112">**Attribute**</span></span>|<span data-ttu-id="1ac5b-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="1ac5b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="1ac5b-114">**type**</span><span class="sxs-lookup"><span data-stu-id="1ac5b-114">**type**</span></span>|<span data-ttu-id="1ac5b-115">要删除的身份验证模块的名称。</span><span class="sxs-lookup"><span data-stu-id="1ac5b-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ac5b-116">子元素</span><span class="sxs-lookup"><span data-stu-id="1ac5b-116">Child Elements</span></span>  
 <span data-ttu-id="1ac5b-117">无。</span><span class="sxs-lookup"><span data-stu-id="1ac5b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ac5b-118">父元素</span><span class="sxs-lookup"><span data-stu-id="1ac5b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1ac5b-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="1ac5b-119">**Element**</span></span>|<span data-ttu-id="1ac5b-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="1ac5b-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1ac5b-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="1ac5b-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="1ac5b-122">指定用来验证网络请求的模块。</span><span class="sxs-lookup"><span data-stu-id="1ac5b-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ac5b-123">备注</span><span class="sxs-lookup"><span data-stu-id="1ac5b-123">Remarks</span></span>  
 <span data-ttu-id="1ac5b-124">`remove`元素中删除配置文件中或在配置层次结构中较高级别前面定义的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="1ac5b-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="1ac5b-125">值`type`属性应为有效的类名称。</span><span class="sxs-lookup"><span data-stu-id="1ac5b-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1ac5b-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="1ac5b-126">Configuration Files</span></span>  
 <span data-ttu-id="1ac5b-127">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="1ac5b-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ac5b-128">示例</span><span class="sxs-lookup"><span data-stu-id="1ac5b-128">Example</span></span>  
 <span data-ttu-id="1ac5b-129">下面的示例删除一个身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="1ac5b-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ac5b-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ac5b-130">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="1ac5b-131">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="1ac5b-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
