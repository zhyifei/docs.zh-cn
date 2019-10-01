---
title: <authenticationModules> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 4fe44deba951e5302518ed855589ad1b0ca75343
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699537"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="f40f7-102">\<authenticationModules > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="f40f7-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="f40f7-103">指定用于对网络请求进行身份验证的模块。</span><span class="sxs-lookup"><span data-stu-id="f40f7-103">Specifies modules used to authenticate network requests.</span></span>  
  
[<span data-ttu-id="f40f7-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f40f7-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f40f7-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f40f7-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="f40f7-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t **\<authenticationModules >**</span><span class="sxs-lookup"><span data-stu-id="f40f7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f40f7-107">语法</span><span class="sxs-lookup"><span data-stu-id="f40f7-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f40f7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f40f7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f40f7-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f40f7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f40f7-110">特性</span><span class="sxs-lookup"><span data-stu-id="f40f7-110">Attributes</span></span>  
 <span data-ttu-id="f40f7-111">无。</span><span class="sxs-lookup"><span data-stu-id="f40f7-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f40f7-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f40f7-112">Child Elements</span></span>  
  
|<span data-ttu-id="f40f7-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="f40f7-113">**Element**</span></span>|<span data-ttu-id="f40f7-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="f40f7-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f40f7-115">add</span><span class="sxs-lookup"><span data-stu-id="f40f7-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="f40f7-116">向应用程序添加身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="f40f7-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="f40f7-117">clear</span><span class="sxs-lookup"><span data-stu-id="f40f7-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="f40f7-118">清除应用程序中的所有身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="f40f7-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="f40f7-119">remove</span><span class="sxs-lookup"><span data-stu-id="f40f7-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="f40f7-120">从应用程序中移除身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="f40f7-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f40f7-121">父元素</span><span class="sxs-lookup"><span data-stu-id="f40f7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f40f7-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="f40f7-122">**Element**</span></span>|<span data-ttu-id="f40f7-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="f40f7-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f40f7-124">system.net</span><span class="sxs-lookup"><span data-stu-id="f40f7-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="f40f7-125">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="f40f7-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f40f7-126">备注</span><span class="sxs-lookup"><span data-stu-id="f40f7-126">Remarks</span></span>  
 <span data-ttu-id="f40f7-127">@No__t-0 元素指定对服务器执行身份验证过程的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="f40f7-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="f40f7-128">身份验证模块必须实现 <xref:System.Net.IAuthenticationModule> 接口。</span><span class="sxs-lookup"><span data-stu-id="f40f7-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f40f7-129">配置文件</span><span class="sxs-lookup"><span data-stu-id="f40f7-129">Configuration Files</span></span>  
 <span data-ttu-id="f40f7-130">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="f40f7-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f40f7-131">示例</span><span class="sxs-lookup"><span data-stu-id="f40f7-131">Example</span></span>  
 <span data-ttu-id="f40f7-132">下面的示例启用了身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="f40f7-132">The following example enables an authentication module.</span></span> <span data-ttu-id="f40f7-133">应将版本和 PublicKeyToken 的值替换为指定模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="f40f7-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f40f7-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="f40f7-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="f40f7-135">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="f40f7-135">Network Settings Schema</span></span>](index.md)
