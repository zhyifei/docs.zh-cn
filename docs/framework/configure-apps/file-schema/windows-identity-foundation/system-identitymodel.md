---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: a54f5ce86aee1a5e831c0b10aa1471d4a82f40a5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251795"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="be1dc-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="be1dc-102">\<system.identityModel></span></span>
<span data-ttu-id="be1dc-103">为在应用程序中启用 Windows Identity Foundation （WIF）选项提供配置。</span><span class="sxs-lookup"><span data-stu-id="be1dc-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
<span data-ttu-id="be1dc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="be1dc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="be1dc-105">&nbsp;&nbsp; **\<System.identitymodel >**</span><span class="sxs-lookup"><span data-stu-id="be1dc-105">&nbsp;&nbsp;**\<system.identityModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be1dc-106">语法</span><span class="sxs-lookup"><span data-stu-id="be1dc-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be1dc-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="be1dc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="be1dc-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="be1dc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be1dc-109">特性</span><span class="sxs-lookup"><span data-stu-id="be1dc-109">Attributes</span></span>  
 <span data-ttu-id="be1dc-110">无</span><span class="sxs-lookup"><span data-stu-id="be1dc-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="be1dc-111">子元素</span><span class="sxs-lookup"><span data-stu-id="be1dc-111">Child Elements</span></span>  
  
|<span data-ttu-id="be1dc-112">元素</span><span class="sxs-lookup"><span data-stu-id="be1dc-112">Element</span></span>|<span data-ttu-id="be1dc-113">描述</span><span class="sxs-lookup"><span data-stu-id="be1dc-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be1dc-114">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="be1dc-114">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="be1dc-115">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="be1dc-115">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be1dc-116">父元素</span><span class="sxs-lookup"><span data-stu-id="be1dc-116">Parent Elements</span></span>  
  
|<span data-ttu-id="be1dc-117">元素</span><span class="sxs-lookup"><span data-stu-id="be1dc-117">Element</span></span>|<span data-ttu-id="be1dc-118">描述</span><span class="sxs-lookup"><span data-stu-id="be1dc-118">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="be1dc-119">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="be1dc-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be1dc-120">备注</span><span class="sxs-lookup"><span data-stu-id="be1dc-120">Remarks</span></span>  
 <span data-ttu-id="be1dc-121">`<system.identityModel>`将部分添加到配置文件，以将服务或应用程序配置为使用 Windows Identity Foundation （WIF）。</span><span class="sxs-lookup"><span data-stu-id="be1dc-121">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="be1dc-122">元素由<xref:System.IdentityModel.Configuration.SystemIdentityModelSection>类表示。 `<system.identityModel>`</span><span class="sxs-lookup"><span data-stu-id="be1dc-122">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be1dc-123">示例</span><span class="sxs-lookup"><span data-stu-id="be1dc-123">Example</span></span>  
 <span data-ttu-id="be1dc-124">下面的示例演示如何将`<system.identityModel>`节添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="be1dc-124">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="be1dc-125">必须首先在`<configSections>`元素下添加配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="be1dc-125">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="be1dc-126">然后，可以将`<system.IdentityModel>`元素添加到配置文件中，以指定一个或多个标识配置。</span><span class="sxs-lookup"><span data-stu-id="be1dc-126">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="be1dc-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="be1dc-127">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
