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
# <a name="ltsystemidentitymodelgt"></a>&lt;system.identityModel&gt;
提供用于启用应用程序中的 Windows Identity Foundation (WIF) 选项的配置。  
  
 \<system.identityModel>  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|指定服务级别标识设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`<configuration>`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
  
## <a name="remarks"></a>备注  
 添加`<system.identityModel>`到配置文件来配置服务或应用程序以使用 Windows Identity Foundation (WIF) 部分。 `<system.identityModel>`元素表示由<xref:System.IdentityModel.Configuration.SystemIdentityModelSection>类。  
  
## <a name="example"></a>示例  
 下面的示例演示如何添加`<system.identityModel>`到配置文件的部分。 必须首先添加下的配置节和命名空间声明`<configSections>`元素。 然后，可以添加`<system.IdentityModel>`为配置文件指定一个或多个标识配置元素。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
