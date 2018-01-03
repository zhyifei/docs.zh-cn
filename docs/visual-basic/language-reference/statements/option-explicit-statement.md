---
title: "Option Explicit 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3d4c9cd3310e0ec3943c4e2b5e28be5b9a393db
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="09705-102">Option Explicit 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09705-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="09705-103">强制显式声明所有变量在文件中，或允许隐式声明的变量。</span><span class="sxs-lookup"><span data-stu-id="09705-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09705-104">语法</span><span class="sxs-lookup"><span data-stu-id="09705-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="09705-105">部件</span><span class="sxs-lookup"><span data-stu-id="09705-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="09705-106">可选。</span><span class="sxs-lookup"><span data-stu-id="09705-106">Optional.</span></span> <span data-ttu-id="09705-107">使`Option Explicit`检查。</span><span class="sxs-lookup"><span data-stu-id="09705-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="09705-108">如果`On`或`Off`未指定，则默认值是`On`。</span><span class="sxs-lookup"><span data-stu-id="09705-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="09705-109">可选。</span><span class="sxs-lookup"><span data-stu-id="09705-109">Optional.</span></span> <span data-ttu-id="09705-110">禁用`Option Explicit`检查。</span><span class="sxs-lookup"><span data-stu-id="09705-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09705-111">备注</span><span class="sxs-lookup"><span data-stu-id="09705-111">Remarks</span></span>  
 <span data-ttu-id="09705-112">当`Option Explicit On`或`Option Explicit`出现在文件中，你必须显式声明所有变量，通过使用`Dim`或`ReDim`语句。</span><span class="sxs-lookup"><span data-stu-id="09705-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="09705-113">如果你尝试使用未声明的变量名称，在编译时就会出错。</span><span class="sxs-lookup"><span data-stu-id="09705-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="09705-114">`Option Explicit Off`语句允许隐式声明变量。</span><span class="sxs-lookup"><span data-stu-id="09705-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="09705-115">使用时，`Option Explicit` 语句必须在文件中任何其他源代码语句之前。</span><span class="sxs-lookup"><span data-stu-id="09705-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09705-116">设置`Option Explicit`到`Off`但通常不很好的做法。</span><span class="sxs-lookup"><span data-stu-id="09705-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="09705-117">在一个或多个位置拼错变量名称，将会在程序运行时导致意想不到的结果。</span><span class="sxs-lookup"><span data-stu-id="09705-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="09705-118">Option Explicit 语句不存在</span><span class="sxs-lookup"><span data-stu-id="09705-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="09705-119">如果源代码不包含`Option Explicit`语句， **Option Explicit**上设置[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)使用。</span><span class="sxs-lookup"><span data-stu-id="09705-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="09705-120">如果使用命令行编译器， [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)使用编译器选项。</span><span class="sxs-lookup"><span data-stu-id="09705-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="09705-121">在 IDE 中设置 Option Explicit</span><span class="sxs-lookup"><span data-stu-id="09705-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="09705-122">在“解决方案资源管理器”中，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="09705-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="09705-123">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="09705-123">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="09705-124">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="09705-124">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="09705-125">设置中的值**Option Explicit**框。</span><span class="sxs-lookup"><span data-stu-id="09705-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="09705-126">当创建新项目， **Option Explicit**上设置**编译**选项卡设置为**Option Explicit**中设置**VB 默认值**对话框。</span><span class="sxs-lookup"><span data-stu-id="09705-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="09705-127">访问**VB 默认值**对话框中，在**工具**菜单上，单击**选项**。</span><span class="sxs-lookup"><span data-stu-id="09705-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="09705-128">在“选项”对话框中，展开“项目和解决方案”，然后单击“VB 默认值”。</span><span class="sxs-lookup"><span data-stu-id="09705-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="09705-129">中的初始默认设置**VB 默认值**是`On`。</span><span class="sxs-lookup"><span data-stu-id="09705-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="09705-130">若要在命令行上设置显式选项</span><span class="sxs-lookup"><span data-stu-id="09705-130">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="09705-131">包括[/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)中的编译器选项**vbc**命令。</span><span class="sxs-lookup"><span data-stu-id="09705-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09705-132">示例</span><span class="sxs-lookup"><span data-stu-id="09705-132">Example</span></span>  
 <span data-ttu-id="09705-133">下面的示例使用`Option Explicit`语句来强制显式声明所有变量。</span><span class="sxs-lookup"><span data-stu-id="09705-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="09705-134">尝试使用未声明的变量，将导致在编译时出现错误。</span><span class="sxs-lookup"><span data-stu-id="09705-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="09705-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="09705-135">See Also</span></span>  
 [<span data-ttu-id="09705-136">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="09705-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="09705-137">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="09705-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="09705-138">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="09705-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="09705-139">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="09705-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="09705-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="09705-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="09705-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="09705-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="09705-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="09705-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="09705-143">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="09705-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
