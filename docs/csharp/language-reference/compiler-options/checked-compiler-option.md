---
title: -checked（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: 4ed8467b0e1923aedf38edfd4a25414cbcb88b7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218307"
---
# <a name="-checked-c-compiler-options"></a><span data-ttu-id="1e508-102">-checked（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="1e508-102">-checked (C# Compiler Options)</span></span>
<span data-ttu-id="1e508-103">-checked 选项指定，不在 [checked](../../../csharp/language-reference/keywords/checked.md) 或 [unchecked](../../../csharp/language-reference/keywords/unchecked.md) 关键字的范围内、并且产生的值超出数据类型范围的整数算法语句是否将导致运行时异常。</span><span class="sxs-lookup"><span data-stu-id="1e508-103">The **-checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../../../csharp/language-reference/keywords/checked.md) or [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e508-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e508-104">Syntax</span></span>  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="1e508-105">备注</span><span class="sxs-lookup"><span data-stu-id="1e508-105">Remarks</span></span>  
 <span data-ttu-id="1e508-106">`checked` 或 `unchecked` 关键字范围内的整数算法语句不受 -checked 选项的影响。</span><span class="sxs-lookup"><span data-stu-id="1e508-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **-checked** option.</span></span>  
  
 <span data-ttu-id="1e508-107">如果不在 `checked` 或 `unchecked` 关键字范围内的整数算法语句产生的值超出数据类型范围，并且编译中使用了 -checked+ (-checked)，则该语句将在运行时导致异常。</span><span class="sxs-lookup"><span data-stu-id="1e508-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **-checked+** (**-checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="1e508-108">如果编译中使用的是 -checked-，则该语句在运行时不会导致异常。</span><span class="sxs-lookup"><span data-stu-id="1e508-108">If **-checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="1e508-109">该选项的默认值为 -checked-。</span><span class="sxs-lookup"><span data-stu-id="1e508-109">The default value for this option is **-checked-**.</span></span> <span data-ttu-id="1e508-110">使用 -checked- 的一个方案是生成大型应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e508-110">One scenario for using **-checked-** is in building large applications.</span></span> <span data-ttu-id="1e508-111">有时使用自动化工具生成此类应用程序，这种工具可以将 -checked 自动设置为 +。</span><span class="sxs-lookup"><span data-stu-id="1e508-111">Sometimes automated tools are used to build such applications, and such a tool might automatically set **-checked** to +.</span></span> <span data-ttu-id="1e508-112">可通过指定 -checked- 替代工具的全局默认值。</span><span class="sxs-lookup"><span data-stu-id="1e508-112">You can override the tool's global default by specifying **-checked-**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1e508-113">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="1e508-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="1e508-114">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="1e508-114">Open the project's **Properties** page.</span></span> <span data-ttu-id="1e508-115">有关详细信息，请参阅 [“项目设计器”->“生成”页 (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)。</span><span class="sxs-lookup"><span data-stu-id="1e508-115">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="1e508-116">单击“生成”属性页。</span><span class="sxs-lookup"><span data-stu-id="1e508-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="1e508-117">单击“高级”按钮。</span><span class="sxs-lookup"><span data-stu-id="1e508-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="1e508-118">修改“检查算术溢出/下溢”属性。</span><span class="sxs-lookup"><span data-stu-id="1e508-118">Modify the **Check for arithmetic overflow/underflow** property.</span></span>  
  
 <span data-ttu-id="1e508-119">要以编程方式访问此编译器选项，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>。</span><span class="sxs-lookup"><span data-stu-id="1e508-119">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e508-120">示例</span><span class="sxs-lookup"><span data-stu-id="1e508-120">Example</span></span>  
 <span data-ttu-id="1e508-121">以下命令编译 `t2.cs`。</span><span class="sxs-lookup"><span data-stu-id="1e508-121">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="1e508-122">命令中 `-checked` 的使用指定，任何不在 `checked` 或 `unchecked` 关键字范围内以及导致数据类型以外值的结果的文件中的整数算术语句，会在运行时引发异常。</span><span class="sxs-lookup"><span data-stu-id="1e508-122">The use of `-checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e508-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e508-123">See Also</span></span>  
 [<span data-ttu-id="1e508-124">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="1e508-124">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="1e508-125">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="1e508-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
