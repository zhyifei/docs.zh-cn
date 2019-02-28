---
title: Visual Basic 编码约定
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: e036792cf33082fa78cf243887b8ac7db7f8ad5a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981486"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="2a2b1-102">Visual Basic 编码约定</span><span class="sxs-lookup"><span data-stu-id="2a2b1-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="2a2b1-103">Microsoft 开发的示例和文档，请按照本主题中的准则。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="2a2b1-104">如果您遵循相同的编码约定，您可能会获得以下优势：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="2a2b1-105">你的代码将具有一致的外观，以便读者可以更好地专注于内容而非布局。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="2a2b1-106">读取器了解您的代码更快速因为它们可以使基于以前的经验的假设。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="2a2b1-107">可以复制、 更改，并更轻松地维护代码。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="2a2b1-108">可帮助确保您的代码演示 Visual Basic 的"最佳实践"。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="2a2b1-109">命名约定</span><span class="sxs-lookup"><span data-stu-id="2a2b1-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="2a2b1-110">有关命名指南的信息，请参阅[命名准则](../../../standard/design-guidelines/naming-guidelines.md)主题。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="2a2b1-111">不使用"My"我的"作为变量名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="2a2b1-112">此做法会与混淆`My`对象。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="2a2b1-113">无需更改自动生成的代码，使它们符合指南中的对象名称。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="2a2b1-114">布局约定</span><span class="sxs-lookup"><span data-stu-id="2a2b1-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="2a2b1-115">插入制表符作为空格，并使用智能缩进四空格缩进。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="2a2b1-116">使用**整齐排列代码 （重新格式化） 的**格式重新设置你的代码在代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="2a2b1-117">有关详细信息，请参阅[选项，文本编辑器，基本 (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="2a2b1-118">使用每行只有一条语句。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-118">Use only one statement per line.</span></span> <span data-ttu-id="2a2b1-119">不要使用 Visual Basic 行分隔符 （:）。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="2a2b1-120">避免使用隐式行继续符为支持显式行继续符"_"，无论该语言允许它在何处。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="2a2b1-121">使用每行只有一个声明。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="2a2b1-122">如果**整齐排列代码 （重新格式化） 的**不格式化继续行自动、 手动缩进一个制表位的延续任务行。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="2a2b1-123">但是，始终左对齐列表中的项。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="2a2b1-124">添加方法和属性定义之间的至少一个空白行。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="2a2b1-125">注释约定</span><span class="sxs-lookup"><span data-stu-id="2a2b1-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="2a2b1-126">将注释放在单独的行而不是代码行末尾处。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="2a2b1-127">开始注释文本以大写字母，并使用句点结束注释文本。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="2a2b1-128">插入注释分隔符 （'） 和注释文本之间的一个空格。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
-   <span data-ttu-id="2a2b1-129">环绕在注释格式化的星号块。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="2a2b1-130">程序结构</span><span class="sxs-lookup"><span data-stu-id="2a2b1-130">Program Structure</span></span>  
  
-   <span data-ttu-id="2a2b1-131">当你使用`Main`方法，使用默认构造进行新控制台应用程序，并使用`My`对命令行参数。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="2a2b1-132">语言准则</span><span class="sxs-lookup"><span data-stu-id="2a2b1-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="2a2b1-133">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="2a2b1-133">String Data Type</span></span>  
  
-   <span data-ttu-id="2a2b1-134">若要连接字符串，请使用与号 (&)。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#4)]  
  
-   <span data-ttu-id="2a2b1-135">若要追加在循环中的字符串，请使用<xref:System.Text.StringBuilder>对象。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="2a2b1-136">事件处理程序中的宽松的委托</span><span class="sxs-lookup"><span data-stu-id="2a2b1-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="2a2b1-137">不显式符合条件的参数 （对象和 EventArgs） 到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="2a2b1-138">如果不使用传递给事件 （例如，发送方为对象，e 为 EventArgs） 的事件参数，使用宽松的委托，并将在代码中的事件参数：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="2a2b1-139">无符号数据类型</span><span class="sxs-lookup"><span data-stu-id="2a2b1-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="2a2b1-140">使用`Integer`而不是无符号类型，将在必要时除外。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="2a2b1-141">数组</span><span class="sxs-lookup"><span data-stu-id="2a2b1-141">Arrays</span></span>  
  
