---
title: "-optimize（C# 编译器选项）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /optimize
dev_langs:
- CSharp
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 75a2b65c159e9adb0103765468182919ed6b0a23
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="optimize-c-compiler-options"></a><span data-ttu-id="a9538-102">/optimize（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="a9538-102">/optimize (C# Compiler Options)</span></span>
<span data-ttu-id="a9538-103">/optimize 选项启用或禁用编译器执行的优化，使输出文件更小、更快、更有效。</span><span class="sxs-lookup"><span data-stu-id="a9538-103">The **/optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9538-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9538-104">Syntax</span></span>  
  
```console  
/optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="a9538-105">备注</span><span class="sxs-lookup"><span data-stu-id="a9538-105">Remarks</span></span>  
 <span data-ttu-id="a9538-106">/optimize 还指示公共语言运行时在运行时优化代码。</span><span class="sxs-lookup"><span data-stu-id="a9538-106">**/optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="a9538-107">默认情况下，禁用优化。</span><span class="sxs-lookup"><span data-stu-id="a9538-107">By default, optimizations are disabled.</span></span> <span data-ttu-id="a9538-108">指定 /optimize+ 可启用优化。</span><span class="sxs-lookup"><span data-stu-id="a9538-108">Specify **/optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="a9538-109">生成程序集使用的模块时，请使用与程序集相同的 /optimize 设置。</span><span class="sxs-lookup"><span data-stu-id="a9538-109">When building a module to be used by an assembly, use the same **/optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="a9538-110">/o 是 /optimize 的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="a9538-110">**/o** is the short form of **/optimize**.</span></span>  
  
 <span data-ttu-id="a9538-111">可以将 /optimize 和 [/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) 选项组合使用。</span><span class="sxs-lookup"><span data-stu-id="a9538-111">It is possible to combine the **/optimize** and [/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a9538-112">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="a9538-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="a9538-113">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="a9538-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="a9538-114">单击“生成”属性页。</span><span class="sxs-lookup"><span data-stu-id="a9538-114">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="a9538-115">修改“优化代码”属性。</span><span class="sxs-lookup"><span data-stu-id="a9538-115">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="a9538-116">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>。</span><span class="sxs-lookup"><span data-stu-id="a9538-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9538-117">示例</span><span class="sxs-lookup"><span data-stu-id="a9538-117">Example</span></span>  
 <span data-ttu-id="a9538-118">编译 `t2.cs` 并启用编译器优化：</span><span class="sxs-lookup"><span data-stu-id="a9538-118">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9538-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9538-119">See Also</span></span>  
 <span data-ttu-id="a9538-120">[（C# 编译器选项）](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9538-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="a9538-121">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="a9538-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

