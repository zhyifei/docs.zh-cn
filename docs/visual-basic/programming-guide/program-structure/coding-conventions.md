---
title: Visual Basic 编码约定
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: b686747b46529b53b0802a7deb38b5b4949f4d5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655356"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="d4b17-102">Visual Basic 编码约定</span><span class="sxs-lookup"><span data-stu-id="d4b17-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="d4b17-103">Microsoft 开发示例和文档，请遵循本主题中的准则。</span><span class="sxs-lookup"><span data-stu-id="d4b17-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="d4b17-104">如果您按照相同的编码约定，你可能会获得以下好处：</span><span class="sxs-lookup"><span data-stu-id="d4b17-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="d4b17-105">你的代码将具有一致的外观，以确保读取器可以更好地专注于内容而非布局。</span><span class="sxs-lookup"><span data-stu-id="d4b17-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="d4b17-106">读者了解你的代码更快速因为它们可能会使基于之前的经验的假设。</span><span class="sxs-lookup"><span data-stu-id="d4b17-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="d4b17-107">你可以复制、 更改，并更轻松地维护代码。</span><span class="sxs-lookup"><span data-stu-id="d4b17-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="d4b17-108">可帮助确保你的代码适用于 Visual Basic 演示"最佳做法"。</span><span class="sxs-lookup"><span data-stu-id="d4b17-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="d4b17-109">命名约定</span><span class="sxs-lookup"><span data-stu-id="d4b17-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="d4b17-110">有关命名准则的信息，请参阅[命名准则](../../../standard/design-guidelines/naming-guidelines.md)主题。</span><span class="sxs-lookup"><span data-stu-id="d4b17-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="d4b17-111">不使用"我的"我的"作为变量名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="d4b17-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="d4b17-112">本练习中创建与混淆`My`对象。</span><span class="sxs-lookup"><span data-stu-id="d4b17-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="d4b17-113">无需更改的自动生成的代码以使它们适合准则中的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="d4b17-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="d4b17-114">布局约定</span><span class="sxs-lookup"><span data-stu-id="d4b17-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="d4b17-115">插入为空格，选项卡，然后使用智能缩进具有四个空间缩进量。</span><span class="sxs-lookup"><span data-stu-id="d4b17-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="d4b17-116">使用**错落有致 （重新格式化） 的代码**重新格式化你在代码编辑器中的代码。</span><span class="sxs-lookup"><span data-stu-id="d4b17-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="d4b17-117">有关详细信息，请参阅[选项，文本编辑器，基本 (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="d4b17-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="d4b17-118">使用每行只有一条语句。</span><span class="sxs-lookup"><span data-stu-id="d4b17-118">Use only one statement per line.</span></span> <span data-ttu-id="d4b17-119">不要使用 Visual Basic 行分隔符字符 （:）。</span><span class="sxs-lookup"><span data-stu-id="d4b17-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="d4b17-120">避免使用该语言允许它支持隐式行继续标志显式行延续字符"_"。</span><span class="sxs-lookup"><span data-stu-id="d4b17-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="d4b17-121">使用每行只有一个声明。</span><span class="sxs-lookup"><span data-stu-id="d4b17-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="d4b17-122">如果**错落有致 （重新格式化） 的代码**不格式连续行自动、 手动缩进一个制表位的延续行。</span><span class="sxs-lookup"><span data-stu-id="d4b17-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="d4b17-123">但是，始终向左对齐列表中的项。</span><span class="sxs-lookup"><span data-stu-id="d4b17-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="d4b17-124">添加方法和属性定义之间的至少一个空白行。</span><span class="sxs-lookup"><span data-stu-id="d4b17-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="d4b17-125">注释约定</span><span class="sxs-lookup"><span data-stu-id="d4b17-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="d4b17-126">将注释放在单独的行而不是在某个代码行的末尾。</span><span class="sxs-lookup"><span data-stu-id="d4b17-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="d4b17-127">开始注释文本以大写字母，并以句点结束注释文本。</span><span class="sxs-lookup"><span data-stu-id="d4b17-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="d4b17-128">插入注释分隔符 （'） 和注释文本之间的一个空格。</span><span class="sxs-lookup"><span data-stu-id="d4b17-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   <span data-ttu-id="d4b17-129">不环绕与格式化的星号块的注释。</span><span class="sxs-lookup"><span data-stu-id="d4b17-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="d4b17-130">程序结构</span><span class="sxs-lookup"><span data-stu-id="d4b17-130">Program Structure</span></span>  
  
