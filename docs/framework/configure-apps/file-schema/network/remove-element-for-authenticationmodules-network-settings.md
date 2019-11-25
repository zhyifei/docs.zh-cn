---
title: authenticationModules 的 <remove> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 2113b2b81ae347b398b0f25028dc6c361aec8447
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089182"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="8784a-102">\<删除 authenticationModules 的 > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="8784a-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="8784a-103">从应用程序中移除身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="8784a-103">Removes an authentication module from the application.</span></span>  

<span data-ttu-id="8784a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8784a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8784a-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8784a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="8784a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8784a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="8784a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="8784a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8784a-108">语法</span><span class="sxs-lookup"><span data-stu-id="8784a-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8784a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8784a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8784a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8784a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8784a-111">特性</span><span class="sxs-lookup"><span data-stu-id="8784a-111">Attributes</span></span>  
  
|<span data-ttu-id="8784a-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="8784a-112">**Attribute**</span></span>|<span data-ttu-id="8784a-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="8784a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="8784a-114">**type**</span><span class="sxs-lookup"><span data-stu-id="8784a-114">**type**</span></span>|<span data-ttu-id="8784a-115">要删除的身份验证模块的名称。</span><span class="sxs-lookup"><span data-stu-id="8784a-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8784a-116">子元素</span><span class="sxs-lookup"><span data-stu-id="8784a-116">Child Elements</span></span>  
 <span data-ttu-id="8784a-117">无。</span><span class="sxs-lookup"><span data-stu-id="8784a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8784a-118">父元素</span><span class="sxs-lookup"><span data-stu-id="8784a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8784a-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="8784a-119">**Element**</span></span>|<span data-ttu-id="8784a-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="8784a-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8784a-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="8784a-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="8784a-122">指定用于对网络请求进行身份验证的模块。</span><span class="sxs-lookup"><span data-stu-id="8784a-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8784a-123">备注</span><span class="sxs-lookup"><span data-stu-id="8784a-123">Remarks</span></span>  
 <span data-ttu-id="8784a-124">`remove` 元素将删除之前在配置文件中或在配置层次结构中的更高级别定义的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="8784a-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="8784a-125">`type` 特性的值应为有效的类名。</span><span class="sxs-lookup"><span data-stu-id="8784a-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8784a-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="8784a-126">Configuration Files</span></span>  
 <span data-ttu-id="8784a-127">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="8784a-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8784a-128">示例</span><span class="sxs-lookup"><span data-stu-id="8784a-128">Example</span></span>  
 <span data-ttu-id="8784a-129">下面的示例将删除身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="8784a-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8784a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="8784a-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="8784a-131">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="8784a-131">Network Settings Schema</span></span>](index.md)
