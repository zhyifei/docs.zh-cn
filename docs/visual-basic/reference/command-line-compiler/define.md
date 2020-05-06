---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: 5035466de4aa17c374824e1b0f02ed594731a9d3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716801"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="7e085-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e085-102">-define (Visual Basic)</span></span>
<span data-ttu-id="7e085-103">定义条件编译器常数。</span><span class="sxs-lookup"><span data-stu-id="7e085-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e085-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e085-104">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="7e085-105">or</span><span class="sxs-lookup"><span data-stu-id="7e085-105">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7e085-106">自变量</span><span class="sxs-lookup"><span data-stu-id="7e085-106">Arguments</span></span>  
  
|<span data-ttu-id="7e085-107">术语</span><span class="sxs-lookup"><span data-stu-id="7e085-107">Term</span></span>|<span data-ttu-id="7e085-108">定义</span><span class="sxs-lookup"><span data-stu-id="7e085-108">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="7e085-109">必需。</span><span class="sxs-lookup"><span data-stu-id="7e085-109">Required.</span></span> <span data-ttu-id="7e085-110">要定义的符号。</span><span class="sxs-lookup"><span data-stu-id="7e085-110">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="7e085-111">可选。</span><span class="sxs-lookup"><span data-stu-id="7e085-111">Optional.</span></span> <span data-ttu-id="7e085-112">指派给 `symbol` 的值。</span><span class="sxs-lookup"><span data-stu-id="7e085-112">The value to assign `symbol`.</span></span> <span data-ttu-id="7e085-113">如果 `value` 是一个字符串，它必须放在反斜杠/双引号序列 (\\") 内而不只是双引号内。</span><span class="sxs-lookup"><span data-stu-id="7e085-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="7e085-114">如果未指定值，则视为 True。</span><span class="sxs-lookup"><span data-stu-id="7e085-114">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e085-115">备注</span><span class="sxs-lookup"><span data-stu-id="7e085-115">Remarks</span></span>  
 <span data-ttu-id="7e085-116">`-define` 选项具有与在源文件中使用 `#Const` 预处理器指令类似的效果，只是使用 `-define` 定义的常数为公共的且应用于项目中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="7e085-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="7e085-117">可以将由此选项创建的符号同 `#If`...`Then`...`#Else` 指令一起使用，以对源文件进行条件编译。</span><span class="sxs-lookup"><span data-stu-id="7e085-117">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="7e085-118">`-d` 是 `-define` 的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="7e085-118">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="7e085-119">通过使用逗号分隔符号定义，可以用 `-define` 定义多个符号。</span><span class="sxs-lookup"><span data-stu-id="7e085-119">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="7e085-120">在 Visual Studio 集成开发环境中设置 -define</span><span class="sxs-lookup"><span data-stu-id="7e085-120">To set -define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="7e085-121">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="7e085-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7e085-122">在“项目”菜单上，单击“属性”   。</span><span class="sxs-lookup"><span data-stu-id="7e085-122">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="7e085-123">2.单击“编译”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="7e085-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="7e085-124">3.单击 **“高级”** 。</span><span class="sxs-lookup"><span data-stu-id="7e085-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="7e085-125">4.修改“自定义常量”  框中的值。</span><span class="sxs-lookup"><span data-stu-id="7e085-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7e085-126">示例</span><span class="sxs-lookup"><span data-stu-id="7e085-126">Example</span></span>  
 <span data-ttu-id="7e085-127">下面的代码定义并使用两个条件编译器常数。</span><span class="sxs-lookup"><span data-stu-id="7e085-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="7e085-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e085-128">See also</span></span>

- [<span data-ttu-id="7e085-129">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="7e085-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7e085-130">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="7e085-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="7e085-131">#Const 指令</span><span class="sxs-lookup"><span data-stu-id="7e085-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="7e085-132">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="7e085-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