-   <span data-ttu-id="d4b17-131">当你使用`Main`方法，默认构造用于新控制台应用程序，并使用`My`命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="d4b17-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="d4b17-132">语言准则</span><span class="sxs-lookup"><span data-stu-id="d4b17-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="d4b17-133">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="d4b17-133">String Data Type</span></span>  
  
-   <span data-ttu-id="d4b17-134">若要连接字符串，使用与号 (&)。</span><span class="sxs-lookup"><span data-stu-id="d4b17-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   <span data-ttu-id="d4b17-135">若要将追加在循环中的字符串，请使用<xref:System.Text.StringBuilder>对象。</span><span class="sxs-lookup"><span data-stu-id="d4b17-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="d4b17-136">事件处理程序中的宽松的委托</span><span class="sxs-lookup"><span data-stu-id="d4b17-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="d4b17-137">不显式计的自变量 （对象和 EventArgs） 到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d4b17-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="d4b17-138">如果你未使用事件自变量传递给事件 （例如，为对象，e 作为 EventArgs 的发送方），使用宽松的委托，并省略在代码中的事件自变量：</span><span class="sxs-lookup"><span data-stu-id="d4b17-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="d4b17-139">无符号数据类型</span><span class="sxs-lookup"><span data-stu-id="d4b17-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="d4b17-140">使用`Integer`而不是无符号类型，除非它们是所必需。</span><span class="sxs-lookup"><span data-stu-id="d4b17-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="d4b17-141">数组</span><span class="sxs-lookup"><span data-stu-id="d4b17-141">Arrays</span></span>  
  
