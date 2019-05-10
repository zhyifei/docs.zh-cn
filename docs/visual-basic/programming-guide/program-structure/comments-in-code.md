---
title: 代码中的注释 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
ms.openlocfilehash: 2737d9494fb4cd2f0cfaec4da1bca69003c6bad7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753754"
---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="66a6c-102">代码中的注释 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66a6c-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="66a6c-103">阅读代码示例时，经常会遇到注释符号 (`'`)。</span><span class="sxs-lookup"><span data-stu-id="66a6c-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="66a6c-104">此符号通知 Visual Basic 编译器忽略它，后面的文本或*注释*。</span><span class="sxs-lookup"><span data-stu-id="66a6c-104">This symbol tells the Visual Basic compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="66a6c-105">注释是为了方便阅读而为代码添加的简短的解释性说明。</span><span class="sxs-lookup"><span data-stu-id="66a6c-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="66a6c-106">在所有过程的开头加入一段说明过程功能特征（过程的作用）的简短注释是一个很好的编程做法。</span><span class="sxs-lookup"><span data-stu-id="66a6c-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="66a6c-107">这对你自己和检查代码的任何其他人都有好处。</span><span class="sxs-lookup"><span data-stu-id="66a6c-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="66a6c-108">应该把实现的详细信息（过程实现的方式）与描述功能特征的注释分开。</span><span class="sxs-lookup"><span data-stu-id="66a6c-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="66a6c-109">若给说明加入了实现的详细信息，切记在更新函数时对这些详细信息进行更新。</span><span class="sxs-lookup"><span data-stu-id="66a6c-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="66a6c-110">注释可以和语句同行并跟随其后，也可以另占一整行。</span><span class="sxs-lookup"><span data-stu-id="66a6c-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="66a6c-111">以下代码阐释了这两种情况。</span><span class="sxs-lookup"><span data-stu-id="66a6c-111">Both are illustrated in the following code.</span></span>  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 <span data-ttu-id="66a6c-112">如果注释需要多行，请在每行的前面使用注释符号，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="66a6c-112">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="66a6c-113">注释原则</span><span class="sxs-lookup"><span data-stu-id="66a6c-113">Commenting Guidelines</span></span>  
 <span data-ttu-id="66a6c-114">下表提供了在一段代码前可以加上哪些类型的注释的一般原则。</span><span class="sxs-lookup"><span data-stu-id="66a6c-114">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="66a6c-115">这些是一些建议;Visual Basic 不会强制实施有关添加注释的规则。</span><span class="sxs-lookup"><span data-stu-id="66a6c-115">These are suggestions; Visual Basic does not enforce rules for adding comments.</span></span> <span data-ttu-id="66a6c-116">编写注释时，应编写对你和代码的任何其他读者都最为有效的注释。</span><span class="sxs-lookup"><span data-stu-id="66a6c-116">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="66a6c-117">注释类型</span><span class="sxs-lookup"><span data-stu-id="66a6c-117">Comment type</span></span>|<span data-ttu-id="66a6c-118">注释说明</span><span class="sxs-lookup"><span data-stu-id="66a6c-118">Comment description</span></span>|  
|<span data-ttu-id="66a6c-119">用途</span><span class="sxs-lookup"><span data-stu-id="66a6c-119">Purpose</span></span>|<span data-ttu-id="66a6c-120">描述过程的用途（而不是其实现方式）</span><span class="sxs-lookup"><span data-stu-id="66a6c-120">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="66a6c-121">假设</span><span class="sxs-lookup"><span data-stu-id="66a6c-121">Assumptions</span></span>|<span data-ttu-id="66a6c-122">列举每个外部变量、控件、打开的文件或过程访问的其他元素</span><span class="sxs-lookup"><span data-stu-id="66a6c-122">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="66a6c-123">Effects</span><span class="sxs-lookup"><span data-stu-id="66a6c-123">Effects</span></span>|<span data-ttu-id="66a6c-124">列举每个受影响的外部变量、控件、文件以及它的作用（仅在作用不明显时列举）</span><span class="sxs-lookup"><span data-stu-id="66a6c-124">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="66a6c-125">输入</span><span class="sxs-lookup"><span data-stu-id="66a6c-125">Inputs</span></span>|<span data-ttu-id="66a6c-126">指定自变量的用途</span><span class="sxs-lookup"><span data-stu-id="66a6c-126">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="66a6c-127">返回</span><span class="sxs-lookup"><span data-stu-id="66a6c-127">Returns</span></span>|<span data-ttu-id="66a6c-128">说明过程返回的值</span><span class="sxs-lookup"><span data-stu-id="66a6c-128">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="66a6c-129">请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="66a6c-129">Remember the following points:</span></span>  
  
- <span data-ttu-id="66a6c-130">每个重要的变量声明前都应有注释，用以描述被声明变量的用途。</span><span class="sxs-lookup"><span data-stu-id="66a6c-130">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
- <span data-ttu-id="66a6c-131">变量、控件和过程的命名应当足够清楚，使得只在遇到复杂的实现详细情况时才使用注释。</span><span class="sxs-lookup"><span data-stu-id="66a6c-131">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
- <span data-ttu-id="66a6c-132">注释不能与行继续符同行。</span><span class="sxs-lookup"><span data-stu-id="66a6c-132">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="66a6c-133">您可以添加或删除的代码块的注释符通过选择一个或多个行代码，然后选择**注释**(![Visual Studio 中的 Visual Basic 注释按钮](./media/comments-in-code/visual-basic-comment-button.gif)) 和**取消注释** (![Visual Studio 中的 Visual Basic 取消注释按钮](./media/comments-in-code/visual-basic-uncomment-button.gif)) 上的按钮**编辑**工具栏。</span><span class="sxs-lookup"><span data-stu-id="66a6c-133">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![The Visual Basic Comment button in Visual Studio.](./media/comments-in-code/visual-basic-comment-button.gif)) and **Uncomment** (![The Visual Basic Uncomment button in Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66a6c-134">也可以用在文本前加关键字 `REM` 的方式给代码添加注释。</span><span class="sxs-lookup"><span data-stu-id="66a6c-134">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="66a6c-135">但是，`'`符号并**注释**/**取消注释**按钮是易于使用和需要较少的空间和内存。</span><span class="sxs-lookup"><span data-stu-id="66a6c-135">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a6c-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="66a6c-136">See also</span></span>

- [<span data-ttu-id="66a6c-137">基本技术-使用 XML 注释记录代码</span><span class="sxs-lookup"><span data-stu-id="66a6c-137">Basic Instincts - Documenting Your Code With XML Comments</span></span>](https://msdn.microsoft.com/magazine/dd722812.aspx)
- [<span data-ttu-id="66a6c-138">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="66a6c-138">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="66a6c-139">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="66a6c-139">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="66a6c-140">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="66a6c-140">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="66a6c-141">REM 语句</span><span class="sxs-lookup"><span data-stu-id="66a6c-141">REM Statement</span></span>](../../../visual-basic/language-reference/statements/rem-statement.md)
