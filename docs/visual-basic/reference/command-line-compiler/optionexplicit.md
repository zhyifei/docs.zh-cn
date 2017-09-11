---
title: "/optionexplicit |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionexplicit
dev_langs:
- VB
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 16
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
ms.openlocfilehash: 3d2622c08b863233c8e1088bad252b37b3b38b04
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="optionexplicit"></a><span data-ttu-id="266ec-102">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="266ec-102">/optionexplicit</span></span>
<span data-ttu-id="266ec-103">如果在使用之前，不声明变量，会导致编译器报告错误。</span><span class="sxs-lookup"><span data-stu-id="266ec-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="266ec-104">语法</span><span class="sxs-lookup"><span data-stu-id="266ec-104">Syntax</span></span>  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="266ec-105">参数</span><span class="sxs-lookup"><span data-stu-id="266ec-105">Arguments</span></span>  
 <span data-ttu-id="266ec-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="266ec-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="266ec-107">可选。</span><span class="sxs-lookup"><span data-stu-id="266ec-107">Optional.</span></span> <span data-ttu-id="266ec-108">指定`/optionexplicit+`需要显式声明变量。</span><span class="sxs-lookup"><span data-stu-id="266ec-108">Specify `/optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="266ec-109">`/optionexplicit+`选项是默认设置，等同于`/optionexplicit`。</span><span class="sxs-lookup"><span data-stu-id="266ec-109">The `/optionexplicit+` option is the default and is the same as `/optionexplicit`.</span></span> <span data-ttu-id="266ec-110">`/optionexplicit-`选项启用隐式声明变量。</span><span class="sxs-lookup"><span data-stu-id="266ec-110">The `/optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="266ec-111">备注</span><span class="sxs-lookup"><span data-stu-id="266ec-111">Remarks</span></span>  
 <span data-ttu-id="266ec-112">如果源代码文件包含[Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md)，语句将覆盖`/optionexplicit`命令行编译器设置。</span><span class="sxs-lookup"><span data-stu-id="266ec-112">If the source code file contains an [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `/optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="266ec-113">在 Visual Studio IDE 中设置 /optionexplicit</span><span class="sxs-lookup"><span data-stu-id="266ec-113">To set /optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="266ec-114">在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="266ec-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="266ec-115">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="266ec-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="266ec-116">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="266ec-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="266ec-117">单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="266ec-117">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="266ec-118">在修改此值**Option Explicit**框。</span><span class="sxs-lookup"><span data-stu-id="266ec-118">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="266ec-119">示例</span><span class="sxs-lookup"><span data-stu-id="266ec-119">Example</span></span>  
 <span data-ttu-id="266ec-120">下面的代码编译时`/optionexplicit-`使用。</span><span class="sxs-lookup"><span data-stu-id="266ec-120">The following code compiles when `/optionexplicit-` is used.</span></span>  
  
 <span data-ttu-id="266ec-121">[!code-vb[VbVbalrCompiler #&5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="266ec-121">[!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="266ec-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="266ec-122">See Also</span></span>  
 <span data-ttu-id="266ec-123">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="266ec-123">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="266ec-124"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="266ec-124"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="266ec-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="266ec-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="266ec-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="266ec-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="266ec-127"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="266ec-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="266ec-128"> [Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="266ec-128"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="266ec-129"> [“选项”对话框 ->“项目”->“Visual Basic 默认值”](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="266ec-129"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
