---
title: "改进的强命名 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "强命名 [.NET Framework], 增强"
  - "具有强名称的程序集"
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 改进的强命名
强名称签名是在 .NET Framework 中的一个用来标识程序集的标识。  它是通常用于验证已从建立人（签名人）传递到收件人（验证程序）的数据完整性的公钥数字。  此签名可用作程序集的唯一标识，从而确保对程序集的引用明确。  程序集作为生成过程的一部分得到签名，并在加载后得到验证。  
  
 强名称签名帮助防止恶意方篡改程序集然后使用原始签名者的密钥重新签名程序集。  但是，强名称密钥不包含有关出版商的任何可靠信息，也不包含证书层次结构。  强名称签名不保障对程序集进行签名的人员的可信度，也不指示该人员是否是该键的合法所有者；它仅指示键的所有者对程序集进行了签名。  因此，建议不要使用强名称签名作为信任第三方代码的安全验证程序。  Microsoft Authenticode 是推荐使用的身份验证代码。  
  
## 常规强名称的限制  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 之前版本使用的强命名技术具有以下缺点：  
  
-   由于密钥持续受到攻击，所以使用改进的技术和硬件可以更轻松地从公钥推断私钥。  若要防止攻击，必须设置较大的密钥。[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]之前的 NET Framework 版本可以用任意大小的密钥（默认大小是 1024 位）签名，但是，用新的密钥为程序集签名会破坏引用程序集早期标识的所有二进制文件。  因此，如果要维护兼容性，则升级签名密钥的范围将极其困难。  
  
-   强名称签名仅支持 SHA\-1 算法。  最近发现 SHA\-1 不适合安全哈希应用程序。  因此，需要使用更强的算法（SHA\-256 或更高）。  SHA\-1 可能丢失其 FIPS 站立，其将呈现选择仅使用 FIPS 兼容软件和算法的问题。  
  
## 增强的强名称的优点  
 增强的强名称的主要优点是与预先存在的强名称的兼容性以及要求一个标识等效于另一个的能力：  
  
-   具有预先存在的已签名的程序集的开发人员可以将他们的标识迁移到 SHA\-2 算法，同时能保留与引用旧标识的程序集的兼容性。  
  
-   创建新的程序集且不关心预先存在的强名称签名的开发人员可以使用更安全的 SHA\-2 算法并以他们一贯的方式对程序集进行签名。  
  
## 使用增强的强名称  
 强名称密钥包括签名密钥和标识键。  程序集通过签名密钥签名，并由标识密钥标识。  在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 之前，这两个键相同。  自 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 开始，标识键就与早期 .NET Framework 版本保持相同，但是，更强的哈希算法加强了签名密钥。  此外，签名密钥使用标识键签名，以创建副署。  
  
 <xref:System.Reflection.AssemblySignatureKeyAttribute> 特性使程序集元数据能够使用预先存在的公钥进行程序集标识，使旧程序集引用可以继续工作。<xref:System.Reflection.AssemblySignatureKeyAttribute> 特性使用副署确保新签名密钥的所有者也是旧标识的所有者。  
  
### 不用键迁移，使用 SHA\-2 登录  
 从“命令提示窗口”中运行以下命令签名不带迁移的强名称的程序集。  
  
1.  生成新的标识密钥（如有必要）。  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2.  提取身份公钥，并指定当签署此密钥时应采用 SHA\-2 算法。  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3.  使用标识公钥文件对程序集延迟签名。  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4.  为具有完整身份密钥对的程序集签名。  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### 通过键迁移使用 SHA\-2 登录  
 从“命令提示窗口”中运行以下命令签名带迁移的强名称的程序集。  
  
1.  生成标识和签名密钥对（如有必要）。  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2.  提取签名公钥，并指定当签署此密钥时应采用 SHA\-2 算法。  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3.  提取身份公钥将确定生成副署的哈希算法。  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4.  生成 <xref:System.Reflection.AssemblySignatureKeyAttribute> 特性的参数，并将该特性附加到程序集。  
  
    ```  
    sn -ac IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  
  
5.  使用标识公钥对程序集延迟签名。  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
  
    ```  
  
6.  使用签名密钥对以完全签发程序集。  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## 请参阅  
 [创建和使用具有强名称的程序集](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)