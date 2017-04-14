---
title: "缓解操作：X509CertificiateClaimSet.FindClaims 方法 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# 缓解操作：X509CertificiateClaimSet.FindClaims 方法
从面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用开始，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> 方法尝试将 `claimType` 参数与其 SAN 字段中的所有 DNS 条目进行匹配。  
  
## 影响  
 此更改仅影响面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用。  
  
 对于面向 .NET Framework 先前版本的应用，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> 方法尝试仅将 `claimType` 参数与最后一个 DNS 条目进行匹配。  
  
## 缓解操作  
 如果无需进行此更改，则面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用可选择将以下配置设置添加到应用配置文件的 [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 节，以便不进行更改：  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" /> </runtime>  
  
```  
  
 此外，面向 .NET Framework 先前版本但在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 下运行的应用可选择将以下配置设置添加到应用配置文件的 [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 节，以便实现此行为：  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" /> </runtime>  
  
```  
  
## 请参阅  
 [重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)