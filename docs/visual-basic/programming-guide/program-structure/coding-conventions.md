---
title: "Visual Basic 编码约定 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- coding conventions, Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
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
ms.openlocfilehash: 16d4ddccd3a16c48e58f297faf8909148899013f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="26e0f-102">Visual Basic 编码约定</span><span class="sxs-lookup"><span data-stu-id="26e0f-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="26e0f-103">Microsoft 开发示例和文档，请遵循本主题中的准则。</span><span class="sxs-lookup"><span data-stu-id="26e0f-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="26e0f-104">如果您遵循相同的编码约定，您可能会获得以下好处︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="26e0f-105">您的代码将具有一致的外观，以确保读取器可以更好地专注于内容而非布局。</span><span class="sxs-lookup"><span data-stu-id="26e0f-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="26e0f-106">读者理解您的代码更加快速因为它们可能会使基于以前的经验的假设。</span><span class="sxs-lookup"><span data-stu-id="26e0f-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="26e0f-107">您可以复制、 更改，并更轻松地维护代码。</span><span class="sxs-lookup"><span data-stu-id="26e0f-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="26e0f-108">可帮助确保您的代码演示 Visual basic"的最佳做法"。</span><span class="sxs-lookup"><span data-stu-id="26e0f-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="26e0f-109">命名约定</span><span class="sxs-lookup"><span data-stu-id="26e0f-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="26e0f-110">有关命名准则的信息，请参阅[命名准则](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3)主题。</span><span class="sxs-lookup"><span data-stu-id="26e0f-110">For information about naming guidelines, see [Naming Guidelines](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) topic.</span></span>  
  
