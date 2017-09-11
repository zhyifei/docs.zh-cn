---
title: "/optioninfer |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioninfer
dev_langs:
- VB
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4bcc35da2a255ca75805c8a918027d2ccb61b154
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="optioninfer"></a><span data-ttu-id="52d07-102">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="52d07-102">/optioninfer</span></span>
<span data-ttu-id="52d07-103">允许在变量声明中使用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="52d07-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d07-104">语法</span><span class="sxs-lookup"><span data-stu-id="52d07-104">Syntax</span></span>  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="52d07-105">参数</span><span class="sxs-lookup"><span data-stu-id="52d07-105">Arguments</span></span>  
  
|<span data-ttu-id="52d07-106">术语</span><span class="sxs-lookup"><span data-stu-id="52d07-106">Term</span></span>|<span data-ttu-id="52d07-107">定义</span><span class="sxs-lookup"><span data-stu-id="52d07-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="52d07-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="52d07-108">`+` &#124; `-`</span></span>|<span data-ttu-id="52d07-109">可选。</span><span class="sxs-lookup"><span data-stu-id="52d07-109">Optional.</span></span> <span data-ttu-id="52d07-110">指定 `/optioninfer+` 来启用局部类型推理，或指定 `/optioninfer-` 来阻止它。</span><span class="sxs-lookup"><span data-stu-id="52d07-110">Specify `/optioninfer+` to enable local type inference, or `/optioninfer-` to block it.</span></span> <span data-ttu-id="52d07-111">没有指定值的 `/optioninfer` 选项等同于 `/optioninfer+`。</span><span class="sxs-lookup"><span data-stu-id="52d07-111">The `/optioninfer` option, with no value specified, is the same as `/optioninfer+`.</span></span> <span data-ttu-id="52d07-112">不存在 `/optioninfer` 切换时，默认值也是 `/optioninfer+`。</span><span class="sxs-lookup"><span data-stu-id="52d07-112">The default value when the `/optioninfer` switch is not present is also `/optioninfer+`.</span></span> <span data-ttu-id="52d07-113">在 Vbc.rsp 响应文件中设置了默认值。</span><span class="sxs-lookup"><span data-stu-id="52d07-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="52d07-114">你可使用 `/noconfig` 选项来保留编译器的内部默认值(而非在 vbc.rsp 中指定的那些值）。</span><span class="sxs-lookup"><span data-stu-id="52d07-114">You can use the `/noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="52d07-115">此选项默认的编译器是 `/optioninfer-`。</span><span class="sxs-lookup"><span data-stu-id="52d07-115">The compiler default for this option is `/optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52d07-116">备注</span><span class="sxs-lookup"><span data-stu-id="52d07-116">Remarks</span></span>  
 <span data-ttu-id="52d07-117">如果源代码文件包含[Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)，语句将覆盖`/optioninfer`命令行编译器设置。</span><span class="sxs-lookup"><span data-stu-id="52d07-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `/optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="52d07-118">若要在 Visual Studio IDE 中设置 /optioninfer</span><span class="sxs-lookup"><span data-stu-id="52d07-118">To set /optioninfer in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="52d07-119">选择一个项目中的**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="52d07-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="52d07-120">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="52d07-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="52d07-121">有关详细信息，请参阅[NIB︰ 使用项目设计器管理项目属性](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e)。</span><span class="sxs-lookup"><span data-stu-id="52d07-121">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="52d07-122">在**编译**选项卡上，修改中的值**Option infer**框。</span><span class="sxs-lookup"><span data-stu-id="52d07-122">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52d07-123">示例</span><span class="sxs-lookup"><span data-stu-id="52d07-123">Example</span></span>  
 <span data-ttu-id="52d07-124">以下代码在启用局部类型推理的情况下编译 `test.vb`。</span><span class="sxs-lookup"><span data-stu-id="52d07-124">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="52d07-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52d07-125">See Also</span></span>  
 <span data-ttu-id="52d07-126">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="52d07-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="52d07-127"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="52d07-127"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="52d07-128"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="52d07-128"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="52d07-129"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="52d07-129"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="52d07-130"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="52d07-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="52d07-131"> [Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="52d07-131"> [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="52d07-132"> [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="52d07-132"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="52d07-133"> [Visual Basic 项目中，默认值选项对话框](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span><span class="sxs-lookup"><span data-stu-id="52d07-133"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span></span>  
<span data-ttu-id="52d07-134"> [“项目设计器”->“编译”页 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="52d07-134"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="52d07-135"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="52d07-135"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="52d07-136"> [从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)</span><span class="sxs-lookup"><span data-stu-id="52d07-136"> [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)</span></span>
