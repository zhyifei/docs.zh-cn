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
ms.openlocfilehash: 12ac146926103b40073d34f48895b0645c8a8ed2
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659470"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="7989c-102">\<清除 authenticationModules 的 > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="7989c-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="7989c-103">清除应用程序中的所有身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="7989c-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="7989c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7989c-104">\<configuration></span></span>  
<span data-ttu-id="7989c-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="7989c-105">\<system.net></span></span>  
<span data-ttu-id="7989c-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="7989c-106">\<authenticationModules></span></span>  
<span data-ttu-id="7989c-107">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="7989c-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7989c-108">语法</span><span class="sxs-lookup"><span data-stu-id="7989c-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7989c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7989c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7989c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7989c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7989c-111">特性</span><span class="sxs-lookup"><span data-stu-id="7989c-111">Attributes</span></span>  
 <span data-ttu-id="7989c-112">无。</span><span class="sxs-lookup"><span data-stu-id="7989c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7989c-113">子元素</span><span class="sxs-lookup"><span data-stu-id="7989c-113">Child Elements</span></span>  
 <span data-ttu-id="7989c-114">无。</span><span class="sxs-lookup"><span data-stu-id="7989c-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7989c-115">父元素</span><span class="sxs-lookup"><span data-stu-id="7989c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7989c-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="7989c-116">**Element**</span></span>|<span data-ttu-id="7989c-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="7989c-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7989c-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="7989c-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="7989c-119">指定用于对网络请求进行身份验证的模块。</span><span class="sxs-lookup"><span data-stu-id="7989c-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7989c-120">备注</span><span class="sxs-lookup"><span data-stu-id="7989c-120">Remarks</span></span>  
 <span data-ttu-id="7989c-121">`clear`元素删除之前在配置文件或配置层次结构的较高级别中定义的所有身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="7989c-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7989c-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="7989c-122">Configuration Files</span></span>  
 <span data-ttu-id="7989c-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="7989c-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7989c-124">示例</span><span class="sxs-lookup"><span data-stu-id="7989c-124">Example</span></span>  
 <span data-ttu-id="7989c-125">下面的示例删除所有配置的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="7989c-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7989c-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7989c-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="7989c-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="7989c-127">Network Settings Schema</span></span>](index.md)
