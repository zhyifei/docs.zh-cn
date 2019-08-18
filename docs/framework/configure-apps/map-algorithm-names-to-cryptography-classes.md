---
title: 将算法名称映射到加密类
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 49f4b5b4b3634df5e648b5208448d644168e9d19
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566722"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a>将算法名称映射到加密类
开发人员可通过以下四种方式使用 Windows SDK 创建加密对象:  
  
- 使用**new**运算符创建对象。  
  
- 通过对该算法的抽象类调用**create**方法, 创建实现特定加密算法的对象。  
  
- 通过调用<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法, 创建实现特定加密算法的对象。  
  
- 通过对该类型算法<xref:System.Security.Cryptography.SymmetricAlgorithm>的抽象类调用**create**方法 (如), 创建一个实现一类加密算法 (如对称块密码) 的对象。  
  
 例如, 假设开发人员想要计算一组字节的 SHA1 哈希。 <xref:System.Security.Cryptography>命名空间包含 SHA1 算法的两个实现, 一个纯粹的托管实现, 另一个包装 CryptoAPI。 开发人员可以通过调用**new**运算符来选择实例化特定的 SHA1 <xref:System.Security.Cryptography.SHA1Managed>实现 (如)。 但是, 如果公共语言运行时加载哪个类 (只要类实现 SHA1 哈希算法), 开发人员就可以通过调用<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>方法来创建对象。 此方法调用**CryptoConfig. cryptoconfig.createfromname ("")** , 该方法必须返回 SHA1 哈希算法的一个实现。  
  
 开发人员还可以调用**CryptoConfig. cryptoconfig.createfromname ("SHA1")** , 因为默认情况下, 加密配置包括 .NET Framework 中附带的算法的短名称。  
  
 如果使用的哈希算法并不重要, 开发人员可以调用方法, <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType>这将返回实现哈希转换的对象。  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a>在配置文件中映射算法名称  
 默认情况下, 运行时为<xref:System.Security.Cryptography.SHA1CryptoServiceProvider>所有四个方案返回一个对象。 但是, 计算机管理员可以更改最后两个方案中的方法返回的对象的类型。 为此, 必须将友好算法名称映射到要在计算机配置文件 (Machine.config) 中使用的类。  
  
 下面的示例演示如何配置运行时, 使其成为**CryptoConfig、CRYPTOCONFIG.CREATEFROMNAME ("SHA1")** 和 HashAlgorithm. 的配置运行时的配置。 **返回对象。** `MySHA1HashClass`  
  
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
  
 您可以在[< 的 cryptoClass\>元素](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)中指定属性的名称 (上一个示例将属性`MySHA1Hash`命名为)。 CryptoClass > 元素中 **\<** 属性的值是公共语言运行时用来查找类的字符串。 您可以使用满足指定[完全限定的类型名称](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)中指定的要求的任何字符串。  
  
 许多算法名称可以映射到同一个类。 Y > 元素将类映射到一个友好算法名称。 [ \<](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) **Name**属性可以是在调用**CryptoConfig. cryptoconfig.createfromname**方法时使用的字符串, 也可以是<xref:System.Security.Cryptography>命名空间中抽象加密类的名称。 **Class**特性的值是 **\<cryptoClass >** 元素中的特性的名称。  
  
> [!NOTE]
>  可以通过调用<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>或**CryptoConfig. cryptoconfig.createfromname ("SHA1")** 方法获取 SHA1 算法。 每个方法仅保证返回实现 SHA1 算法的对象。 不需要将算法的每个友好名称映射到配置文件中的相同类。  
  
 有关默认名称及其映射到的类的列表, 请参阅<xref:System.Security.Cryptography.CryptoConfig>。  
  
## <a name="see-also"></a>请参阅

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
- [配置加密类](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
