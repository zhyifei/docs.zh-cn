---
title: "-target:exe（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 515359b7a8a76e20896389b308df34db03f3798d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="-targetexe-c-compiler-options"></a><span data-ttu-id="8aefe-102">-target:exe（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="8aefe-102">-target:exe (C# Compiler Options)</span></span>
<span data-ttu-id="8aefe-103">-target:exe 选项将使编译器创建可执行文件 (EXE) 和控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="8aefe-103">The **-target:exe** option causes the compiler to create an executable (EXE), console application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aefe-104">语法</span><span class="sxs-lookup"><span data-stu-id="8aefe-104">Syntax</span></span>  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a><span data-ttu-id="8aefe-105">备注</span><span class="sxs-lookup"><span data-stu-id="8aefe-105">Remarks</span></span>  
 <span data-ttu-id="8aefe-106">默认情况下，-target:exe 选项有效。</span><span class="sxs-lookup"><span data-stu-id="8aefe-106">The **-target:exe** option is in effect by default.</span></span> <span data-ttu-id="8aefe-107">将创建扩展名为 .exe 的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="8aefe-107">The executable file will be created with the .exe extension.</span></span>  
  
 <span data-ttu-id="8aefe-108">使用 [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) 创建 Windows 程序可执行文件。</span><span class="sxs-lookup"><span data-stu-id="8aefe-108">Use [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) to create a Windows program executable.</span></span>  
  
 <span data-ttu-id="8aefe-109">除非使用 [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 选项进行指定，否则输出文件名采用包含 [Main](../../../csharp/programming-guide/main-and-command-args/index.md) 方法的输入文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8aefe-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="8aefe-110">在命令行中进行指定时，-out 或 -target:module 选项上所有文件都用于创建 .exe 文件</span><span class="sxs-lookup"><span data-stu-id="8aefe-110">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .exe file</span></span>  
  
 <span data-ttu-id="8aefe-111">编译为 .exe 文件的源代码文件中只需要一个 **Main** 方法。</span><span class="sxs-lookup"><span data-stu-id="8aefe-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="8aefe-112">如果代码具有多个附带 Main 方法的类，则可使用 [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) 编译器选项指定包含 Main 方法的类。</span><span class="sxs-lookup"><span data-stu-id="8aefe-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) compiler option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="8aefe-113">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="8aefe-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="8aefe-114">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="8aefe-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="8aefe-115">单击“应用程序”属性页。</span><span class="sxs-lookup"><span data-stu-id="8aefe-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="8aefe-116">修改“输出类型”属性。</span><span class="sxs-lookup"><span data-stu-id="8aefe-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="8aefe-117">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>。</span><span class="sxs-lookup"><span data-stu-id="8aefe-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aefe-118">示例</span><span class="sxs-lookup"><span data-stu-id="8aefe-118">Example</span></span>  
 <span data-ttu-id="8aefe-119">以下每个命令行都将编译 `in.cs` 并创建 `in.exe`：</span><span class="sxs-lookup"><span data-stu-id="8aefe-119">Each of the following command lines will compile `in.cs`, creating `in.exe`:</span></span>  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8aefe-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8aefe-120">See Also</span></span>  
 [<span data-ttu-id="8aefe-121">-target（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="8aefe-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="8aefe-122">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="8aefe-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
