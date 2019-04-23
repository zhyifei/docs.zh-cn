---
title: Option Explicit 语句 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 0a319ba4259e66ed9a37aa2de9e97d2335b78663
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308609"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="89b56-102">Option Explicit 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89b56-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="89b56-103">强制显式声明所有变量在文件中，或允许隐式声明的变量。</span><span class="sxs-lookup"><span data-stu-id="89b56-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b56-104">语法</span><span class="sxs-lookup"><span data-stu-id="89b56-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="89b56-105">部件</span><span class="sxs-lookup"><span data-stu-id="89b56-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="89b56-106">可选。</span><span class="sxs-lookup"><span data-stu-id="89b56-106">Optional.</span></span> <span data-ttu-id="89b56-107">使`Option Explicit`检查。</span><span class="sxs-lookup"><span data-stu-id="89b56-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="89b56-108">如果`On`或`Off`未指定，默认值为`On`。</span><span class="sxs-lookup"><span data-stu-id="89b56-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="89b56-109">可选。</span><span class="sxs-lookup"><span data-stu-id="89b56-109">Optional.</span></span> <span data-ttu-id="89b56-110">禁用`Option Explicit`检查。</span><span class="sxs-lookup"><span data-stu-id="89b56-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89b56-111">备注</span><span class="sxs-lookup"><span data-stu-id="89b56-111">Remarks</span></span>  
 <span data-ttu-id="89b56-112">当`Option Explicit On`或`Option Explicit`出现在文件中，您必须通过使用显式声明所有变量`Dim`或`ReDim`语句。</span><span class="sxs-lookup"><span data-stu-id="89b56-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="89b56-113">如果你尝试使用未声明的变量名称，在编译时就会出错。</span><span class="sxs-lookup"><span data-stu-id="89b56-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="89b56-114">`Option Explicit Off`语句允许隐式声明变量。</span><span class="sxs-lookup"><span data-stu-id="89b56-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="89b56-115">使用时，`Option Explicit` 语句必须在文件中任何其他源代码语句之前。</span><span class="sxs-lookup"><span data-stu-id="89b56-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89b56-116">设置`Option Explicit`到`Off`通常不是一个好的做法。</span><span class="sxs-lookup"><span data-stu-id="89b56-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="89b56-117">在一个或多个位置拼错变量名称，将会在程序运行时导致意想不到的结果。</span><span class="sxs-lookup"><span data-stu-id="89b56-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="89b56-118">Option Explicit 语句不存在</span><span class="sxs-lookup"><span data-stu-id="89b56-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="89b56-119">如果源代码不包含`Option Explicit`语句中， **Option Explicit**上设置[编译页，项目设计器 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)使用。</span><span class="sxs-lookup"><span data-stu-id="89b56-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="89b56-120">如果使用命令行编译器，则[/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)使用编译器选项。</span><span class="sxs-lookup"><span data-stu-id="89b56-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="89b56-121">若要在 IDE 中设置 Option Explicit</span><span class="sxs-lookup"><span data-stu-id="89b56-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="89b56-122">在“解决方案资源管理器”中，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="89b56-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="89b56-123">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="89b56-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="89b56-124">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="89b56-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="89b56-125">中的值设置**Option Explicit**框。</span><span class="sxs-lookup"><span data-stu-id="89b56-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="89b56-126">创建一个新项目时**Option Explicit**上设置**编译**选项卡设置为**Option Explicit**中设置**VB 默认值**对话框。</span><span class="sxs-lookup"><span data-stu-id="89b56-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="89b56-127">访问**VB 默认值**对话框中，在**工具**菜单中，单击**选项**。</span><span class="sxs-lookup"><span data-stu-id="89b56-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="89b56-128">在“选项”对话框中，展开“项目和解决方案”，然后单击“VB 默认值”。</span><span class="sxs-lookup"><span data-stu-id="89b56-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="89b56-129">中的初始默认设置**VB 默认值**是`On`。</span><span class="sxs-lookup"><span data-stu-id="89b56-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="89b56-130">若要在命令行上设置 Option Explicit</span><span class="sxs-lookup"><span data-stu-id="89b56-130">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="89b56-131">包括[/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)中的编译器选项**vbc**命令。</span><span class="sxs-lookup"><span data-stu-id="89b56-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89b56-132">示例</span><span class="sxs-lookup"><span data-stu-id="89b56-132">Example</span></span>  
 <span data-ttu-id="89b56-133">下面的示例使用`Option Explicit`语句强制显式声明所有变量。</span><span class="sxs-lookup"><span data-stu-id="89b56-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="89b56-134">尝试使用未声明的变量将导致在编译时错误。</span><span class="sxs-lookup"><span data-stu-id="89b56-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="89b56-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="89b56-135">See also</span></span>

- [<span data-ttu-id="89b56-136">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="89b56-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="89b56-137">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="89b56-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="89b56-138">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="89b56-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="89b56-139">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="89b56-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="89b56-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="89b56-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="89b56-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="89b56-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="89b56-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="89b56-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="89b56-143">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="89b56-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
