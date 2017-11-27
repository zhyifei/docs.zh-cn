---
title: /define (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8bc3056c3e2d7a4aad469d3bf2c404f5f5248384
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="define-visual-basic"></a><span data-ttu-id="047e7-102">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="047e7-102">/define (Visual Basic)</span></span>
<span data-ttu-id="047e7-103">定义条件编译器常数。</span><span class="sxs-lookup"><span data-stu-id="047e7-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="047e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="047e7-104">Syntax</span></span>  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="047e7-105">参数</span><span class="sxs-lookup"><span data-stu-id="047e7-105">Arguments</span></span>  
  
|<span data-ttu-id="047e7-106">术语</span><span class="sxs-lookup"><span data-stu-id="047e7-106">Term</span></span>|<span data-ttu-id="047e7-107">定义</span><span class="sxs-lookup"><span data-stu-id="047e7-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="047e7-108">必需。</span><span class="sxs-lookup"><span data-stu-id="047e7-108">Required.</span></span> <span data-ttu-id="047e7-109">要定义的符号。</span><span class="sxs-lookup"><span data-stu-id="047e7-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="047e7-110">可选。</span><span class="sxs-lookup"><span data-stu-id="047e7-110">Optional.</span></span> <span data-ttu-id="047e7-111">指派给 `symbol` 的值。</span><span class="sxs-lookup"><span data-stu-id="047e7-111">The value to assign `symbol`.</span></span> <span data-ttu-id="047e7-112">如果`value`是一个字符串，则必须由反斜杠/双引号序列括起来 (\\") 而不是引号引起来。</span><span class="sxs-lookup"><span data-stu-id="047e7-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="047e7-113">如果未指定值，则视为 True。</span><span class="sxs-lookup"><span data-stu-id="047e7-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="047e7-114">备注</span><span class="sxs-lookup"><span data-stu-id="047e7-114">Remarks</span></span>  
 <span data-ttu-id="047e7-115">`/define` 选项具有与在源文件中使用 `#Const` 预处理器指令类似的效果，只是使用 `/define` 定义的常数为公共的且应用于项目中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="047e7-115">The `/define` option has an effect  similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `/define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="047e7-116">可以将由此选项创建的符号同 `#If`...`Then`...`#Else` 指令一起使用，以对源文件进行条件编译。</span><span class="sxs-lookup"><span data-stu-id="047e7-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="047e7-117">`/d` 是 `/define` 的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="047e7-117">`/d` is the short form of `/define`.</span></span>  
  
 <span data-ttu-id="047e7-118">通过使用逗号分隔符号定义，可以用 `/define` 定义多个符号。</span><span class="sxs-lookup"><span data-stu-id="047e7-118">You can define multiple symbols with `/define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="047e7-119">在 Visual Studio 集成开发环境中设置/定义</span><span class="sxs-lookup"><span data-stu-id="047e7-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="047e7-120">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="047e7-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="047e7-121">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="047e7-121">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="047e7-122">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="047e7-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="047e7-123">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="047e7-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="047e7-124">3.单击 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="047e7-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="047e7-125">4.修改中的值**自定义常量**框。</span><span class="sxs-lookup"><span data-stu-id="047e7-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="047e7-126">示例</span><span class="sxs-lookup"><span data-stu-id="047e7-126">Example</span></span>  
 <span data-ttu-id="047e7-127">下面的代码定义并使用两个条件编译器常数。</span><span class="sxs-lookup"><span data-stu-id="047e7-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="047e7-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="047e7-128">See Also</span></span>  
 [<span data-ttu-id="047e7-129">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="047e7-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="047e7-130">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="047e7-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="047e7-131">#Const 指令</span><span class="sxs-lookup"><span data-stu-id="047e7-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="047e7-132">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="047e7-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
