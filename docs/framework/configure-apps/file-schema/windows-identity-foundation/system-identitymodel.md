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
# <a name="systemidentitymodel"></a>\<system.identityModel>
为在应用程序中启用 Windows Identity Foundation （WIF）选项提供配置。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp; **\<System.identitymodel >**  
  
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
|[\<identityConfiguration>](identityconfiguration.md)|指定服务级别标识设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`<configuration>`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
  
## <a name="remarks"></a>备注  
 `<system.identityModel>`将部分添加到配置文件，以将服务或应用程序配置为使用 Windows Identity Foundation （WIF）。 元素由<xref:System.IdentityModel.Configuration.SystemIdentityModelSection>类表示。 `<system.identityModel>`  
  
## <a name="example"></a>示例  
 下面的示例演示如何将`<system.identityModel>`节添加到配置文件。 必须首先在`<configSections>`元素下添加配置节和命名空间声明。 然后，可以将`<system.IdentityModel>`元素添加到配置文件中，以指定一个或多个标识配置。  
  
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

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
