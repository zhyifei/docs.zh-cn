---
title: -target:module（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: 7cc0e48a7a4a3ec3f28c89e80fadf6aa7e1130f2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43393121"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="5cb91-102">-target:module（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="5cb91-102">-target:module (C# Compiler Options)</span></span>
<span data-ttu-id="5cb91-103">此选项会导致编译器不生成程序集清单。</span><span class="sxs-lookup"><span data-stu-id="5cb91-103">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb91-104">语法</span><span class="sxs-lookup"><span data-stu-id="5cb91-104">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="5cb91-105">备注</span><span class="sxs-lookup"><span data-stu-id="5cb91-105">Remarks</span></span>  
 <span data-ttu-id="5cb91-106">默认情况下，使用此选项编译时所创建的输出文件具有扩展名 .netmodule。</span><span class="sxs-lookup"><span data-stu-id="5cb91-106">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="5cb91-107">.NET Framework 公共语言运行时无法加载不含程序集清单的文件。</span><span class="sxs-lookup"><span data-stu-id="5cb91-107">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="5cb91-108">但是，此类文件可以通过 [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) 合并到程序集的程序集清单中。</span><span class="sxs-lookup"><span data-stu-id="5cb91-108">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="5cb91-109">如果在一次编译中创建了多个模块，某个模块中的[内部](../../../csharp/language-reference/keywords/internal.md)类型将适用于编译中的其他模块。</span><span class="sxs-lookup"><span data-stu-id="5cb91-109">If more than one module is created in a single compilation, [internal](../../../csharp/language-reference/keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="5cb91-110">如果一个模块中的代码引用另一模块中的 `internal` 类型，则两个模块必须通过 -addmodule 合并到一个程序集清单中。</span><span class="sxs-lookup"><span data-stu-id="5cb91-110">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="5cb91-111">Visual Studio 开发环境中不支持创建模块。</span><span class="sxs-lookup"><span data-stu-id="5cb91-111">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="5cb91-112">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>。</span><span class="sxs-lookup"><span data-stu-id="5cb91-112">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cb91-113">示例</span><span class="sxs-lookup"><span data-stu-id="5cb91-113">Example</span></span>  
 <span data-ttu-id="5cb91-114">通过创建 `in.netmodule` 编译 `in.cs`：</span><span class="sxs-lookup"><span data-stu-id="5cb91-114">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cb91-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cb91-115">See Also</span></span>  

- [<span data-ttu-id="5cb91-116">-target（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="5cb91-116">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
- [<span data-ttu-id="5cb91-117">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="5cb91-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
