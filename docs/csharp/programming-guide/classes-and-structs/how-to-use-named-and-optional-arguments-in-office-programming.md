---
title: "如何：在 Office 编程中使用命名自变量和可选自变量（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c773e7a6d902b9e61e724a69c9fdf5d61606de50
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a><span data-ttu-id="bfbfa-102">如何：在 Office 编程中使用命名自变量和可选自变量（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="bfbfa-102">How to: Use Named and Optional Arguments in Office Programming (C# Programming Guide)</span></span>
<span data-ttu-id="bfbfa-103">在 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 中引入的命名参数和可选参数增强了 C# 编程中的便利性、灵活性和可读性。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-103">Named arguments and optional arguments, introduced in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], enhance convenience, flexibility, and readability in C# programming.</span></span> <span data-ttu-id="bfbfa-104">另外，这些功能显著方便了对 COM 接口（如 Microsoft Office 自动化 API）的访问。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-104">In addition, these features greatly facilitate access to COM interfaces such as the Microsoft Office automation APIs.</span></span>  
  
 <span data-ttu-id="bfbfa-105">在下面的示例中，方法 [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) 具有十六个参数，用于表示表的各种特性，例如列数和行数、格式设置、边框、字体以及颜色。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-105">In the following example, method [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) has sixteen parameters that represent characteristics of a table, such as number of columns and rows, formatting, borders, fonts, and colors.</span></span> <span data-ttu-id="bfbfa-106">由于大多数时候都不需要为所有十六个参数指定特定值，因此所有这些参数都是可选的。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-106">All sixteen parameters are optional, because most of the time you do not want to specify particular values for all of them.</span></span> <span data-ttu-id="bfbfa-107">但是，如果没有命名实参和可选实参，则必须为每个形参提供值或占位符值。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-107">However, without named and optional arguments, a value or a placeholder value has to be provided for each parameter.</span></span> <span data-ttu-id="bfbfa-108">有了命名实参和可选实参，则只需为项目所需的形参指定值。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-108">With named and optional arguments, you specify values only for the parameters that are required for your project.</span></span>  
  
 <span data-ttu-id="bfbfa-109">必须在计算机上安装 Microsoft Office Word 才能完成这些过程。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-109">You must have Microsoft Office Word installed on your computer to complete these procedures.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a><span data-ttu-id="bfbfa-110">创建新的控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="bfbfa-110">To create a new console application</span></span>  
  
1.  <span data-ttu-id="bfbfa-111">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-111">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="bfbfa-112">在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-112">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="bfbfa-113">在“模板类别”窗格中，展开“Visual C#”，然后单击“Windows”。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-113">In the **Templates Categories** pane, expand **Visual C#**, and then click **Windows**.</span></span>  
  
4.  <span data-ttu-id="bfbfa-114">查看“模板”窗格的顶部，确保“.NET Framework 4”出现在“目标框架”框中。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-114">Look in the top of the **Templates** pane to make sure that **.NET Framework 4** appears in the **Target Framework** box.</span></span>  
  
5.  <span data-ttu-id="bfbfa-115">在“模板”窗格中，单击“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-115">In the **Templates** pane, click **Console Application**.</span></span>  
  
6.  <span data-ttu-id="bfbfa-116">在“名称”字段中键入项目的名称。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-116">Type a name for your project in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="bfbfa-117">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-117">Click **OK**.</span></span>  
  
     <span data-ttu-id="bfbfa-118">新项目将出现在“解决方案资源管理器”中。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-118">The new project appears in **Solution Explorer**.</span></span>  
  
### <a name="to-add-a-reference"></a><span data-ttu-id="bfbfa-119">添加引用</span><span class="sxs-lookup"><span data-stu-id="bfbfa-119">To add a reference</span></span>  
  
1.  <span data-ttu-id="bfbfa-120">在“解决方案资源管理器”中，右键单击你的项目名称，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-120">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="bfbfa-121">此时会显示“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-121">The **Add Reference** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="bfbfa-122">在“.NET”页上的“组件名称”列表中，选择“Microsoft.Office.Interop.Word”。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-122">On the **.NET** page, select **Microsoft.Office.Interop.Word** in the **Component Name** list.</span></span>  
  
3.  <span data-ttu-id="bfbfa-123">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-123">Click **OK**.</span></span>  
  
### <a name="to-add-necessary-using-directives"></a><span data-ttu-id="bfbfa-124">添加必要的 using 指令</span><span class="sxs-lookup"><span data-stu-id="bfbfa-124">To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="bfbfa-125">在“解决方案资源管理器”中，右键单击“Program.cs”文件，然后单击“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-125">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="bfbfa-126">将以下 `using` 指令添加到代码文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-126">Add the following `using` directives to the top of the code file.</span></span>  
  
     <span data-ttu-id="bfbfa-127">[!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-127">[!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]</span></span>  
  
### <a name="to-display-text-in-a-word-document"></a><span data-ttu-id="bfbfa-128">在 Word 文档中显示文本</span><span class="sxs-lookup"><span data-stu-id="bfbfa-128">To display text in a Word document</span></span>  
  
1.  <span data-ttu-id="bfbfa-129">在 Program.cs 的 `Program` 类中，添加以下方法以创建 Word 应用程序和 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-129">In the `Program` class in Program.cs, add the following method to create a Word application and a Word document.</span></span> <span data-ttu-id="bfbfa-130">[Add](http://go.microsoft.com/fwlink/?LinkId=145381) 方法具有四个可选参数。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-130">The [Add](http://go.microsoft.com/fwlink/?LinkId=145381) method has four optional parameters.</span></span> <span data-ttu-id="bfbfa-131">此示例使用这些参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-131">This example uses their default values.</span></span> <span data-ttu-id="bfbfa-132">因此，调用语句中不必有参数。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-132">Therefore, no arguments are necessary in the calling statement.</span></span>  
  
     <span data-ttu-id="bfbfa-133">[!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-133">[!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]</span></span>  
  
2.  <span data-ttu-id="bfbfa-134">将以下代码添加到方法的末尾，以定义要在文档何处显示文本，以及要显示什么文本。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-134">Add the following code at the end of the method to define where to display text in the document, and what text to display.</span></span>  
  
     <span data-ttu-id="bfbfa-135">[!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-135">[!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]</span></span>  
  
### <a name="to-run-the-application"></a><span data-ttu-id="bfbfa-136">要运行应用程序</span><span class="sxs-lookup"><span data-stu-id="bfbfa-136">To run the application</span></span>  
  
1.  <span data-ttu-id="bfbfa-137">将以下语句添加到 Main。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-137">Add the following statement to Main.</span></span>  
  
     <span data-ttu-id="bfbfa-138">[!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-138">[!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]</span></span>  
  
2.  <span data-ttu-id="bfbfa-139">按 Ctrl+F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-139">Press CTRL+F5 to run the project.</span></span> <span data-ttu-id="bfbfa-140">此时会出现一个 Word 文档，其中包含指定的文本。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-140">A Word document appears that contains the specified text.</span></span>  
  
### <a name="to-change-the-text-to-a-table"></a><span data-ttu-id="bfbfa-141">将文本更改为表</span><span class="sxs-lookup"><span data-stu-id="bfbfa-141">To change the text to a table</span></span>  
  
1.  <span data-ttu-id="bfbfa-142">使用 `ConvertToTable` 方法将文本放入表中。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-142">Use the `ConvertToTable` method to enclose the text in a table.</span></span> <span data-ttu-id="bfbfa-143">该方法具有十六个可选参数。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-143">The method has sixteen optional parameters.</span></span> <span data-ttu-id="bfbfa-144">IntelliSense 将可选参数放入括号中，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-144">IntelliSense encloses optional parameters in brackets, as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="bfbfa-145">![ConvertToTable 方法的参数列表。](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span><span class="sxs-lookup"><span data-stu-id="bfbfa-145">![List of parameters for ConvertToTable method.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span></span>  
<span data-ttu-id="bfbfa-146">ConvertToTable 参数</span><span class="sxs-lookup"><span data-stu-id="bfbfa-146">ConvertToTable parameters</span></span>  
  
     <span data-ttu-id="bfbfa-147">通过使用命名实参和可选实参，可以只对要更改的形参指定值。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-147">Named and optional arguments enable you to specify values for only the parameters that you want to change.</span></span> <span data-ttu-id="bfbfa-148">将以下代码添加到方法 `DisplayInWord` 的末尾以创建一个简单的表。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-148">Add the following code to the end of method `DisplayInWord` to create a simple table.</span></span> <span data-ttu-id="bfbfa-149">此参数指定 `range` 中文本字符串内的逗号分隔表的各个单元格。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-149">The argument specifies that the commas in the text string in `range` separate the cells of the table.</span></span>  
  
     <span data-ttu-id="bfbfa-150">[!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-150">[!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]</span></span>  
  
     <span data-ttu-id="bfbfa-151">在 C# 早期版本中，对 `ConvertToTable` 的调用需要对每个形参使用引用实参，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-151">In earlier versions of C#, the call to `ConvertToTable` requires a reference argument for each parameter, as shown in the following code.</span></span>  
  
     <span data-ttu-id="bfbfa-152">[!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-152">[!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]</span></span>  
  
2.  <span data-ttu-id="bfbfa-153">按 Ctrl+F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-153">Press CTRL+F5 to run the project.</span></span>  
  
### <a name="to-experiment-with-other-parameters"></a><span data-ttu-id="bfbfa-154">试验其他参数</span><span class="sxs-lookup"><span data-stu-id="bfbfa-154">To experiment with other parameters</span></span>  
  
1.  <span data-ttu-id="bfbfa-155">若要更改表以使其具有一列三行，请将 `DisplayInWord` 中的最后一行替换为以下语句，然后按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-155">To change the table so that it has one column and three rows, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span>  
  
     <span data-ttu-id="bfbfa-156">[!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-156">[!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]</span></span>  
  
2.  <span data-ttu-id="bfbfa-157">若要为表指定预定义的格式，请将 `DisplayInWord` 中的最后一行替换为以下语句，然后按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-157">To specify a predefined format for the table, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span> <span data-ttu-id="bfbfa-158">格式可以为任何 [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382) 常量。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-158">The format can be any of the [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382) constants.</span></span>  
  
     <span data-ttu-id="bfbfa-159">[!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-159">[!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfbfa-160">示例</span><span class="sxs-lookup"><span data-stu-id="bfbfa-160">Example</span></span>  
 <span data-ttu-id="bfbfa-161">下面的代码包括完整的示例。</span><span class="sxs-lookup"><span data-stu-id="bfbfa-161">The following code includes the full example.</span></span>  
  
 <span data-ttu-id="bfbfa-162">[!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="bfbfa-162">[!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfbfa-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfbfa-163">See Also</span></span>  
 [<span data-ttu-id="bfbfa-164">命名参数和可选参数</span><span class="sxs-lookup"><span data-stu-id="bfbfa-164">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)