-   <span data-ttu-id="2a2b1-142">在初始化数组声明行上的时，请使用短语法。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="2a2b1-143">例如，使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     <span data-ttu-id="2a2b1-144">不要使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
-   <span data-ttu-id="2a2b1-145">将数组指定符置于类型上而不是变量上。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="2a2b1-146">例如，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     <span data-ttu-id="2a2b1-147">不要使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
-   <span data-ttu-id="2a2b1-148">当声明和初始化基本数据类型的数组时，请使用 {} 语法。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="2a2b1-149">例如，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     <span data-ttu-id="2a2b1-150">不要使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="2a2b1-151">使用 With 关键字</span><span class="sxs-lookup"><span data-stu-id="2a2b1-151">Use the With Keyword</span></span>  
 <span data-ttu-id="2a2b1-152">当你进行一系列调用到一个对象时，请考虑使用`With`关键字：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="2a2b1-153">可以使用 Try...Catch 和 Using 语句时使用异常处理</span><span class="sxs-lookup"><span data-stu-id="2a2b1-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="2a2b1-154">请勿使用 `On Error Goto`。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="2a2b1-155">使用 IsNot 关键字</span><span class="sxs-lookup"><span data-stu-id="2a2b1-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="2a2b1-156">使用`IsNot`关键字而不是`Not...Is Nothing`。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="2a2b1-157">新的关键字</span><span class="sxs-lookup"><span data-stu-id="2a2b1-157">New Keyword</span></span>  
  
-   <span data-ttu-id="2a2b1-158">使用短实例化。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-158">Use short instantiation.</span></span> <span data-ttu-id="2a2b1-159">例如，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     <span data-ttu-id="2a2b1-160">前面的行是等效于此：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
-   <span data-ttu-id="2a2b1-161">使用对象初始值设定项的新对象而不是无参数构造函数：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a><span data-ttu-id="2a2b1-162">事件处理</span><span class="sxs-lookup"><span data-stu-id="2a2b1-162">Event Handling</span></span>  
  
-   <span data-ttu-id="2a2b1-163">使用`Handles`而非`AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="2a2b1-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
-   <span data-ttu-id="2a2b1-164">使用`AddressOf`，并执行不显式实例化委托：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
-   <span data-ttu-id="2a2b1-165">在定义事件时，使用短语法并让编译器定义此委托：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
-   <span data-ttu-id="2a2b1-166">不要验证事件是否是`Nothing`(null)，然后再调用`RaiseEvent`方法。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="2a2b1-167">`RaiseEvent` 检查`Nothing`引发事件之前。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="2a2b1-168">使用共享的成员</span><span class="sxs-lookup"><span data-stu-id="2a2b1-168">Using Shared Members</span></span>  
 <span data-ttu-id="2a2b1-169">调用`Shared`使用类名称，不能从一个实例变量的成员。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="2a2b1-170">使用 XML 文本</span><span class="sxs-lookup"><span data-stu-id="2a2b1-170">Use XML Literals</span></span>  
 <span data-ttu-id="2a2b1-171">XML 文本简化了在使用 XML （例如，加载、 查询和转换） 时遇到的最常见任务。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="2a2b1-172">当使用 XML 进行开发时，请遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="2a2b1-173">使用 XML 文本创建 XML 文档和片段，而不直接调用 XML Api。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="2a2b1-174">导入 XML 命名空间在文件或项目级别，以充分利用 XML 文本的性能优化。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="2a2b1-175">使用 XML 轴属性访问元素和 XML 文档中的属性。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="2a2b1-176">使用嵌入的表达式包括值并创建从现有值而不是使用 API 调用，如 XML`Add`方法：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a><span data-ttu-id="2a2b1-177">LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="2a2b1-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="2a2b1-178">对查询变量使用有意义的名称：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
-   <span data-ttu-id="2a2b1-179">为确保匿名类型的属性名称正确大写使用 Pascal 的查询中的元素提供名称大小写：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
-   <span data-ttu-id="2a2b1-180">如果结果中的属性名称模棱两可，请对属性重命名。</span><span class="sxs-lookup"><span data-stu-id="2a2b1-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="2a2b1-181">例如，如果您的查询返回一个客户名称和一个订单 ID，重命名它们而不是它们保留为`Name`和`ID`结果中：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
-   <span data-ttu-id="2a2b1-182">查询变量和范围变量的声明中使用类型推断功能：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
-   <span data-ttu-id="2a2b1-183">对齐下的查询子句`From`语句：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
-   <span data-ttu-id="2a2b1-184">使用`Where`子句之前其他查询子句，以便更高版本的查询子句作用于筛选的数据集：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
-   <span data-ttu-id="2a2b1-185">使用`Join`子句显式定义的联接操作，而不是使用`Where`子句隐式定义联接操作：</span><span class="sxs-lookup"><span data-stu-id="2a2b1-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="2a2b1-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a2b1-186">See also</span></span>
- [<span data-ttu-id="2a2b1-187">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="2a2b1-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
