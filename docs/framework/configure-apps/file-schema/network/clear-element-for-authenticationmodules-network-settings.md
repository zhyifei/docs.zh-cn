---
title: authenticationModules 的 <clear> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: 052f7eef30500d37389585956728250a46b718a3
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698403"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="d795e-102">用于 authenticationModules 的 0clear > 元素（网络设置） @no__t</span><span class="sxs-lookup"><span data-stu-id="d795e-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="d795e-103">清除应用程序中的所有身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="d795e-103">Clears all authentication modules from the application.</span></span>  
  
[<span data-ttu-id="d795e-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d795e-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d795e-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d795e-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="d795e-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d795e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="d795e-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="d795e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d795e-108">语法</span><span class="sxs-lookup"><span data-stu-id="d795e-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d795e-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d795e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d795e-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d795e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d795e-111">特性</span><span class="sxs-lookup"><span data-stu-id="d795e-111">Attributes</span></span>  
 <span data-ttu-id="d795e-112">无。</span><span class="sxs-lookup"><span data-stu-id="d795e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d795e-113">子元素</span><span class="sxs-lookup"><span data-stu-id="d795e-113">Child Elements</span></span>  
 <span data-ttu-id="d795e-114">无。</span><span class="sxs-lookup"><span data-stu-id="d795e-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d795e-115">父元素</span><span class="sxs-lookup"><span data-stu-id="d795e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d795e-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="d795e-116">**Element**</span></span>|<span data-ttu-id="d795e-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="d795e-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d795e-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="d795e-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="d795e-119">指定用于对网络请求进行身份验证的模块。</span><span class="sxs-lookup"><span data-stu-id="d795e-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d795e-120">备注</span><span class="sxs-lookup"><span data-stu-id="d795e-120">Remarks</span></span>  
 <span data-ttu-id="d795e-121">@No__t-0 元素删除先前在配置文件中或在配置层次结构中的更高级别定义的所有身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="d795e-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d795e-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="d795e-122">Configuration Files</span></span>  
 <span data-ttu-id="d795e-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="d795e-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d795e-124">示例</span><span class="sxs-lookup"><span data-stu-id="d795e-124">Example</span></span>  
 <span data-ttu-id="d795e-125">下面的示例删除所有配置的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="d795e-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d795e-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d795e-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="d795e-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="d795e-127">Network Settings Schema</span></span>](index.md)
