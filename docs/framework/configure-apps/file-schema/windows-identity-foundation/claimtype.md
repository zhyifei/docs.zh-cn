---
title: '&lt;ClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94f8586a9ca63b8c1f1128cdda4a74ccfe0f5416
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtypegt"></a>&lt;ClaimType&gt;
指定一个可选或所需的传入安全令牌声明。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimTypeRequired >  
\<claimType >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|类型|声明类型。 通常一个 URI。 必须的。|  
|可选|一个布尔值，指定声明类型是否为可选。 可选。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<claimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|指定传入安全令牌所需的声明的集。|
