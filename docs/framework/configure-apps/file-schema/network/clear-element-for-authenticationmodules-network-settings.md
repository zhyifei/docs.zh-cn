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
ms.openlocfilehash: 3c018c7d474286f7a9cde2d070e4b54d164b5b40
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094367"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="13d10-102">\<清除 > authenticationModules （网络设置） 的</span><span class="sxs-lookup"><span data-stu-id="13d10-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="13d10-103">清除所有身份验证模块从应用程序。</span><span class="sxs-lookup"><span data-stu-id="13d10-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="13d10-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="13d10-104">\<configuration></span></span>  
<span data-ttu-id="13d10-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="13d10-105">\<system.net></span></span>  
<span data-ttu-id="13d10-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="13d10-106">\<authenticationModules></span></span>  
<span data-ttu-id="13d10-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="13d10-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d10-108">语法</span><span class="sxs-lookup"><span data-stu-id="13d10-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13d10-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13d10-109">Attributes and Elements</span></span>  
 <span data-ttu-id="13d10-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="13d10-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13d10-111">特性</span><span class="sxs-lookup"><span data-stu-id="13d10-111">Attributes</span></span>  
 <span data-ttu-id="13d10-112">无。</span><span class="sxs-lookup"><span data-stu-id="13d10-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13d10-113">子元素</span><span class="sxs-lookup"><span data-stu-id="13d10-113">Child Elements</span></span>  
 <span data-ttu-id="13d10-114">无。</span><span class="sxs-lookup"><span data-stu-id="13d10-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13d10-115">父元素</span><span class="sxs-lookup"><span data-stu-id="13d10-115">Parent Elements</span></span>  
  
|<span data-ttu-id="13d10-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="13d10-116">**Element**</span></span>|<span data-ttu-id="13d10-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="13d10-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="13d10-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="13d10-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="13d10-119">指定使用网络请求进行身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="13d10-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13d10-120">备注</span><span class="sxs-lookup"><span data-stu-id="13d10-120">Remarks</span></span>  
 <span data-ttu-id="13d10-121">`clear`元素移除所有配置文件中或在配置层次结构中较高级别上前面定义的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="13d10-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="13d10-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="13d10-122">Configuration Files</span></span>  
 <span data-ttu-id="13d10-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="13d10-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13d10-124">示例</span><span class="sxs-lookup"><span data-stu-id="13d10-124">Example</span></span>  
 <span data-ttu-id="13d10-125">以下示例将删除所有配置的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="13d10-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="13d10-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="13d10-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="13d10-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="13d10-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