-   <span data-ttu-id="26e0f-111">不使用"我的"我的"作为变量名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="26e0f-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="26e0f-112">这种做法会导致与混淆`My`对象。</span><span class="sxs-lookup"><span data-stu-id="26e0f-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="26e0f-113">无需更改的自动生成的代码以使它们适合这些准则中的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="26e0f-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="26e0f-114">布局约定</span><span class="sxs-lookup"><span data-stu-id="26e0f-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="26e0f-115">插入选项卡中的根据空格，并使用具有四个空间缩进量智能缩进。</span><span class="sxs-lookup"><span data-stu-id="26e0f-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="26e0f-116">使用**整齐排列 （重新格式化） 的代码**重新格式化您的代码在代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="26e0f-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="26e0f-117">有关详细信息，请参阅[选项，文本编辑器中，基本 (Visual Basic 中)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="26e0f-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="26e0f-118">使用每行只有一条语句。</span><span class="sxs-lookup"><span data-stu-id="26e0f-118">Use only one statement per line.</span></span> <span data-ttu-id="26e0f-119">不要使用 Visual Basic 行分隔符 （:）。</span><span class="sxs-lookup"><span data-stu-id="26e0f-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="26e0f-120">避免使用该语言允许它支持隐式行继续符显式行延续字符"_"。</span><span class="sxs-lookup"><span data-stu-id="26e0f-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="26e0f-121">使用每行只有一个声明。</span><span class="sxs-lookup"><span data-stu-id="26e0f-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="26e0f-122">如果**整齐排列 （重新格式化） 的代码**不格式连续行自动、 手动缩进一个制表位的延续任务行。</span><span class="sxs-lookup"><span data-stu-id="26e0f-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="26e0f-123">但是，始终向左对齐列表中的项。</span><span class="sxs-lookup"><span data-stu-id="26e0f-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="26e0f-124">添加方法和属性定义之间的至少一个空白行。</span><span class="sxs-lookup"><span data-stu-id="26e0f-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="26e0f-125">注释约定</span><span class="sxs-lookup"><span data-stu-id="26e0f-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="26e0f-126">将注释放在单独的行而不是在代码行的末尾。</span><span class="sxs-lookup"><span data-stu-id="26e0f-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="26e0f-127">开始注释文本以大写字母，并以句点结束注释文本。</span><span class="sxs-lookup"><span data-stu-id="26e0f-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="26e0f-128">插入注释分隔符 （'） 与注释文本之间的一个空格。</span><span class="sxs-lookup"><span data-stu-id="26e0f-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     <span data-ttu-id="26e0f-129">[!code-vb[VbVbalrGuidelines #&2;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-129">[!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-130">请不要括起来格式化的星号块注释。</span><span class="sxs-lookup"><span data-stu-id="26e0f-130">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="26e0f-131">程序结构</span><span class="sxs-lookup"><span data-stu-id="26e0f-131">Program Structure</span></span>  
  
-   <span data-ttu-id="26e0f-132">当您使用`Main`方法中，默认结构用于新的控制台应用程序，并使用`My`对命令行参数。</span><span class="sxs-lookup"><span data-stu-id="26e0f-132">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     <span data-ttu-id="26e0f-133">[!code-vb[VbVbalrGuidelines #&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-133">[!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="26e0f-134">语言准则</span><span class="sxs-lookup"><span data-stu-id="26e0f-134">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="26e0f-135">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="26e0f-135">String Data Type</span></span>  
  
-   <span data-ttu-id="26e0f-136">若要连接字符串，使用 and 符 （&）。</span><span class="sxs-lookup"><span data-stu-id="26e0f-136">To concatenate strings, use an ampersand (&).</span></span>  
  
     <span data-ttu-id="26e0f-137">[!code-vb[VbVbalrGuidelines #&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-137">[!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-138">若要追加在循环中的字符串，请使用<xref:System.Text.StringBuilder>对象。</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="26e0f-138">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="26e0f-139">[!code-vb[VbVbalrGuidelines #&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-139">[!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span></span>  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="26e0f-140">宽松的委托事件处理程序中</span><span class="sxs-lookup"><span data-stu-id="26e0f-140">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="26e0f-141">请勿显式限定 （对象和 EventArgs） 的参数与事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26e0f-141">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="26e0f-142">如果您未使用的事件参数传递给事件 （例如，发件人为对象，作为 EventArgs e），使用宽松的委托，并使出在代码中的事件参数︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-142">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 <span data-ttu-id="26e0f-143">[!code-vb[VbVbalrGuidelines #&7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-143">[!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="26e0f-144">无符号数据类型</span><span class="sxs-lookup"><span data-stu-id="26e0f-144">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="26e0f-145">使用`Integer`而不是无符号类型，除非它们是所必需。</span><span class="sxs-lookup"><span data-stu-id="26e0f-145">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="26e0f-146">数组</span><span class="sxs-lookup"><span data-stu-id="26e0f-146">Arrays</span></span>  
  
-   <span data-ttu-id="26e0f-147">在声明行上初始化数组时，请使用短语法。</span><span class="sxs-lookup"><span data-stu-id="26e0f-147">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="26e0f-148">例如，使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="26e0f-148">For example, use the following syntax.</span></span>  
  
     <span data-ttu-id="26e0f-149">[!code-vb[VbVbalrGuidelines #&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-149">[!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span></span>  
  
     <span data-ttu-id="26e0f-150">不要使用下面的语法。</span><span class="sxs-lookup"><span data-stu-id="26e0f-150">Do not use the following syntax.</span></span>  
  
     <span data-ttu-id="26e0f-151">[!code-vb[VbVbalrGuidelines #&9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-151">[!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-152">将数组指示符放在类型上，而不在该变量上。</span><span class="sxs-lookup"><span data-stu-id="26e0f-152">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="26e0f-153">例如，使用以下语法︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-153">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="26e0f-154">[!code-vb[VbVbalrGuidelines #&11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-154">[!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span></span>  
  
     <span data-ttu-id="26e0f-155">不要使用以下语法︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-155">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="26e0f-156">[!code-vb[VbVbalrGuidelines #&10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-156">[!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-157">在声明并初始化的基本数据类型的数组时，请使用 {} 语法。</span><span class="sxs-lookup"><span data-stu-id="26e0f-157">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="26e0f-158">例如，使用以下语法︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-158">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="26e0f-159">[!code-vb[VbVbalrGuidelines #&12;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-159">[!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span></span>  
  
     <span data-ttu-id="26e0f-160">不要使用以下语法︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-160">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="26e0f-161">[!code-vb[VbVbalrGuidelines #&13;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-161">[!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span></span>  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="26e0f-162">使用 With 关键字</span><span class="sxs-lookup"><span data-stu-id="26e0f-162">Use the With Keyword</span></span>  
 <span data-ttu-id="26e0f-163">当你进行一系列调用到一个对象时，请考虑使用`With`关键字︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-163">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 <span data-ttu-id="26e0f-164">[!code-vb[VbVbalrGuidelines #&15;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-164">[!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span></span>  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="26e0f-165">可以使用 Try...Catch 和 Using 语句时使用异常处理</span><span class="sxs-lookup"><span data-stu-id="26e0f-165">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="26e0f-166">请不要使用`On Error Goto`。</span><span class="sxs-lookup"><span data-stu-id="26e0f-166">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="26e0f-167">使用 IsNot 关键字</span><span class="sxs-lookup"><span data-stu-id="26e0f-167">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="26e0f-168">使用`IsNot`关键字而不是`Not...Is Nothing`。</span><span class="sxs-lookup"><span data-stu-id="26e0f-168">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="26e0f-169">New 关键字</span><span class="sxs-lookup"><span data-stu-id="26e0f-169">New Keyword</span></span>  
  
-   <span data-ttu-id="26e0f-170">使用短实例化。</span><span class="sxs-lookup"><span data-stu-id="26e0f-170">Use short instantiation.</span></span> <span data-ttu-id="26e0f-171">例如，使用以下语法︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-171">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="26e0f-172">[!code-vb[VbVbalrGuidelines #&21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-172">[!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span></span>  
  
     <span data-ttu-id="26e0f-173">前面的行是等效于此︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-173">The preceding line is equivalent to this:</span></span>  
  
     <span data-ttu-id="26e0f-174">[!code-vb[VbVbalrGuidelines #&22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-174">[!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-175">为新对象，而无参数构造函数不使用对象初始值设定项︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-175">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     <span data-ttu-id="26e0f-176">[!code-vb[VbVbalrGuidelines 第&23;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-176">[!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="26e0f-177">事件处理</span><span class="sxs-lookup"><span data-stu-id="26e0f-177">Event Handling</span></span>  
  
-   <span data-ttu-id="26e0f-178">使用`Handles`而不是`AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="26e0f-178">Use `Handles` rather than `AddHandler`:</span></span>  
  
     <span data-ttu-id="26e0f-179">[!code-vb[VbVbalrGuidelines #&24;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-179">[!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-180">使用`AddressOf`，并不显式实例委托︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-180">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     <span data-ttu-id="26e0f-181">[!code-vb[VbVbalrGuidelines #&25;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-181">[!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-182">在定义事件时，使用短语法，并让编译器定义委托︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-182">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     <span data-ttu-id="26e0f-183">[!code-vb[VbVbalrGuidelines #&26;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-183">[!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-184">不验证事件是否是`Nothing`(null)，然后才能调用`RaiseEvent`方法。</span><span class="sxs-lookup"><span data-stu-id="26e0f-184">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="26e0f-185">`RaiseEvent`检查`Nothing`引发事件之前。</span><span class="sxs-lookup"><span data-stu-id="26e0f-185">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="26e0f-186">使用共享的成员</span><span class="sxs-lookup"><span data-stu-id="26e0f-186">Using Shared Members</span></span>  
 <span data-ttu-id="26e0f-187">调用`Shared`通过类的名称，不能从实例变量的成员。</span><span class="sxs-lookup"><span data-stu-id="26e0f-187">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="26e0f-188">使用 XML 文本</span><span class="sxs-lookup"><span data-stu-id="26e0f-188">Use XML Literals</span></span>  
 <span data-ttu-id="26e0f-189">XML 文本简化您使用 XML （例如，加载、 查询和转换） 时遇到的最常见任务。</span><span class="sxs-lookup"><span data-stu-id="26e0f-189">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="26e0f-190">当使用 XML 进行开发时，请遵循以下准则︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-190">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="26e0f-191">使用 XML 文本来创建 XML 文档和片段而不是直接调用 XML Api。</span><span class="sxs-lookup"><span data-stu-id="26e0f-191">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="26e0f-192">导入 XML 命名空间在文件或项目级别，以利用 XML 文本的性能优化。</span><span class="sxs-lookup"><span data-stu-id="26e0f-192">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="26e0f-193">XML 轴属性用于访问 XML 文档中元素和属性。</span><span class="sxs-lookup"><span data-stu-id="26e0f-193">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="26e0f-194">使用嵌入式的表达式包括值并根据现有值而不是使用 API 调用，如创建 XML`Add`方法︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-194">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     <span data-ttu-id="26e0f-195">[!code-vb[VbVbalrGuidelines #&27;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-195">[!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="26e0f-196">LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="26e0f-196">LINQ Queries</span></span>  
  
-   <span data-ttu-id="26e0f-197">对查询变量使用有意义的名称︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-197">Use meaningful names for query variables:</span></span>  
  
     <span data-ttu-id="26e0f-198">[!code-vb[VbVbalrGuidelines #&28;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-198">[!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-199">若要确保匿名类型的属性名称正确大写使用 Pascal 查询中的元素为提供的名称的大小写︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-199">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     <span data-ttu-id="26e0f-200">[!code-vb[VbVbalrGuidelines #&29;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-200">[!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-201">如果结果中的属性名称模棱两可，请对属性重命名。</span><span class="sxs-lookup"><span data-stu-id="26e0f-201">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="26e0f-202">例如，如果您的查询返回客户名称和一个订单 ID，将其重命名而不是将它们保留为`Name`和`ID`结果中︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-202">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     <span data-ttu-id="26e0f-203">[!code-vb[VbVbalrGuidelines #&30;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-203">[!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-204">在查询变量和范围变量的声明中使用类型推断︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-204">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     <span data-ttu-id="26e0f-205">[!code-vb[VbVbalrGuidelines #&31;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-205">[!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-206">对齐下的查询子句`From`语句︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-206">Align query clauses under the `From` statement:</span></span>  
  
     <span data-ttu-id="26e0f-207">[!code-vb[VbVbalrGuidelines #&32;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-207">[!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-208">使用`Where`子句之前其他查询子句，以便更高版本的查询子句作用于筛选的数据集︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-208">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     <span data-ttu-id="26e0f-209">[!code-vb[VbVbalrGuidelines 第&33;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-209">[!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span></span>  
  
-   <span data-ttu-id="26e0f-210">使用`Join`子句显式定义联接操作，而不是使用`Where`子句隐式定义联接操作︰</span><span class="sxs-lookup"><span data-stu-id="26e0f-210">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     <span data-ttu-id="26e0f-211">[!code-vb[VbVbalrGuidelines #&34;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span><span class="sxs-lookup"><span data-stu-id="26e0f-211">[!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e0f-212">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26e0f-212">See Also</span></span>  
 [<span data-ttu-id="26e0f-213">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="26e0f-213">Secure Coding Guidelines</span></span>](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)
