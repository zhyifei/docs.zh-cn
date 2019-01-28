---
title: -target:library（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 0bdf8d95004ca11e3d6b9b27568f7310a802a28b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542439"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="24b85-102">-target:library（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="24b85-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="24b85-103">-target:library 选项导致编译器创建动态链接库 (DLL) 而不是可执行文件 (EXE)。</span><span class="sxs-lookup"><span data-stu-id="24b85-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24b85-104">语法</span><span class="sxs-lookup"><span data-stu-id="24b85-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="24b85-105">备注</span><span class="sxs-lookup"><span data-stu-id="24b85-105">Remarks</span></span>  
 <span data-ttu-id="24b85-106">将创建具有 .dll 扩展名的 DLL。</span><span class="sxs-lookup"><span data-stu-id="24b85-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="24b85-107">除非使用 [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 选项指定，否则输出文件的名称采用第一个输入文件的名称。</span><span class="sxs-lookup"><span data-stu-id="24b85-107">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="24b85-108">在命令行中进行指定时，-out 或 -target:module 选项上所有文件都用于创建 .dll 文件。</span><span class="sxs-lookup"><span data-stu-id="24b85-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="24b85-109">生成 .dll 文件时，不需要 [ Main ](../../../csharp/programming-guide/main-and-command-args/index.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="24b85-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="24b85-110">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="24b85-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="24b85-111">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="24b85-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="24b85-112">单击“应用程序”属性页。</span><span class="sxs-lookup"><span data-stu-id="24b85-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="24b85-113">修改“输出类型”属性。</span><span class="sxs-lookup"><span data-stu-id="24b85-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="24b85-114">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>。</span><span class="sxs-lookup"><span data-stu-id="24b85-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24b85-115">示例</span><span class="sxs-lookup"><span data-stu-id="24b85-115">Example</span></span>  
 <span data-ttu-id="24b85-116">通过创建 `in.dll` 编译 `in.cs`：</span><span class="sxs-lookup"><span data-stu-id="24b85-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="24b85-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="24b85-117">See also</span></span>

- [<span data-ttu-id="24b85-118">-target（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="24b85-118">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="24b85-119">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="24b85-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
