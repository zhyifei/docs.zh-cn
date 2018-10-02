---
title: '&lt;system.identityModel&gt;'
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 1b3121a6e7e036ec268cf83ffbf545c0e669a9b9
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032274"
---
# <a name="ltsystemidentitymodelgt"></a><span data-ttu-id="24816-102">&lt;system.identityModel&gt;</span><span class="sxs-lookup"><span data-stu-id="24816-102">&lt;system.identityModel&gt;</span></span>
<span data-ttu-id="24816-103">提供用于启用应用程序中的 Windows Identity Foundation (WIF) 选项的配置。</span><span class="sxs-lookup"><span data-stu-id="24816-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="24816-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="24816-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24816-105">语法</span><span class="sxs-lookup"><span data-stu-id="24816-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24816-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="24816-106">Attributes and Elements</span></span>  
 <span data-ttu-id="24816-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="24816-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24816-108">特性</span><span class="sxs-lookup"><span data-stu-id="24816-108">Attributes</span></span>  
 <span data-ttu-id="24816-109">无</span><span class="sxs-lookup"><span data-stu-id="24816-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="24816-110">子元素</span><span class="sxs-lookup"><span data-stu-id="24816-110">Child Elements</span></span>  
  
|<span data-ttu-id="24816-111">元素</span><span class="sxs-lookup"><span data-stu-id="24816-111">Element</span></span>|<span data-ttu-id="24816-112">描述</span><span class="sxs-lookup"><span data-stu-id="24816-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24816-113">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="24816-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="24816-114">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="24816-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24816-115">父元素</span><span class="sxs-lookup"><span data-stu-id="24816-115">Parent Elements</span></span>  
  
|<span data-ttu-id="24816-116">元素</span><span class="sxs-lookup"><span data-stu-id="24816-116">Element</span></span>|<span data-ttu-id="24816-117">描述</span><span class="sxs-lookup"><span data-stu-id="24816-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="24816-118">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="24816-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24816-119">备注</span><span class="sxs-lookup"><span data-stu-id="24816-119">Remarks</span></span>  
 <span data-ttu-id="24816-120">添加`<system.identityModel>`到配置文件来配置服务或应用程序以使用 Windows Identity Foundation (WIF) 部分。</span><span class="sxs-lookup"><span data-stu-id="24816-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="24816-121">`<system.identityModel>`元素表示由<xref:System.IdentityModel.Configuration.SystemIdentityModelSection>类。</span><span class="sxs-lookup"><span data-stu-id="24816-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24816-122">示例</span><span class="sxs-lookup"><span data-stu-id="24816-122">Example</span></span>  
 <span data-ttu-id="24816-123">下面的示例演示如何添加`<system.identityModel>`到配置文件的部分。</span><span class="sxs-lookup"><span data-stu-id="24816-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="24816-124">必须首先添加下的配置节和命名空间声明`<configSections>`元素。</span><span class="sxs-lookup"><span data-stu-id="24816-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="24816-125">然后，可以添加`<system.IdentityModel>`为配置文件指定一个或多个标识配置元素。</span><span class="sxs-lookup"><span data-stu-id="24816-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="24816-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="24816-126">See Also</span></span>  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
