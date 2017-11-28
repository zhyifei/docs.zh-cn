---
title: "-delaysign（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 62f76747a29a90562706dff5fa742316c5b99b74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="delaysign-c-compiler-options"></a><span data-ttu-id="0b801-102">/delaysign（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="0b801-102">/delaysign (C# Compiler Options)</span></span>
<span data-ttu-id="0b801-103">此选项会使编译器在输出文件中保留空间，以便以后添加数字签名。</span><span class="sxs-lookup"><span data-stu-id="0b801-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b801-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b801-104">Syntax</span></span>  
  
```console  
/delaysign[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b801-105">参数</span><span class="sxs-lookup"><span data-stu-id="0b801-105">Arguments</span></span>  
 <span data-ttu-id="0b801-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0b801-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="0b801-107">如果需要完全签名的程序集，请使用 **/delaysign-**。</span><span class="sxs-lookup"><span data-stu-id="0b801-107">Use **/delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="0b801-108">如果仅需要将公钥置于程序集中，则使用 /delaysign+。</span><span class="sxs-lookup"><span data-stu-id="0b801-108">Use **/delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="0b801-109">默认值为 **/delaysign-**。</span><span class="sxs-lookup"><span data-stu-id="0b801-109">The default is **/delaysign-**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b801-110">备注</span><span class="sxs-lookup"><span data-stu-id="0b801-110">Remarks</span></span>  
 <span data-ttu-id="0b801-111">除非与 [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) 或 [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) 一同使用，否则 /delaysign 选项将不起作用。</span><span class="sxs-lookup"><span data-stu-id="0b801-111">The **/delaysign** option has no effect unless used with [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) or [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span>  
  
 <span data-ttu-id="0b801-112">在请求完全签名的程序集时，编译器会对包含清单（程序集元数据）的文件进行哈希处理，并使用私钥对哈希进行签名。</span><span class="sxs-lookup"><span data-stu-id="0b801-112">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="0b801-113">产生的数字签名存储在包含清单的文件中。</span><span class="sxs-lookup"><span data-stu-id="0b801-113">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="0b801-114">在对程序集延迟签名时，编译器不会计算和存储签名，而只是在文件中保留空间以便稍后可添加签名。</span><span class="sxs-lookup"><span data-stu-id="0b801-114">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="0b801-115">例如，使用 /delaysign+ 可允许测试人员将程序集放入全局缓存中。</span><span class="sxs-lookup"><span data-stu-id="0b801-115">For example, using **/delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="0b801-116">测试完成后，可使用[程序集链接器](../../../framework/tools/al-exe-assembly-linker.md)实用工具将私钥置于程序集中，对程序集进行完全签名。</span><span class="sxs-lookup"><span data-stu-id="0b801-116">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>  
  
 <span data-ttu-id="0b801-117">有关详细信息，请参阅[创建和使用具有强名称的程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)和[延迟为程序集签名](../../../framework/app-domains/delay-sign-assembly.md)。</span><span class="sxs-lookup"><span data-stu-id="0b801-117">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0b801-118">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="0b801-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="0b801-119">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="0b801-119">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="0b801-120">修改“仅延迟签名”属性。</span><span class="sxs-lookup"><span data-stu-id="0b801-120">Modify the **Delay sign only** property.</span></span>  
  
 <span data-ttu-id="0b801-121">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>。</span><span class="sxs-lookup"><span data-stu-id="0b801-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b801-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b801-122">See Also</span></span>  
 [<span data-ttu-id="0b801-123">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="0b801-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="0b801-124">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="0b801-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
