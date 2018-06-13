---
title: '&lt;清除&gt;authenticationModules （网络设置） 的元素'
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 94e0242ca685e8b0118a55ba44fb0569c13f10f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751982"
---
# <a name="ltcleargt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="e7a12-102">&lt;清除&gt;authenticationModules （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="e7a12-102">&lt;clear&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="e7a12-103">清除从应用程序的所有身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="e7a12-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="e7a12-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e7a12-104">\<configuration></span></span>  
<span data-ttu-id="e7a12-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e7a12-105">\<system.net></span></span>  
<span data-ttu-id="e7a12-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="e7a12-106">\<authenticationModules></span></span>  
<span data-ttu-id="e7a12-107">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="e7a12-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a12-108">语法</span><span class="sxs-lookup"><span data-stu-id="e7a12-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7a12-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e7a12-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e7a12-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e7a12-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7a12-111">特性</span><span class="sxs-lookup"><span data-stu-id="e7a12-111">Attributes</span></span>  
 <span data-ttu-id="e7a12-112">无。</span><span class="sxs-lookup"><span data-stu-id="e7a12-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7a12-113">子元素</span><span class="sxs-lookup"><span data-stu-id="e7a12-113">Child Elements</span></span>  
 <span data-ttu-id="e7a12-114">无。</span><span class="sxs-lookup"><span data-stu-id="e7a12-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7a12-115">父元素</span><span class="sxs-lookup"><span data-stu-id="e7a12-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e7a12-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="e7a12-116">**Element**</span></span>|<span data-ttu-id="e7a12-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="e7a12-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e7a12-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="e7a12-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="e7a12-119">指定用来验证网络请求的模块。</span><span class="sxs-lookup"><span data-stu-id="e7a12-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7a12-120">备注</span><span class="sxs-lookup"><span data-stu-id="e7a12-120">Remarks</span></span>  
 <span data-ttu-id="e7a12-121">`clear`元素中删除配置文件中或在配置层次结构中较高级别前面定义的所有身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="e7a12-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e7a12-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="e7a12-122">Configuration Files</span></span>  
 <span data-ttu-id="e7a12-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="e7a12-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7a12-124">示例</span><span class="sxs-lookup"><span data-stu-id="e7a12-124">Example</span></span>  
 <span data-ttu-id="e7a12-125">下面的示例中移除所有配置的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="e7a12-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7a12-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7a12-126">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="e7a12-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="e7a12-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
