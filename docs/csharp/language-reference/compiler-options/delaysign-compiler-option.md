---
title: -delaysign（C# 编译器选项）
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 105f564d40799c1c006caf8b59d6199dbd8e9318
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400191"
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="9baa5-102">-delaysign（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="9baa5-102">-delaysign (C# Compiler Options)</span></span>

<span data-ttu-id="9baa5-103">此选项会使编译器在输出文件中保留空间，以便以后添加数字签名。</span><span class="sxs-lookup"><span data-stu-id="9baa5-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>

## <a name="syntax"></a><span data-ttu-id="9baa5-104">语法</span><span class="sxs-lookup"><span data-stu-id="9baa5-104">Syntax</span></span>

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a><span data-ttu-id="9baa5-105">自变量</span><span class="sxs-lookup"><span data-stu-id="9baa5-105">Arguments</span></span>

<span data-ttu-id="9baa5-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9baa5-106">`+` &#124; `-`</span></span>

<span data-ttu-id="9baa5-107">如果需要完全签名的程序集，请使用 -delaysign-。</span><span class="sxs-lookup"><span data-stu-id="9baa5-107">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="9baa5-108">如果仅需要将公钥置于程序集中，则使用 -delaysign+。</span><span class="sxs-lookup"><span data-stu-id="9baa5-108">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="9baa5-109">默认值为 -delaysign-。</span><span class="sxs-lookup"><span data-stu-id="9baa5-109">The default is **-delaysign-**.</span></span>

## <a name="remarks"></a><span data-ttu-id="9baa5-110">备注</span><span class="sxs-lookup"><span data-stu-id="9baa5-110">Remarks</span></span>

<span data-ttu-id="9baa5-111">除非与 [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) 或 [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) 一同使用，否则 -delaysign 选项将不起作用。</span><span class="sxs-lookup"><span data-stu-id="9baa5-111">The **-delaysign** option has no effect unless used with [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) or [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span>

<span data-ttu-id="9baa5-112">-Delaysign 和 -publicsign 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="9baa5-112">The **-delaysign** and **-publicsign** options are mutually exclusive.</span></span>

<span data-ttu-id="9baa5-113">在请求完全签名的程序集时，编译器会对包含清单（程序集元数据）的文件进行哈希处理，并使用私钥对哈希进行签名。</span><span class="sxs-lookup"><span data-stu-id="9baa5-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="9baa5-114">该操作创建存储在包含清单的文件中的数字签名。</span><span class="sxs-lookup"><span data-stu-id="9baa5-114">That operation creates a digital signature which is stored in the file that contains the manifest.</span></span> <span data-ttu-id="9baa5-115">在对程序集延迟签名时，编译器不会计算和存储签名，而只是在文件中保留空间以便稍后可添加签名。</span><span class="sxs-lookup"><span data-stu-id="9baa5-115">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="9baa5-116">例如，使用 -delaysign+ 可允许测试人员将程序集放入全局缓存中。</span><span class="sxs-lookup"><span data-stu-id="9baa5-116">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="9baa5-117">测试完成后，可使用[程序集链接器](../../../framework/tools/al-exe-assembly-linker.md)实用工具将私钥置于程序集中，对程序集进行完全签名。</span><span class="sxs-lookup"><span data-stu-id="9baa5-117">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>

<span data-ttu-id="9baa5-118">有关详细信息，请参阅[创建和使用具有强名称的程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)和[延迟为程序集签名](../../../framework/app-domains/delay-sign-assembly.md)。</span><span class="sxs-lookup"><span data-stu-id="9baa5-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="9baa5-119">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="9baa5-119">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="9baa5-120">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="9baa5-120">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="9baa5-121">修改“仅延迟签名”属性。</span><span class="sxs-lookup"><span data-stu-id="9baa5-121">Modify the **Delay sign only** property.</span></span>

<span data-ttu-id="9baa5-122">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>。</span><span class="sxs-lookup"><span data-stu-id="9baa5-122">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="9baa5-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9baa5-123">See Also</span></span>

- [<span data-ttu-id="9baa5-124">C# -publicsign 选项</span><span class="sxs-lookup"><span data-stu-id="9baa5-124">C# -publicsign option</span></span>](publicsign-compiler-option.md)  
- [<span data-ttu-id="9baa5-125">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="9baa5-125">C# Compiler Options</span></span>](index.md)  
- [<span data-ttu-id="9baa5-126">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="9baa5-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
