---
title: 缓解：X509CertificateClaimSet.FindClaims 方法
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
ms.openlocfilehash: 0b306960c4f11bb6f54aecaeb13297e7725e16a8
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102640"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>缓解：X509CertificateClaimSet.FindClaims 方法

从面向 .NET Framework 4.6.1 的应用开始，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 方法尝试将 `claimType` 参数与其 SAN 字段中的所有 DNS 条目进行匹配。  
  
## <a name="impact"></a>影响  
 此更改仅影响面向从 .NET Framework 4.6.1 开始的 .NET Framework 版本的应用。  
  
 对于面向 .NET Framework 先前版本的应用，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 方法尝试仅将 `claimType` 参数与最后一个 DNS 条目进行匹配。  
  
## <a name="mitigation"></a>缓解  
 如果无需进行此更改，则面向从 .NET Framework 4.6.1 开始的 .NET Framework 版本的应用可通过将以下配置设置添加到应用配置文件的 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 部分，来选择放弃更改：  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 此外，面向 .NET Framework 以前版本但在 .NET Framework 4.6.1 或更高版本下运行的应用可通过将以下配置设置添加到应用配置文件的 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 部分，来选择实现此行为：  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a>请参阅

- [应用程序兼容性](application-compatibility.md)
