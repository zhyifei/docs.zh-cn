---
title: 延迟为程序集签名
ms.date: 07/31/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87346b28ff98c453949fe31aea4d0ef1880b0095
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296333"
---
# <a name="delay-signing-an-assembly"></a><span data-ttu-id="be960-102">延迟为程序集签名</span><span class="sxs-lookup"><span data-stu-id="be960-102">Delay Signing an Assembly</span></span>
<span data-ttu-id="be960-103">组织可以使用严密保护的密钥对，开发人员无法每天对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="be960-103">An organization can have a closely guarded key pair that developers do not have access to on a daily basis.</span></span> <span data-ttu-id="be960-104">通常情况下公钥可用，但私钥的访问权限仅限于少数几个人。</span><span class="sxs-lookup"><span data-stu-id="be960-104">The public key is often available, but access to the private key is restricted to only a few individuals.</span></span> <span data-ttu-id="be960-105">开发使用强名称的程序集时，每个引用强名称目标程序集的程序集都包含用于向目标程序集赋予强名称的公钥的标记。</span><span class="sxs-lookup"><span data-stu-id="be960-105">When developing assemblies with strong names, each assembly that references the strong-named target assembly contains the token of the public key used to give the target assembly a strong name.</span></span> <span data-ttu-id="be960-106">这要求公钥在开发过程中可用。</span><span class="sxs-lookup"><span data-stu-id="be960-106">This requires that the public key be available during the development process.</span></span>  
  
 <span data-ttu-id="be960-107">生成时，可以使用延迟签名或部分签名，从而在可移植可执行 (PE) 文件中保留用于强名称签名的空间，而将实际签名延迟到之后某个阶段执行（通常在传送程序集之前）。</span><span class="sxs-lookup"><span data-stu-id="be960-107">You can use delayed or partial signing at build time to reserve space in the portable executable (PE) file for the strong name signature, but defer the actual signing until some later stage (typically just before shipping the assembly).</span></span>  
  
 <span data-ttu-id="be960-108">以下步骤概述了延迟程序集签名的过程：</span><span class="sxs-lookup"><span data-stu-id="be960-108">The following steps outline the process to delay sign an assembly:</span></span>  
  
