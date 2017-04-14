---
title: "延迟为程序集签名 | Microsoft Docs"
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
  - "推迟程序集签名"
  - "对程序集进行签名"
  - "程序集 [.NET Framework]，签名"
  - "具有强名称的程序集，延迟程序集签名"
  - "部分程序集签名"
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 延迟为程序集签名
一个单位可以具有开发人员在日常使用中无法访问的严密保护的密钥对。  公钥通常是可用的，但对私钥的访问权仅限于少数个人。  开发强名称程序集时，每个引用具有强名称的目标程序集的程序集中都包含了用于为目标程序集指定强名称的公钥的标记。  这要求公钥在开发过程中可用。  
  
 您可以在生成时使用延迟签名或部分签名，在可迁移可执行 \(PE\) 文件中为强名称签名保留空间，但要将实际签名延迟至后面某些阶段（通常就在传送程序集之前）。  
  
 下面的步骤说明了延时对程序集签名的过程：  
  
1.  从将执行最终签名的单位获取密钥对的公钥部分。  此密钥通常是 .snk 文件的形式，使用 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 提供的[强名称工具 \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 可创建此文件。  
  
2.  使用 <xref:System.Reflection> 中的两种自定义特性来批注程序集的源代码：  
  
    -   <xref:System.Reflection.AssemblyKeyFileAttribute>，它将包含公钥的文件的名称作为参数传递给其构造函数。  
  
    -   <xref:System.Reflection.AssemblyDelaySignAttribute>，它通过将 **true** 作为参数传递给其构造函数，表明正在使用延迟签名。  例如：  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
         [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
         [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3.  编译器将公钥插入程序集清单，并在 PE 文件中为完整的强名称签名保留空间。  真正的公钥必须在生成程序集时存储，以便引用此程序集的其他程序集可获取密钥以存储在它们自已的程序集引用中。  
  
4.  由于程序集没有有效的强名称签名，所以必须关闭该签名的验证。  您可以将“强名称”工具与 **–Vr** 选项一起使用来执行此操作。  
  
     下面的示例关闭名为 `myAssembly.dll` 的程序集的验证。  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     在无法运行强名称工具的平台上关闭验证，如高级RISC \(ARM\) 微处理器，使用 **–Vk** 选项创建注册表文件。  导入注册表文文件到要关闭验证的计算机上的注册表。  下面的示例为创建`myAssembly.dll`的注册键文件。  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     使用 **–Vr** 或 **–Vk** 选项，则可选择可以包括测试键签名的 .snk 文件。  
  
    > [!CAUTION]
    >  仅在开发阶段使用**\-Vr** or **–Vk**选项。  将程序集添加到跳过验证列表会产生安全漏洞。  如果将某程序集添加到跳过验证列表中，则恶意程序集可以使用该程序集的完全指定程序集名称来隐藏身份，完全指定程序集名称由程序集名称、版本、区域性和公钥标记组成。  这使恶意程序集也可以跳过验证。  
  
    > [!NOTE]
    >  如果在 64 位计算机上使用 Visual Studio 进行开发的过程中使用延迟签名，并为**“Any CPU”**编译程序集，则可能必须应用 **\-Vr** 选项两次。（在 Visual Studio 中，**“Any CPU”**是**“目标平台”**生成属性的值；在从命令行进行编译时，此值是默认值。）若要从命令行或文件资源管理器运行应用程序，请使用 64 位版本的[Sn.exe（强名称工具）](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 以对程序集应用 **\-Vr** 选项。  若要在设计时将程序集加载到 Visual Studio 中（例如，如果程序集包含应用程序中的其他程序集所使用的组件），请使用 32 位版本的强名称工具。  这是因为，在从命令行运行程序集时，实时 \(JIT\) 编译器会将程序集编译为 64 位本机代码；在将程序集加载到设计时环境中时，实时 \(JIT\) 编译器会将程序集编译为 32 位本机代码。  
  
5.  以后，通常是在即将交付前，将程序集提交给组织的签名机构，以便与“强名称”工具一起使用 **–R** 选项来实际进行强名称签名。  
  
     下面的示例使用 `sgKey.snk` 密钥对为名为 `myAssembly.dll` 的程序集签署强名称。  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## 请参阅  
 [创建程序集](../../../docs/framework/app-domains/create-assemblies.md)   
 [如何：创建公钥\/私钥对](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)   
 [Sn.exe（强名称工具）](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)