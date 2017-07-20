---
title: "密码设置架构 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "配置架构 [.NET Framework], 密码系统"
  - "配置节 [.NET Framework]"
  - "配置设置 [.NET Framework], 密码系统"
  - "密码系统, 映射算法名称"
  - "密码系统, 设置架构"
  - "元素 [.NET Framework], 密码系统"
  - "架构配置设置"
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 密码设置架构
密码设置架构中包含的元素指定如何将友好算法名称映射到实现加密算法的类。  
  
 [\<configuration（配置）\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<mscorlib\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [\<cryptographySettings\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [\<cryptoNameMapping\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [\<cryptoClasses\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [\<oidMap\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [\<oidEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|元素|说明|  
|--------|--------|  
|[\<\<cryptoClasses\>\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|包含密码类的列表，这些类具有到**\<nameEntry\>**元素中的友好名称的映射。|  
|[\<\<cryptoClass\>\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|包含一个密码类，该类具有到  **\<nameEntry\>**元素中的友好名称的映射。|  
|[\<\<cryptographySettings\>\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|包含密码设置。|  
|[\<\<cryptoNameMapping\>\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|包含类到友好名称的映射。|  
|[密码设置的 \<\<mscorlib\>\> 元素](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|包含 **\<cryptographySettings\>\<\>**元素。|  
|[\<\<nameEntry\>\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|将类名映射为友好算法名称，这样允许一个类具有多个友好名称。|  
|[\<\<oidEntry\>\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|将 ASN.1 对象标识符 \(OID\) 映射到友好名称。|  
|[\<\<oidMap\>\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|包含到类的 ASN.1 OID 映射。|  
  
## 请参阅  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [加密服务](../../../../../docs/standard/security/cryptographic-services.md)