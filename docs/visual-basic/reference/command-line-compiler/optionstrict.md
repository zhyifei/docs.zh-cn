---
title: "/optionstrict |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionstrict
dev_langs:
- VB
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 17
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
ms.openlocfilehash: c22445cb53ca4f5621cf7aa69ab840b26f8e08c9
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="optionstrict"></a><span data-ttu-id="dfd30-102">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="dfd30-102">/optionstrict</span></span>
<span data-ttu-id="dfd30-103">强制使用严格类型语义来限制隐式类型转换。</span><span class="sxs-lookup"><span data-stu-id="dfd30-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfd30-104">语法</span><span class="sxs-lookup"><span data-stu-id="dfd30-104">Syntax</span></span>  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="dfd30-105">参数</span><span class="sxs-lookup"><span data-stu-id="dfd30-105">Arguments</span></span>  
 <span data-ttu-id="dfd30-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="dfd30-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="dfd30-107">可选。</span><span class="sxs-lookup"><span data-stu-id="dfd30-107">Optional.</span></span> <span data-ttu-id="dfd30-108">`/optionstrict+`选项将限制隐式类型转换。</span><span class="sxs-lookup"><span data-stu-id="dfd30-108">The `/optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="dfd30-109">此选项的默认值是`/optionstrict-`。</span><span class="sxs-lookup"><span data-stu-id="dfd30-109">The default for this option is `/optionstrict-`.</span></span> <span data-ttu-id="dfd30-110">`/optionstrict+`选项等同于`/optionstrict`。</span><span class="sxs-lookup"><span data-stu-id="dfd30-110">The `/optionstrict+` option is the same as `/optionstrict`.</span></span> <span data-ttu-id="dfd30-111">您可以使用内容的许可类型语义。</span><span class="sxs-lookup"><span data-stu-id="dfd30-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="dfd30-112">必需。</span><span class="sxs-lookup"><span data-stu-id="dfd30-112">Required.</span></span> <span data-ttu-id="dfd30-113">不遵从严格语言语义时发出警告。</span><span class="sxs-lookup"><span data-stu-id="dfd30-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfd30-114">备注</span><span class="sxs-lookup"><span data-stu-id="dfd30-114">Remarks</span></span>  
 <span data-ttu-id="dfd30-115">当`/optionstrict+`的效力范围是可以隐式地进行唯一扩大类型转换。</span><span class="sxs-lookup"><span data-stu-id="dfd30-115">When `/optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="dfd30-116">隐式收缩类型转换，如分配`Decimal`键入指向整数的类型对象的对象，报告为错误。</span><span class="sxs-lookup"><span data-stu-id="dfd30-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="dfd30-117">若要生成的隐式收缩类型转换的警告，请使用`/optionstrict:custom`。</span><span class="sxs-lookup"><span data-stu-id="dfd30-117">To generate warnings for implicit narrowing type conversions, use `/optionstrict:custom`.</span></span> <span data-ttu-id="dfd30-118">使用`/nowarn:numberlist`以忽略特定警告和`/warnaserror:numberlist`将特定的警告视为错误。</span><span class="sxs-lookup"><span data-stu-id="dfd30-118">Use `/nowarn:numberlist` to ignore particular warnings and `/warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="dfd30-119">在 Visual Studio IDE 中设置 /optionstrict</span><span class="sxs-lookup"><span data-stu-id="dfd30-119">To set /optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="dfd30-120">在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="dfd30-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="dfd30-121">在**项目**菜单上，单击**属性。**</span><span class="sxs-lookup"><span data-stu-id="dfd30-121">On the **Project** menu, click **Properties.**</span></span> <span data-ttu-id="dfd30-122">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="dfd30-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="dfd30-123">单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="dfd30-123">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="dfd30-124">在修改此值**Option Strict**框。</span><span class="sxs-lookup"><span data-stu-id="dfd30-124">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set-optionstrict-programmatically"></a><span data-ttu-id="dfd30-125">以编程方式设置 /optionstrict</span><span class="sxs-lookup"><span data-stu-id="dfd30-125">To set /optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="dfd30-126">请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd30-126">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfd30-127">示例</span><span class="sxs-lookup"><span data-stu-id="dfd30-127">Example</span></span>  
 <span data-ttu-id="dfd30-128">下面的代码编译`Test.vb`使用严格类型语义。</span><span class="sxs-lookup"><span data-stu-id="dfd30-128">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfd30-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfd30-129">See Also</span></span>  
 <span data-ttu-id="dfd30-130">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="dfd30-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="dfd30-131"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="dfd30-131"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="dfd30-132"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="dfd30-132"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="dfd30-133"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="dfd30-133"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="dfd30-134"> [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) </span><span class="sxs-lookup"><span data-stu-id="dfd30-134"> [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) </span></span>  
<span data-ttu-id="dfd30-135"> [/warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md) </span><span class="sxs-lookup"><span data-stu-id="dfd30-135"> [/warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md) </span></span>  
<span data-ttu-id="dfd30-136"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="dfd30-136"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="dfd30-137"> [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dfd30-137"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="dfd30-138"> [“选项”对话框 ->“项目”->“Visual Basic 默认值”](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="dfd30-138"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