1.  <span data-ttu-id="be960-109">从将执行最终签名的组织处获取密钥对的公钥部分。</span><span class="sxs-lookup"><span data-stu-id="be960-109">Obtain the public key portion of the key pair from the organization that will do the eventual signing.</span></span> <span data-ttu-id="be960-110">此密钥通常是 .snk 文件，可以通过使用 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 提供的[强名称工具 (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) 创建。</span><span class="sxs-lookup"><span data-stu-id="be960-110">Typically this key is in the form of an .snk file, which can be created using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
2.  <span data-ttu-id="be960-111">使用 <xref:System.Reflection> 中的两个自定义属性对程序集的源代码进行注释：</span><span class="sxs-lookup"><span data-stu-id="be960-111">Annotate the source code for the assembly with two custom attributes from <xref:System.Reflection>:</span></span>  
  
    -   <span data-ttu-id="be960-112"><xref:System.Reflection.AssemblyKeyFileAttribute>，将包含公钥的文件名作为参数传递给其构造函数。</span><span class="sxs-lookup"><span data-stu-id="be960-112"><xref:System.Reflection.AssemblyKeyFileAttribute>, which passes the name of the file containing the public key as a parameter to its constructor.</span></span>  
  
    -   <span data-ttu-id="be960-113"><xref:System.Reflection.AssemblyDelaySignAttribute>，通过将 true 作为参数传递给其构造函数来指示正在采用延迟签名。</span><span class="sxs-lookup"><span data-stu-id="be960-113"><xref:System.Reflection.AssemblyDelaySignAttribute>, which indicates that delay signing is being used by passing **true** as a parameter to its constructor.</span></span> <span data-ttu-id="be960-114">例如:</span><span class="sxs-lookup"><span data-stu-id="be960-114">For example:</span></span>  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
         [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
         [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3.  <span data-ttu-id="be960-115">编译器将公钥插入程序集清单，并在 PE 文件中保留用于完整的强名称签名的空间。</span><span class="sxs-lookup"><span data-stu-id="be960-115">The compiler inserts the public key into the assembly manifest and reserves space in the PE file for the full strong name signature.</span></span> <span data-ttu-id="be960-116">生成程序集后，必须存储真正的公钥，这样引用此程序集的其他程序集才能获取该密钥，并将其存储在自己的程序集引用中。</span><span class="sxs-lookup"><span data-stu-id="be960-116">The real public key must be stored while the assembly is built so that other assemblies that reference this assembly can obtain the key to store in their own assembly reference.</span></span>  
  
4.  <span data-ttu-id="be960-117">程序集没有有效的强名称签名，因此必须关闭对此签名的验证。</span><span class="sxs-lookup"><span data-stu-id="be960-117">Because the assembly does not have a valid strong name signature, the verification of that signature must be turned off.</span></span> <span data-ttu-id="be960-118">可配合使用强名称工具和 –Vr 选项来实现此操作。</span><span class="sxs-lookup"><span data-stu-id="be960-118">You can do this by using the **–Vr** option with the Strong Name tool.</span></span>  
  
     <span data-ttu-id="be960-119">以下示例关闭了对名为 `myAssembly.dll` 的程序集的验证。</span><span class="sxs-lookup"><span data-stu-id="be960-119">The following example turns off verification for an assembly called `myAssembly.dll`.</span></span>  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     <span data-ttu-id="be960-120">若要在无法运行强名称工具的平台上（如高级 RISC 计算机 (ARM) 微处理器）关闭验证，请使用 –Vk 选项创建注册表文件。</span><span class="sxs-lookup"><span data-stu-id="be960-120">To turn off verification on platforms where you can’t run the Strong Name tool, such as Advanced RISC Machine (ARM) microprocessors, use the **–Vk** option to create a registry file.</span></span> <span data-ttu-id="be960-121">将该注册表文件导入到要关闭验证的计算机上的注册表中。</span><span class="sxs-lookup"><span data-stu-id="be960-121">Import the registry file into the registry on the computer where you want to turn off verification.</span></span> <span data-ttu-id="be960-122">下面的示例为 `myAssembly.dll` 创建了一个注册表文件。</span><span class="sxs-lookup"><span data-stu-id="be960-122">The following example creates a registry file for `myAssembly.dll`.</span></span>  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     <span data-ttu-id="be960-123">通过 –Vr 或 –Vk 选项，可以选择是否包括 .snk 文件以测试密钥签名。</span><span class="sxs-lookup"><span data-stu-id="be960-123">With either the **–Vr** or **–Vk** option, you can optionally include an .snk file for test key signing.</span></span>  
  
    > [!WARNING]
    > <span data-ttu-id="be960-124">不要依赖于通过强名称实现安全性。</span><span class="sxs-lookup"><span data-stu-id="be960-124">Do not rely on strong names for security.</span></span> <span data-ttu-id="be960-125">它们仅提供唯一的标识。</span><span class="sxs-lookup"><span data-stu-id="be960-125">They provide a unique identity only.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="be960-126">如果在 64 位电脑上使用 Visual Studio 进行开发时使用延迟签名，并且编译“任何 CPU”的程序集，可能需要两次应用 -Vr 选项。</span><span class="sxs-lookup"><span data-stu-id="be960-126">If you use delay signing during development with Visual Studio on a 64-bit computer, and you compile an assembly for **Any CPU**, you might have to apply the **-Vr** option twice.</span></span> <span data-ttu-id="be960-127">（在 Visual Studio 中，“任何 CPU”是平台目标生成属性的一个值；从命令行中编译时，它是默认值。）若要在命令行或文件资源管理器中运行应用程序，请使用 64 位版本的 [Sn.exe（强签名工具）](../../../docs/framework/tools/sn-exe-strong-name-tool.md)对程序集应用 -Vr 选项。</span><span class="sxs-lookup"><span data-stu-id="be960-127">(In Visual Studio, **Any CPU** is a value of the **Platform Target** build property; when you compile from the command line, it is the default.) To run your application from the command line or from File Explorer, use the 64-bit version of the [Sn.exe (Strong Name Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) to apply the **-Vr** option to the assembly.</span></span> <span data-ttu-id="be960-128">若要在设计时将程序集加载到 Visual Studio（例如，如果程序集包含应用程序中其他程序集使用的组件），请使用 32 位版本的强名称工具。</span><span class="sxs-lookup"><span data-stu-id="be960-128">To load the assembly into Visual Studio at design time (for example, if the assembly contains components that are used by other assemblies in your application), use the 32-bit version of the strong-name tool.</span></span> <span data-ttu-id="be960-129">这是因为从命令行中运行程序集时，实时 (JIT) 编译器会将程序集编译为 64 位本机代码，而将程序集加载到设计时环境时，会将其编译为 32 位本机代码。</span><span class="sxs-lookup"><span data-stu-id="be960-129">This is because the just-in-time (JIT) compiler compiles the assembly to 64-bit native code when the assembly is run from the command line, and to 32-bit native code when the assembly is loaded into the design-time environment.</span></span>  
  
5.  <span data-ttu-id="be960-130">之后（通常在传送前）再通过强名称工具使用 –R 选项，将程序集提交到组织的签名机构以执行实际的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="be960-130">Later, usually just before shipping, you submit the assembly to your organization's signing authority for the actual strong name signing using the **–R** option with the Strong Name tool.</span></span>  
  
     <span data-ttu-id="be960-131">下面的示例使用 `sgKey.snk` 密钥对为程序集 `myAssembly.dll` 签署了强名称。</span><span class="sxs-lookup"><span data-stu-id="be960-131">The following example signs an assembly called `myAssembly.dll` with a strong name using the `sgKey.snk` key pair.</span></span>  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="be960-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="be960-132">See Also</span></span>  
- [<span data-ttu-id="be960-133">创建程序集</span><span class="sxs-lookup"><span data-stu-id="be960-133">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
- [<span data-ttu-id="be960-134">如何：创建公钥/私钥对</span><span class="sxs-lookup"><span data-stu-id="be960-134">How to: Create a Public-Private Key Pair</span></span>](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)  
- [<span data-ttu-id="be960-135">Sn.exe（强名称工具）</span><span class="sxs-lookup"><span data-stu-id="be960-135">Sn.exe (Strong Name Tool)</span></span>](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
- [<span data-ttu-id="be960-136">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="be960-136">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
