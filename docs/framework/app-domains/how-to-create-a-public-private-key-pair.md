---
title: "如何：创建公钥/私钥对"
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
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 772bcae9c3467553e4ca90989a82798155ee034c
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-public-private-key-pair"></a><span data-ttu-id="c1541-102">如何：创建公钥/私钥对</span><span class="sxs-lookup"><span data-stu-id="c1541-102">How to: Create a Public-Private Key Pair</span></span>
<span data-ttu-id="c1541-103">若要使用强名称为程序集签名，必须具有公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="c1541-103">To sign an assembly with a strong name, you must have a public/private key pair.</span></span> <span data-ttu-id="c1541-104">这一对加密的公钥和私钥用于在编译过程中创建强名称程序集。</span><span class="sxs-lookup"><span data-stu-id="c1541-104">This public and private cryptographic key pair is used during compilation to create a strong-named assembly.</span></span> <span data-ttu-id="c1541-105">可以使用[强名称工具 (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 创建密钥对。</span><span class="sxs-lookup"><span data-stu-id="c1541-105">You can create a key pair using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).</span></span> <span data-ttu-id="c1541-106">密钥对文件通常具有 .snk 扩展名。</span><span class="sxs-lookup"><span data-stu-id="c1541-106">Key pair files usually have an .snk extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1541-107">在 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 中，C# 和 Visual Basic 项目属性页包括一个“签名”选项卡，通过该选项卡，无需使用 Sn.exe 即可选择现有密钥文件或生成新密钥文件。</span><span class="sxs-lookup"><span data-stu-id="c1541-107">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], the C# and Visual Basic project property pages include a **Signing** tab that enables you to select existing key files or to generate new key files without using Sn.exe.</span></span> <span data-ttu-id="c1541-108">在 Visual C++ 中，可以在“属性页”窗口的“配置属性”部分的“链接器”部分中，在“高级”属性页中指定现有密钥文件的位置。</span><span class="sxs-lookup"><span data-stu-id="c1541-108">In Visual C++, you can specify the location of an existing key file in the **Advanced** property page in the **Linker** section of the **Configuration Properties** section of the **Property Pages** window.</span></span> <span data-ttu-id="c1541-109">从 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 开始，使用 <xref:System.Reflection.AssemblyKeyFileAttribute> 特性标识密钥文件对的方法已过时。</span><span class="sxs-lookup"><span data-stu-id="c1541-109">The use of the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute to identify key file pairs has been made obsolete beginning with [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span></span>  
  
### <a name="to-create-a-key-pair"></a><span data-ttu-id="c1541-110">创建密钥对</span><span class="sxs-lookup"><span data-stu-id="c1541-110">To create a key pair</span></span>  
  
1.  <span data-ttu-id="c1541-111">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c1541-111">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="c1541-112">**sn –k** \<*file name*></span><span class="sxs-lookup"><span data-stu-id="c1541-112">**sn –k** \<*file name*></span></span>  
  
     <span data-ttu-id="c1541-113">此命令中，“文件名”是包含密钥对的输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c1541-113">In this command, *file name* is the name of the output file containing the key pair.</span></span>  
  
 <span data-ttu-id="c1541-114">以下示例创建名为 `sgKey.snk` 的密钥对。</span><span class="sxs-lookup"><span data-stu-id="c1541-114">The following example creates a key pair called `sgKey.snk`.</span></span>  
  
```  
sn -k sgKey.snk  
```  
  
 <span data-ttu-id="c1541-115">如果打算延迟为程序集签名并控制整个密钥对（密钥对不太可能在测试方案之外），可使用以下命令生成密钥对，然后从中将公钥提取到一个单独的文件中。</span><span class="sxs-lookup"><span data-stu-id="c1541-115">If you intend to delay sign an assembly and you control the whole key pair (which is unlikely outside test scenarios), you can use the following commands to generate a key pair and then extract the public key from it into a separate file.</span></span> <span data-ttu-id="c1541-116">首先，创建密钥对：</span><span class="sxs-lookup"><span data-stu-id="c1541-116">First, create the key pair:</span></span>  
  
```  
sn -k keypair.snk  
```  
  
 <span data-ttu-id="c1541-117">接下来，从密钥对中提取公钥，并将其复制到一个单独的文件中：</span><span class="sxs-lookup"><span data-stu-id="c1541-117">Next, extract the public key from the key pair and copy it to a separate file:</span></span>  
  
```  
sn -p keypair.snk public.snk  
```  
  
 <span data-ttu-id="c1541-118">创建密钥对之后，必须将文件放在强名称签名工具可以找到的位置。</span><span class="sxs-lookup"><span data-stu-id="c1541-118">Once you create the key pair, you must put the file where the strong name signing tools can find it.</span></span>  
  
 <span data-ttu-id="c1541-119">当使用强名称对程序集进行签名时，[程序集链接器 (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) 查找与当前目录和输出目录相关的密钥文件。</span><span class="sxs-lookup"><span data-stu-id="c1541-119">When signing an assembly with a strong name, the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) looks for the key file relative to the current directory and to the output directory.</span></span> <span data-ttu-id="c1541-120">当使用命令行编译器时，只需将密钥复制到包含代码模块的当前目录即可。</span><span class="sxs-lookup"><span data-stu-id="c1541-120">When using command-line compilers, you can simply copy the key to the current directory containing your code modules.</span></span>  
  
 <span data-ttu-id="c1541-121">如果使用 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 的早期版本，且在项目属性中没有“签名”选项卡，建议将符合后列条件的项目目录作为密钥文件位置，该目录应按以下所示指定文件特性：</span><span class="sxs-lookup"><span data-stu-id="c1541-121">If you are using an earlier version of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that does not have a **Signing** tab in the project properties, the recommended key file location is the project directory with the file attribute specified as follows:</span></span>  
  
 <span data-ttu-id="c1541-122">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span><span class="sxs-lookup"><span data-stu-id="c1541-122">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1541-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1541-123">See Also</span></span>  
 [<span data-ttu-id="c1541-124">创建和使用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="c1541-124">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

