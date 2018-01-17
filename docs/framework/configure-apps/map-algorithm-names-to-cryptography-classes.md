---
title: "将算法名称映射到加密类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9c9c5b1f69200d4ee5d39c98445b668813718dd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>将算法名称映射到加密类
有四种方法，开发人员可以创建加密对象使用[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:  
  
-   通过创建对象**新**运算符。  
  
-   创建一个对象，通过调用实现特定的加密算法**创建**该算法的抽象类上的方法。  
  
-   创建一个对象，通过调用实现特定的加密算法<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法。  
  
-   创建实现加密算法 （如一种对称的块密码） 的类通过调用的对象**创建**算法该类型的抽象类上的方法 (如<xref:System.Security.Cryptography.SymmetricAlgorithm>)。  
  
 例如，假设开发人员想要计算的一组字节的 SHA1 哈希。 <xref:System.Security.Cryptography>命名空间包含 SHA1 算法、 一个纯托管的实现和一个包装 CryptoAPI 的两个实现。 开发人员可以选择实例化特定 SHA1 实现 (如<xref:System.Security.Cryptography.SHA1Managed>) 通过调用**新**运算符。 但是，如果它并不重要公共语言运行时加载，只要类实现的 SHA1 哈希算法的类，开发人员可以创建一个对象通过调用<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>方法。 此方法调用**System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**，其必须返回 SHA1 哈希算法实现。  
  
 开发人员还可以调用**System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")**因为默认情况下，加密配置包括在.NET Framework 中提供的算法的短名称。  
  
 如果它并不重要使用的哈希算法，开发人员可以调用<xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType>方法，返回实现哈希转换的对象。  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>映射算法名称在配置文件中  
 默认情况下，运行时返回<xref:System.Security.Cryptography.SHA1CryptoServiceProvider>所有四种方案的对象。 但是，计算机管理员可以更改中的最后两个方案的方法返回的对象的类型。 若要执行此操作，你必须映射到你想要在计算机配置文件 (Machine.config) 中使用的类的友好算法名称。  
  
 下面的示例演示如何配置运行时，以便**System.Security.Cryptography.SHA1.Create**， **System.Security.CryptoConfig.CreateFromName("SHA1")**，和**System.Security.Cryptography.HashAlgorithm.Create**返回`MySHA1HashClass`对象。  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 你可以指定中的属性的名称[< cryptoClass\>元素](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)(前面的示例将该特性命名`MySHA1Hash`)。 中的属性的值 **\<cryptoClass >**元素是一个字符串，公共语言运行时使用找到的类。 你可以使用任何字符串都满足中指定的要求[指定完全限定的类型名称](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。  
  
 许多算法名称可以映射到同一个类。 [ \<NameEntry > 元素](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)将类映射到一个友好算法名称。 **名称**属性可以是在调用时使用的任一字符串**System.Security.Cryptography.CryptoConfig.CreateFromName**方法或在抽象加密类的名称<xref:System.Security.Cryptography>命名空间。 值**类**特性是中的属性的名称 **\<cryptoClass >**元素。  
  
> [!NOTE]
>  你可以通过调用获取 SHA1 算法<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>或**Security.CryptoConfig.CreateFromName("SHA1")**方法。 每个方法仅保证它返回实现 SHA1 算法的对象。 无需将每个友好算法名称映射到配置文件中的同一个类。  
  
 默认名称以及它们映射到的类的列表，请参阅<xref:System.Security.Cryptography.CryptoConfig>。  
  
## <a name="see-also"></a>请参阅  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 [配置加密类](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