-   <span data-ttu-id="d4b17-142">初始化数组在声明行上的时，请使用短的语法。</span><span class="sxs-lookup"><span data-stu-id="d4b17-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="d4b17-143">例如，使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="d4b17-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     <span data-ttu-id="d4b17-144">不要使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="d4b17-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   <span data-ttu-id="d4b17-145">把数组指示符的类型，而不在该变量。</span><span class="sxs-lookup"><span data-stu-id="d4b17-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="d4b17-146">例如，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="d4b17-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     <span data-ttu-id="d4b17-147">不要使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="d4b17-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   <span data-ttu-id="d4b17-148">在声明并初始化数组的基本数据类型时，请使用 {} 语法。</span><span class="sxs-lookup"><span data-stu-id="d4b17-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="d4b17-149">例如，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="d4b17-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     <span data-ttu-id="d4b17-150">不要使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="d4b17-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="d4b17-151">使用 With 关键字</span><span class="sxs-lookup"><span data-stu-id="d4b17-151">Use the With Keyword</span></span>  
 <span data-ttu-id="d4b17-152">当你进行一系列调用对一个对象时，请考虑使用`With`关键字：</span><span class="sxs-lookup"><span data-stu-id="d4b17-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="d4b17-153">可以使用 Try...Catch 和 Using 语句时使用异常处理</span><span class="sxs-lookup"><span data-stu-id="d4b17-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="d4b17-154">不要使用`On Error Goto`。</span><span class="sxs-lookup"><span data-stu-id="d4b17-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="d4b17-155">使用 IsNot 关键字</span><span class="sxs-lookup"><span data-stu-id="d4b17-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="d4b17-156">使用`IsNot`关键字而不是`Not...Is Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d4b17-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="d4b17-157">New 关键字</span><span class="sxs-lookup"><span data-stu-id="d4b17-157">New Keyword</span></span>  
  
-   <span data-ttu-id="d4b17-158">使用短实例化。</span><span class="sxs-lookup"><span data-stu-id="d4b17-158">Use short instantiation.</span></span> <span data-ttu-id="d4b17-159">例如，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="d4b17-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     <span data-ttu-id="d4b17-160">前面的行是等效于此：</span><span class="sxs-lookup"><span data-stu-id="d4b17-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   <span data-ttu-id="d4b17-161">新对象而不是无参数构造函数中使用对象初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="d4b17-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a><span data-ttu-id="d4b17-162">事件处理</span><span class="sxs-lookup"><span data-stu-id="d4b17-162">Event Handling</span></span>  
  
-   <span data-ttu-id="d4b17-163">使用`Handles`而非`AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="d4b17-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   <span data-ttu-id="d4b17-164">使用`AddressOf`，和执行不显式实例化委托：</span><span class="sxs-lookup"><span data-stu-id="d4b17-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   <span data-ttu-id="d4b17-165">在定义事件时，使用短的语法，并让编译器定义的委托：</span><span class="sxs-lookup"><span data-stu-id="d4b17-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   <span data-ttu-id="d4b17-166">不验证事件是否是`Nothing`(null)，然后才能调用`RaiseEvent`方法。</span><span class="sxs-lookup"><span data-stu-id="d4b17-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="d4b17-167">`RaiseEvent` 检查`Nothing`它引发事件之前。</span><span class="sxs-lookup"><span data-stu-id="d4b17-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="d4b17-168">使用共享的成员</span><span class="sxs-lookup"><span data-stu-id="d4b17-168">Using Shared Members</span></span>  
 <span data-ttu-id="d4b17-169">调用`Shared`使用的类名称，不是从一个实例变量的成员。</span><span class="sxs-lookup"><span data-stu-id="d4b17-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="d4b17-170">使用 XML 文本</span><span class="sxs-lookup"><span data-stu-id="d4b17-170">Use XML Literals</span></span>  
 <span data-ttu-id="d4b17-171">XML 文本简化在使用 XML （例如，负载、 查询和转换） 时遇到的最常见任务。</span><span class="sxs-lookup"><span data-stu-id="d4b17-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="d4b17-172">当用 XML 开发时，请遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="d4b17-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="d4b17-173">使用 XML 文本来创建 XML 文档和片段，而不是直接调用 XML Api。</span><span class="sxs-lookup"><span data-stu-id="d4b17-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="d4b17-174">导入在要充分利用 XML 文本的性能优化的文件或项目级别的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="d4b17-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="d4b17-175">XML 轴属性用于访问元素和 XML 文档中的属性。</span><span class="sxs-lookup"><span data-stu-id="d4b17-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="d4b17-176">使用嵌入式的表达式包含值，从现有值，而不使用 API 调用，如创建 XML`Add`方法：</span><span class="sxs-lookup"><span data-stu-id="d4b17-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a><span data-ttu-id="d4b17-177">LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="d4b17-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="d4b17-178">使用有意义的名称对查询变量：</span><span class="sxs-lookup"><span data-stu-id="d4b17-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   <span data-ttu-id="d4b17-179">提供的查询，以确保匿名类型的属性名称都正确大写使用 Pascal 中的元素的名称的大小写：</span><span class="sxs-lookup"><span data-stu-id="d4b17-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   <span data-ttu-id="d4b17-180">如果结果中的属性名称模棱两可，请对属性重命名。</span><span class="sxs-lookup"><span data-stu-id="d4b17-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="d4b17-181">例如，如果你的查询返回客户名称和一个订单 ID，将其重命名而不是将它们保留为`Name`和`ID`结果中：</span><span class="sxs-lookup"><span data-stu-id="d4b17-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   <span data-ttu-id="d4b17-182">查询变量和范围变量的声明中使用类型推断功能：</span><span class="sxs-lookup"><span data-stu-id="d4b17-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   <span data-ttu-id="d4b17-183">对齐下的查询子句`From`语句：</span><span class="sxs-lookup"><span data-stu-id="d4b17-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   <span data-ttu-id="d4b17-184">使用`Where`子句之前其他查询子句，以便更高版本的查询子句作用于筛选的数据集：</span><span class="sxs-lookup"><span data-stu-id="d4b17-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   <span data-ttu-id="d4b17-185">使用`Join`子句显式定义联接操作而不是使用`Where`子句隐式定义联接操作：</span><span class="sxs-lookup"><span data-stu-id="d4b17-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d4b17-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4b17-186">See Also</span></span>  
 [<span data-ttu-id="d4b17-187">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="d4b17-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
