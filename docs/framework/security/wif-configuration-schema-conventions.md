---
title: "WIF 配置架构约定 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# WIF 配置架构约定
本主题讨论约定使用在Windows标识基础\(WIF\)配置主题中并描述了用于 [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) 和 [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 部分和属性的一些常用的功能。  
  
<a name="BKMK_Modes"></a>   
## 模式  
 许多WIF配置元素具有 `mode` 属性。  此属性通常控制要选件类用于执行处理的特定部分，哪些配置元素允许作为当前元素的子元素。  配置会引发错误因架构设置，因此，如果在配置文件中的元素将被忽略。  
  
<a name="BKMK_TimespanValues"></a>   
## timespan值  
 其中 <xref:System.TimeSpan> 用作属性的类型，请参见 <xref:System.TimeSpan.Parse%28System.String%29> 方法发现了允许的格式。  此格式符合以下规范。  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 例如，“30 "，“30.00:00”，“30.00:00: 00 "的所有这意味着30天;和“00:05”，“00:05: 00 "，“0.00:05: 00.00 "的所有这意味着5分钟。  
  
<a name="BKMK_CertificateReferences"></a>   
## 证书引用  
 使用 `<certificateReference>` 元素，多个元素为对证书。  当引用证书时，以下属性可用。  
  
|||  
|-|-|  
|`storeLocation`|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> 枚举的值: `CurrentUser` 或 `CurrentMachine`。|  
|`storeName`|<xref:System.Security.Cryptography.X509Certificates.StoreName> 枚举的值;最有用此上下文的是 `My` 和 `TrustedPeople`。|  
|`x509FindType`|<xref:System.Security.Cryptography.X509Certificates.X509FindType> 枚举的值;最有用此上下文的是 `FindBySubjectName` 和 `FindByThumbprint`。  若要消除错误的可能性，建议 `FindByThumbprint` 类型用于生产环境中。|  
|`findValue`|用于的值基于 `x509FindType` 属性查找证书。  若要消除错误的可能性，建议 `FindByThumbprint` 类型用于生产环境中。  当 `FindByThumbPrint` 指定时，此属性采用证书指纹匹配的十六进制字符串形式的值;例如，“97249e1a5fa6bee5e515b82111ef524a4c91583f”。|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## 自定义类型引用  
 使用 `type` 属性，多个元素引用自定义类型。  此属性应指定自定义类型的名称。  若要引用从全局程序集缓存\(GAC\)的类型，应使用强名称。  若要引用从一个程序集中的类型在bin目录中，程序集限定的简单引用可以使用。  在App\_Code\/内容定义的类型可通过指定类型还引用名称没有限定的程序集。  
  
 必须从指定的类型派生自定义类型，并且它们必须提供 `public` 默认\(0个参数\)构造函数。  
  
## 请参阅  
 [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)   
 [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)