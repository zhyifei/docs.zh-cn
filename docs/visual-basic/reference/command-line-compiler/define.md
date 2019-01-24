---
title: -定义 (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: 3560ea14236bfa2fffbc309847e8ef9e4b821de9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739266"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="2edf8-102">-定义 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2edf8-102">-define (Visual Basic)</span></span>
<span data-ttu-id="2edf8-103">定义条件编译器常数。</span><span class="sxs-lookup"><span data-stu-id="2edf8-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2edf8-104">语法</span><span class="sxs-lookup"><span data-stu-id="2edf8-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2edf8-105">自变量</span><span class="sxs-lookup"><span data-stu-id="2edf8-105">Arguments</span></span>  
  
|<span data-ttu-id="2edf8-106">术语</span><span class="sxs-lookup"><span data-stu-id="2edf8-106">Term</span></span>|<span data-ttu-id="2edf8-107">定义</span><span class="sxs-lookup"><span data-stu-id="2edf8-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="2edf8-108">必需。</span><span class="sxs-lookup"><span data-stu-id="2edf8-108">Required.</span></span> <span data-ttu-id="2edf8-109">要定义的符号。</span><span class="sxs-lookup"><span data-stu-id="2edf8-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="2edf8-110">可选。</span><span class="sxs-lookup"><span data-stu-id="2edf8-110">Optional.</span></span> <span data-ttu-id="2edf8-111">指派给 `symbol` 的值。</span><span class="sxs-lookup"><span data-stu-id="2edf8-111">The value to assign `symbol`.</span></span> <span data-ttu-id="2edf8-112">如果`value`是一个字符串，它必须用反斜杠/双引号序列 (\\") 而不是引号引起来。</span><span class="sxs-lookup"><span data-stu-id="2edf8-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="2edf8-113">如果未指定值，则视为 True。</span><span class="sxs-lookup"><span data-stu-id="2edf8-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2edf8-114">备注</span><span class="sxs-lookup"><span data-stu-id="2edf8-114">Remarks</span></span>  
 <span data-ttu-id="2edf8-115">`-define`选项才起作用类似于使用`#Const`预处理器指令在源代码文件中，除定义的常数`-define`是公共的并将应用到项目中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="2edf8-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="2edf8-116">可以将由此选项创建的符号同 `#If`...`Then`...`#Else` 指令一起使用，以对源文件进行条件编译。</span><span class="sxs-lookup"><span data-stu-id="2edf8-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="2edf8-117">`-d` 是 `-define` 的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="2edf8-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="2edf8-118">通过使用逗号分隔符号定义，可以用 `-define` 定义多个符号。</span><span class="sxs-lookup"><span data-stu-id="2edf8-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="2edf8-119">在 Visual Studio 集成开发环境中设置/定义</span><span class="sxs-lookup"><span data-stu-id="2edf8-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2edf8-120">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="2edf8-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2edf8-121">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="2edf8-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="2edf8-122">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="2edf8-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2edf8-123">3.单击 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="2edf8-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="2edf8-124">4.修改中的值**自定义常量**框。</span><span class="sxs-lookup"><span data-stu-id="2edf8-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2edf8-125">示例</span><span class="sxs-lookup"><span data-stu-id="2edf8-125">Example</span></span>  
 <span data-ttu-id="2edf8-126">下面的代码定义并使用两个条件编译器常数。</span><span class="sxs-lookup"><span data-stu-id="2edf8-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2edf8-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="2edf8-127">See also</span></span>
- [<span data-ttu-id="2edf8-128">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="2edf8-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2edf8-129">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="2edf8-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="2edf8-130">#Const 指令</span><span class="sxs-lookup"><span data-stu-id="2edf8-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="2edf8-131">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="2edf8-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
