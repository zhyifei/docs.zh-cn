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
ms.openlocfilehash: b502cc4a0958f074018d4b0ce6b3fb118b811c2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154967"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="fe5b9-102">\<authenticationModules> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="fe5b9-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="fe5b9-103">指定用于验证网络请求的模块。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-103">Specifies modules used to authenticate network requests.</span></span>  

<span data-ttu-id="fe5b9-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe5b9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fe5b9-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fe5b9-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="fe5b9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<身份验证模块>**</span><span class="sxs-lookup"><span data-stu-id="fe5b9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fe5b9-107">语法</span><span class="sxs-lookup"><span data-stu-id="fe5b9-107">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe5b9-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fe5b9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fe5b9-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe5b9-110">属性</span><span class="sxs-lookup"><span data-stu-id="fe5b9-110">Attributes</span></span>  
 <span data-ttu-id="fe5b9-111">无。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fe5b9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fe5b9-112">Child Elements</span></span>  
  
|<span data-ttu-id="fe5b9-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="fe5b9-113">**Element**</span></span>|<span data-ttu-id="fe5b9-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe5b9-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fe5b9-115">添加</span><span class="sxs-lookup"><span data-stu-id="fe5b9-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="fe5b9-116">向应用程序添加身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="fe5b9-117">清楚</span><span class="sxs-lookup"><span data-stu-id="fe5b9-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="fe5b9-118">清除应用程序中的所有身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="fe5b9-119">删除</span><span class="sxs-lookup"><span data-stu-id="fe5b9-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="fe5b9-120">从应用程序中删除身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe5b9-121">父元素</span><span class="sxs-lookup"><span data-stu-id="fe5b9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fe5b9-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="fe5b9-122">**Element**</span></span>|<span data-ttu-id="fe5b9-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe5b9-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fe5b9-124">system.net</span><span class="sxs-lookup"><span data-stu-id="fe5b9-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="fe5b9-125">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe5b9-126">备注</span><span class="sxs-lookup"><span data-stu-id="fe5b9-126">Remarks</span></span>  
 <span data-ttu-id="fe5b9-127">该`authenticationModule`元素指定使用服务器执行身份验证过程的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="fe5b9-128">身份验证模块必须实现<xref:System.Net.IAuthenticationModule>接口。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fe5b9-129">配置文件</span><span class="sxs-lookup"><span data-stu-id="fe5b9-129">Configuration Files</span></span>  
 <span data-ttu-id="fe5b9-130">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe5b9-131">示例</span><span class="sxs-lookup"><span data-stu-id="fe5b9-131">Example</span></span>  
 <span data-ttu-id="fe5b9-132">以下示例启用身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-132">The following example enables an authentication module.</span></span> <span data-ttu-id="fe5b9-133">应将版本和 PublicKeyToken 的值替换为指定模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="fe5b9-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe5b9-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe5b9-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="fe5b9-135">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="fe5b9-135">Network Settings Schema</span></span>](index.md)
