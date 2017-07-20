---
title: "延迟为程序集签名 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2fce2174da6b5d954e0197d7c834289070c09a22
ms.contentlocale: zh-cn
ms.lasthandoff: 06/02/2017

---
# <a name="delay-signing-an-assembly"></a>延迟为程序集签名
组织可以使用严密保护的密钥对，开发人员无法每天对其进行访问。 通常情况下公钥可用，但私钥的访问权限仅限于少数几个人。 开发使用强名称的程序集时，每个引用强名称目标程序集的程序集都包含用于向目标程序集赋予强名称的公钥的标记。 这要求公钥在开发过程中可用。  
  
 生成时，可以使用延迟签名或部分签名，从而在可移植可执行 (PE) 文件中保留用于强名称签名的空间，而将实际签名延迟到之后某个阶段执行（通常在传送程序集之前）。  
  
 以下步骤概述了延迟程序集签名的过程：  
  
1.  从将执行最终签名的组织处获取密钥对的公钥部分。 此密钥通常是 .snk 文件，可以通过使用 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 提供的[强名称工具 (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 创建。  
  
2.  使用 <xref:System.Reflection> 中的两个自定义属性对程序集的源代码进行注释：  
  
    -   <xref:System.Reflection.AssemblyKeyFileAttribute>，将包含公钥的文件名作为参数传递给其构造函数。  
  
    -   <xref:System.Reflection.AssemblyDelaySignAttribute>，通过将 true 作为参数传递给其构造函数来指示正在采用延迟签名。 例如：  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)][!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)][!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3.  编译器将公钥插入程序集清单，并在 PE 文件中保留用于完整的强名称签名的空间。 生成程序集后，必须存储真正的公钥，这样引用此程序集的其他程序集才能获取该密钥，并将其存储在自己的程序集引用中。  
  
4.  程序集没有有效的强名称签名，因此必须关闭对此签名的验证。 可配合使用强名称工具和 –Vr 选项来实现此操作。  
  
     以下示例关闭了对名为 `myAssembly.dll` 的程序集的验证。  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     若要在无法运行强名称工具的平台上（如高级 RISC 计算机 (ARM) 微处理器）关闭验证，请使用 –Vk 选项创建注册表文件。 将该注册表文件导入到要关闭验证的计算机上的注册表中。 下面的示例为 `myAssembly.dll` 创建了一个注册表文件。  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     通过 –Vr 或 –Vk 选项，可以选择是否包括 .snk 文件以测试密钥签名。  
  
    > [!CAUTION]
    >  仅在开发阶段使用 -Vr 或 –Vk 选项。 将程序集添加到跳过验证列表会产生安全漏洞。 如果将某程序集添加到跳过验证列表中，则恶意程序集可以使用该程序集的完全指定程序集名称来隐藏身份，完全指定程序集名称由程序集名称、版本、区域性和公钥标记组成。 这使恶意程序集也可以跳过验证。  
  
    > [!NOTE]
    >  如果在 64 位电脑上使用 Visual Studio 进行开发时使用延迟签名，并且编译“任何 CPU”的程序集，可能需要两次应用 -Vr 选项。 （在 Visual Studio 中，“任何 CPU”是平台目标生成属性的一个值；从命令行中编译时，它是默认值。）若要在命令行或文件资源管理器中运行应用程序，请使用 64 位版本的 [Sn.exe（强签名工具）](../../../docs/framework/tools/sn-exe-strong-name-tool.md)对程序集应用 -Vr 选项。 若要在设计时将程序集加载到 Visual Studio（例如，如果程序集包含应用程序中其他程序集使用的组件），请使用 32 位版本的强名称工具。 这是因为从命令行中运行程序集时，实时 (JIT) 编译器会将程序集编译为 64 位本机代码，而将程序集加载到设计时环境时，会将其编译为 32 位本机代码。  
  
5.  之后（通常在传送前）再通过强名称工具使用 –R 选项，将程序集提交到组织的签名机构以执行实际的强名称签名。  
  
     下面的示例使用 `sgKey.snk` 密钥对为程序集 `myAssembly.dll` 签署了强名称。  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [创建程序集](../../../docs/framework/app-domains/create-assemblies.md)   
 [如何：创建公钥/私钥对](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)   
 [Sn.exe（强名称工具）](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)
