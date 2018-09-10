---
title: -target（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
ms.openlocfilehash: a337ecbc614ff40eda42fc5263dbb52aa92b905f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185727"
---
# <a name="-target-c-compiler-options"></a><span data-ttu-id="06594-102">-target（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="06594-102">-target (C# Compiler Options)</span></span>
<span data-ttu-id="06594-103">-target 编译器选项可指定为以下四种形式之一：</span><span class="sxs-lookup"><span data-stu-id="06594-103">The **-target** compiler option can be specified in one of four forms:</span></span>  
  
 [<span data-ttu-id="06594-104">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="06594-104">-target:appcontainerexe</span></span>](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="06594-105">创建 [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)]应用的 .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="06594-105">To create an .exe file for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [<span data-ttu-id="06594-106">/target:exe</span><span class="sxs-lookup"><span data-stu-id="06594-106">-target:exe</span></span>](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 <span data-ttu-id="06594-107">创建 .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="06594-107">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="06594-108">/target:library</span><span class="sxs-lookup"><span data-stu-id="06594-108">-target:library</span></span>](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 <span data-ttu-id="06594-109">创建代码库。</span><span class="sxs-lookup"><span data-stu-id="06594-109">To create a code library.</span></span>  
  
 [<span data-ttu-id="06594-110">/target:module</span><span class="sxs-lookup"><span data-stu-id="06594-110">-target:module</span></span>](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 <span data-ttu-id="06594-111">创建模块。</span><span class="sxs-lookup"><span data-stu-id="06594-111">To create a module.</span></span>  
  
 [<span data-ttu-id="06594-112">/target:winexe</span><span class="sxs-lookup"><span data-stu-id="06594-112">-target:winexe</span></span>](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 <span data-ttu-id="06594-113">创建 Windows 程序。</span><span class="sxs-lookup"><span data-stu-id="06594-113">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="06594-114">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="06594-114">-target:winmdobj</span></span>](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 <span data-ttu-id="06594-115">创建一个 .winmdobj 中间文件。</span><span class="sxs-lookup"><span data-stu-id="06594-115">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="06594-116">如果不指定 -target:module，-target 会将 .NET Framework 程序集清单放入输出文件中。</span><span class="sxs-lookup"><span data-stu-id="06594-116">Unless you specify **-target:module**, **-target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="06594-117">有关详细信息，请参阅[公共语言运行时中的程序集](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md)和[公共特性](../../programming-guide/concepts/attributes/common-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="06594-117">For more information, see [Assemblies in the Common Language Runtime](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) and [Common Attributes](../../programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
 <span data-ttu-id="06594-118">程序集清单放置在编译中的第一个 .exe 输出文件中，如果没有 .exe 输出文件，会放置在第一个 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="06594-118">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="06594-119">例如，在以下的命令行中，清单将放置在 `1.exe` 中：</span><span class="sxs-lookup"><span data-stu-id="06594-119">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="06594-120">编译器每次编译只创建一个程序集清单。</span><span class="sxs-lookup"><span data-stu-id="06594-120">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="06594-121">关于编译中所有文件的信息都放在程序集清单中。</span><span class="sxs-lookup"><span data-stu-id="06594-121">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="06594-122">除用 -target:module 创建的文件之外，所有输出文件都可包含程序集清单。</span><span class="sxs-lookup"><span data-stu-id="06594-122">All output files except those created with **-target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="06594-123">在命令行生成多个输出文件时，只能创建一个程序集清单，且该清单必须放置在命令行上指定的第一个输出文件中。</span><span class="sxs-lookup"><span data-stu-id="06594-123">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="06594-124">无论第一个输出文件是什么（-target:exe、-target:winexe、-target:library 或 -target:module），在同一编译中生成的任何其他输出文件都必须是模块 (-target:module)。</span><span class="sxs-lookup"><span data-stu-id="06594-124">No matter what the first output file is (**-target:exe**, **-target:winexe**, **-target:library** or **-target:module**), any other output files produced in the same compilation must be modules (**-target:module**).</span></span>  
  
 <span data-ttu-id="06594-125">如果创建了一个程序集，则可以用 <xref:System.CLSCompliantAttribute> 属性指示全部或部分代码是符合 CLS 的。</span><span class="sxs-lookup"><span data-stu-id="06594-125">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="06594-126">有关如何以编程方式设置此编译器选项的详细信息，请参阅 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>。</span><span class="sxs-lookup"><span data-stu-id="06594-126">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06594-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="06594-127">See Also</span></span>  

- [<span data-ttu-id="06594-128">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="06594-128">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="06594-129">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="06594-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
- [<span data-ttu-id="06594-130">-subsystemversion（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="06594-130">-subsystemversion (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)
