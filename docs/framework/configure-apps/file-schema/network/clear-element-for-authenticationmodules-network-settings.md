---
title: '&lt;清除&gt;authenticationModules （网络设置） 的'
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
ms.openlocfilehash: 42fa6a44891e012300f61f1a11a47537c6739e2c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205186"
---
# <a name="ltcleargt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="a6533-102">&lt;清除&gt;authenticationModules （网络设置） 的</span><span class="sxs-lookup"><span data-stu-id="a6533-102">&lt;clear&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="a6533-103">清除所有身份验证模块从应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6533-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="a6533-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a6533-104">\<configuration></span></span>  
<span data-ttu-id="a6533-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a6533-105">\<system.net></span></span>  
<span data-ttu-id="a6533-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="a6533-106">\<authenticationModules></span></span>  
<span data-ttu-id="a6533-107">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="a6533-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6533-108">语法</span><span class="sxs-lookup"><span data-stu-id="a6533-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6533-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a6533-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a6533-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a6533-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6533-111">特性</span><span class="sxs-lookup"><span data-stu-id="a6533-111">Attributes</span></span>  
 <span data-ttu-id="a6533-112">无。</span><span class="sxs-lookup"><span data-stu-id="a6533-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a6533-113">子元素</span><span class="sxs-lookup"><span data-stu-id="a6533-113">Child Elements</span></span>  
 <span data-ttu-id="a6533-114">无。</span><span class="sxs-lookup"><span data-stu-id="a6533-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6533-115">父元素</span><span class="sxs-lookup"><span data-stu-id="a6533-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a6533-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="a6533-116">**Element**</span></span>|<span data-ttu-id="a6533-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="a6533-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a6533-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="a6533-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="a6533-119">指定使用网络请求进行身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="a6533-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6533-120">备注</span><span class="sxs-lookup"><span data-stu-id="a6533-120">Remarks</span></span>  
 <span data-ttu-id="a6533-121">`clear`元素移除所有配置文件中或在配置层次结构中较高级别上前面定义的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="a6533-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a6533-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="a6533-122">Configuration Files</span></span>  
 <span data-ttu-id="a6533-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="a6533-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6533-124">示例</span><span class="sxs-lookup"><span data-stu-id="a6533-124">Example</span></span>  
 <span data-ttu-id="a6533-125">以下示例将删除所有配置的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="a6533-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6533-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6533-126">See Also</span></span>  
- <xref:System.Net.IAuthenticationModule>  
- <xref:System.Net.AuthenticationManager>  
- [<span data-ttu-id="a6533-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="a6533-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
