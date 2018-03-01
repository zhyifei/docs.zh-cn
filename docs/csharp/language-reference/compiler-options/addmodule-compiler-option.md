---
title: "-addmodule（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: db440b58862e372e443c9c51961b0c3cc2dd211e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="8a1a2-102">-addmodule（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="8a1a2-102">-addmodule (C# Compiler Options)</span></span>
<span data-ttu-id="8a1a2-103">此选项将添加一个模块，该模块通过将 target: module 切换到当前编译进行创建。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-103">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a1a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="8a1a2-104">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8a1a2-105">自变量</span><span class="sxs-lookup"><span data-stu-id="8a1a2-105">Arguments</span></span>  
 <span data-ttu-id="8a1a2-106">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="8a1a2-106">`file`, `file2`</span></span>  
 <span data-ttu-id="8a1a2-107">包含元数据的输出文件。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-107">An output file that contains metadata.</span></span> <span data-ttu-id="8a1a2-108">该文件不能包含程序集清单。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-108">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="8a1a2-109">若要导入多个文件，请用逗号或分号将文件名隔开。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-109">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a1a2-110">备注</span><span class="sxs-lookup"><span data-stu-id="8a1a2-110">Remarks</span></span>  
 <span data-ttu-id="8a1a2-111">通过 -addmodule 添加的所有模块在运行时必须位于与输出文件相同的目录中。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-111">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="8a1a2-112">也就是说，在编译时可在任何目录中指定模块，但在运行时该模块必须位于应用程序目录中。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-112">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="8a1a2-113">如果在运行时该模块不位于应用程序目录中，则将出现 <xref:System.TypeLoadException>。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-113">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="8a1a2-114">`file` 不能包含程序集。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-114">`file` cannot contain an assembly.</span></span> <span data-ttu-id="8a1a2-115">例如，如果输出文件使用 [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) 创建，其元数据可通过 -addmodule 导入。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-115">For example, if the output file was created with [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="8a1a2-116">如果输出文件通过使用 -target 选项而不是 -target:module 创建，则其元数据不能通过 -addmodule 导入，但可以通过 [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 导入。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-116">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="8a1a2-117">此编译器选项在 Visual Studio 中不可用；项目不能引用模块。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-117">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="8a1a2-118">此外，不能以编程方式更改此编译器选项。</span><span class="sxs-lookup"><span data-stu-id="8a1a2-118">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a1a2-119">示例</span><span class="sxs-lookup"><span data-stu-id="8a1a2-119">Example</span></span>  
 <span data-ttu-id="8a1a2-120">编译源文件 `input.cs`，并从 `metad1.netmodule` 和 `metad2.netmodule` 添加元数据以生成 `out.exe`：</span><span class="sxs-lookup"><span data-stu-id="8a1a2-120">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a1a2-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a1a2-121">See Also</span></span>  
 [<span data-ttu-id="8a1a2-122">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="8a1a2-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="8a1a2-123">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="8a1a2-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="8a1a2-124">多文件程序集</span><span class="sxs-lookup"><span data-stu-id="8a1a2-124">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)  
 [<span data-ttu-id="8a1a2-125">如何：生成多文件程序集</span><span class="sxs-lookup"><span data-stu-id="8a1a2-125">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
