---
title: "如何：创建发行者策略"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 182882d33772054c7ac4208ca9571fa8018c2a07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-publisher-policy"></a>如何：创建发行者策略
程序集的供应商可以状态应用程序应使用通过包括发布服务器策略文件与已升级的程序集的程序集的较新版本。 发布服务器策略文件指定程序集重定向和基本代码设置，并为应用程序配置文件使用相同的格式。 发布服务器策略文件编译成程序集和放入全局程序集缓存。  
  
 有三个步骤中创建发布服务器策略涉及：  
  
1.  创建发布服务器策略文件。  
  
2.  创建发行者策略程序集。  
  
3.  将发行者策略程序集添加到全局程序集缓存中。  
  
 发布服务器策略的架构中所述[重定向程序集版本](../../../docs/framework/configure-apps/redirect-assembly-versions.md)。 下面的示例说明了一个发行者策略文件，将重定向的一个版本`myAssembly`到另一个。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 若要了解如何指定基本代码，请参阅[指定程序集的位置](../../../docs/framework/configure-apps/specify-assembly-location.md)。  
  
## <a name="creating-the-publisher-policy-assembly"></a>创建发行者策略程序集  
 使用[程序集链接器 (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)创建发行者策略程序集。  
  
#### <a name="to-create-a-publisher-policy-assembly"></a>若要创建发行者策略程序集  
  
1.  在命令提示符下键入以下命令：  
  
     **al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*  
  
     在此命令：  
  
    -   *PublisherPolicyFile*参数是发布服务器策略文件的名称。  
  
    -   *PublisherPolicyAssemblyFile*参数是导致此命令的发行者策略程序集的名称。 程序集文件名称必须遵循格式：  
  
         **策略。** *majorNumber* **。** *minorNumber* **。** *mainAssemblyName* **.dll**  
  
    -   *KeyPairFile*参数是包含密钥对的文件的名称。 你必须签名的程序集和具有相同的密钥对的发行者策略程序集。  
  
    -   *ProcessorArchitecture*参数标识的特定于处理器的程序集的目标平台。  
  
        > [!NOTE]
        >  面向特定的处理器体系结构的能力是.NET Framework 2.0 版中新增功能。  
  
     下面的命令创建名为的发行者策略程序集`policy.1.0.myAssembly`从发布服务器策略文件调用`pub.config`，对使用的密钥对中的程序集分配强名称`sgKey.snk`文件中，并指定该程序集针对 x86处理器体系结构。  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     发行者策略程序集必须与它将应用于程序集的处理器体系结构匹配。 因此，如果你的程序集具有<xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A>值<xref:System.Reflection.ProcessorArchitecture.MSIL>，该程序集的发布服务器策略程序集必须用来创建`/platform:anycpu`。 必须提供单独为每个特定于处理器的程序集的发行者策略程序集。  
  
     此规则的结果是版本号的，若要更改的程序集的处理器体系结构，你必须更改的主要或次要组件，以便你可以提供具有正确的处理器体系结构的新发布服务器策略程序集。 程序集具有不同的处理器体系结构，旧的发行者策略程序集无法服务你的程序集。  
  
     另一个后果是版本 2.0 链接器不能用于创建编译使用早期版本的.NET Framework 中，因为它始终指定处理器体系结构的程序集的发行者策略程序集。  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>将发行者策略程序集添加到全局程序集缓存  
 使用[全局程序集缓存工具 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)将发行者策略程序集添加到全局程序集缓存。  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>若要将发行者策略程序集添加到全局程序集缓存  
  
1.  在命令提示符下键入以下命令：  
  
     **gacutil /i***publisherPolicyAssemblyFile*   
  
     以下命令将添加`policy.1.0.myAssembly.dll`到全局程序集缓存。  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  无法将发行者策略程序集添加到全局程序集缓存中，除非原始发布服务器策略文件位于与程序集位于同一目录中。  
  
## <a name="see-also"></a>请参阅  
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [配置应用程序](../../../docs/framework/configure-apps/index.md)  
 [配置.NET Framework 应用](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [运行时设置架构](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)  
 [重定向程序集版本](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
