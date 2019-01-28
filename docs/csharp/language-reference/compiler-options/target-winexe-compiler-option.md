---
title: -target:winexe（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: affb06c62baa7f53e46e1d66b522e9ce9e74d976
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666054"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="5b14c-102">-target:winexe（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="5b14c-102">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="5b14c-103">-target:winexe 选项使编译器创建可执行文件 (EXE) 和 Windows 程序。</span><span class="sxs-lookup"><span data-stu-id="5b14c-103">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b14c-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b14c-104">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="5b14c-105">备注</span><span class="sxs-lookup"><span data-stu-id="5b14c-105">Remarks</span></span>  
 <span data-ttu-id="5b14c-106">将创建扩展名为 .exe 的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="5b14c-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="5b14c-107">Windows 程序从 .NET Framework 库或使用 Win32 API 提供用户界面。</span><span class="sxs-lookup"><span data-stu-id="5b14c-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Win32 APIs.</span></span>  
  
 <span data-ttu-id="5b14c-108">使用 [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) 创建控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="5b14c-108">Use [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="5b14c-109">除非使用 [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 选项进行指定，否则输出文件名采用包含 [Main](../../../csharp/programming-guide/main-and-command-args/index.md) 方法的输入文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5b14c-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="5b14c-110">在命令行中进行指定时，直到下一个 -out 或 [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 选项为止的所有文件均用于创建 Windows 程序。</span><span class="sxs-lookup"><span data-stu-id="5b14c-110">When specified at the command line, all files until the next **-out** or [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="5b14c-111">编译为 .exe 文件的源代码文件中只需要一个 **Main** 方法。</span><span class="sxs-lookup"><span data-stu-id="5b14c-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="5b14c-112">如果代码具有多个附带 Main 方法的类，则可使用 [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) 选项指定包含 Main 方法的类。</span><span class="sxs-lookup"><span data-stu-id="5b14c-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5b14c-113">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="5b14c-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="5b14c-114">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="5b14c-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="5b14c-115">单击“应用程序”属性页。</span><span class="sxs-lookup"><span data-stu-id="5b14c-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="5b14c-116">修改“输出类型”属性。</span><span class="sxs-lookup"><span data-stu-id="5b14c-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="5b14c-117">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>。</span><span class="sxs-lookup"><span data-stu-id="5b14c-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b14c-118">示例</span><span class="sxs-lookup"><span data-stu-id="5b14c-118">Example</span></span>  
 <span data-ttu-id="5b14c-119">将 `in.cs` 编译为 Windows 程序：</span><span class="sxs-lookup"><span data-stu-id="5b14c-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b14c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b14c-120">See also</span></span>

- [<span data-ttu-id="5b14c-121">-target（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="5b14c-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="5b14c-122">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="5b14c-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
