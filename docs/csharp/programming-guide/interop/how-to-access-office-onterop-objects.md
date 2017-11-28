---
title: "如何：通过使用 Visual C# 功能访问 Office 互操作对象（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- optional parameters [C#], Office programming
- named and optional arguments [C#], Office programming
- dynamic [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
- Office programming [C#]
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
caps.latest.revision: "33"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 25e83195d5f0d8a49e402a5a32e61940960b052a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-office-interop-objects-by-using-visual-c-features-c-programming-guide"></a><span data-ttu-id="fbb31-102">如何：通过使用 Visual C# 功能访问 Office 互操作对象（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fbb31-102">How to: Access Office Interop Objects by Using Visual C# Features (C# Programming Guide)</span></span>
<span data-ttu-id="fbb31-103">Visual C# 具有一些功能，可简化对 Office API 对象的访问。</span><span class="sxs-lookup"><span data-stu-id="fbb31-103">Visual C# has features that simplify access to Office API objects.</span></span> <span data-ttu-id="fbb31-104">这些新功能包括命名实参和可选实参、名为 `dynamic` 的新类型，以及在 COM 方法中将实参传递为引用形参（就像它们是值形参）的功能。</span><span class="sxs-lookup"><span data-stu-id="fbb31-104">The new features include named and optional arguments, a new type called `dynamic`, and the ability to pass arguments to reference parameters in COM methods as if they were value parameters.</span></span>  
  
 <span data-ttu-id="fbb31-105">在本主题中，你将利用这些新功能来编写创建并显示 Microsoft Office Excel 工作表的代码。</span><span class="sxs-lookup"><span data-stu-id="fbb31-105">In this topic you will use the new features to write code that creates and displays a Microsoft Office Excel worksheet.</span></span> <span data-ttu-id="fbb31-106">然后，你将编写添加包含链接到 Excel 工作表的图标的 Office Word 文档的代码。</span><span class="sxs-lookup"><span data-stu-id="fbb31-106">You will then write code to add an Office Word document that contains an icon that is linked to the Excel worksheet.</span></span>  
  
 <span data-ttu-id="fbb31-107">若要完成本演练，你的计算机上必须安装 Microsoft Office Excel 2007 和 Microsoft Office Word 2007 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fbb31-107">To complete this walkthrough, you must have Microsoft Office Excel 2007 and Microsoft Office Word 2007, or later versions, installed on your computer.</span></span>  
  
 <span data-ttu-id="fbb31-108">如果你使用的操作系统早于 [!INCLUDE[windowsver](~/includes/windowsver-md.md)]，请确保安装 [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fbb31-108">If you are using an operating system that is older than [!INCLUDE[windowsver](~/includes/windowsver-md.md)], make sure that [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] is installed.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a><span data-ttu-id="fbb31-109">创建新的控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="fbb31-109">To create a new console application</span></span>  
  
1.  <span data-ttu-id="fbb31-110">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fbb31-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="fbb31-111">在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="fbb31-111">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="fbb31-112">此时将出现 **“新建项目”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="fbb31-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="fbb31-113">在“已安装的模板”窗格中，展开“Visual C#”，然后单击“Windows”。</span><span class="sxs-lookup"><span data-stu-id="fbb31-113">In the **Installed Templates** pane, expand **Visual C#**, and then click **Windows**.</span></span>  
  
4.  <span data-ttu-id="fbb31-114">查看“新建项目”对话框的顶部，确保“.NET Framework 4”（或更高版本）选为目标框架。</span><span class="sxs-lookup"><span data-stu-id="fbb31-114">Look at the top of the **New Project** dialog box to make sure that **.NET Framework 4** (or later version) is selected as a target framework.</span></span>  
  
5.  <span data-ttu-id="fbb31-115">在“模板”窗格中，单击“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="fbb31-115">In the **Templates** pane, click **Console Application**.</span></span>  
  
6.  <span data-ttu-id="fbb31-116">在“名称”字段中键入项目的名称。</span><span class="sxs-lookup"><span data-stu-id="fbb31-116">Type a name for your project in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="fbb31-117">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fbb31-117">Click **OK**.</span></span>  
  
     <span data-ttu-id="fbb31-118">新项目将出现在“解决方案资源管理器”中。</span><span class="sxs-lookup"><span data-stu-id="fbb31-118">The new project appears in **Solution Explorer**.</span></span>  
  
### <a name="to-add-references"></a><span data-ttu-id="fbb31-119">添加引用</span><span class="sxs-lookup"><span data-stu-id="fbb31-119">To add references</span></span>  
  
1.  <span data-ttu-id="fbb31-120">在“解决方案资源管理器”中，右键单击你的项目名称，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="fbb31-120">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="fbb31-121">此时会显示“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="fbb31-121">The **Add Reference** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="fbb31-122">在“程序集”页上，在“组件名称”列表中选择“Microsoft.Office.Interop.Word”，然后按住 Ctrl 键并选择“Microsoft.Office.Interop.Excel”。</span><span class="sxs-lookup"><span data-stu-id="fbb31-122">On the **Assemblies**  page, select **Microsoft.Office.Interop.Word** in the **Component Name** list, and then hold down the CTRL key and select **Microsoft.Office.Interop.Excel**.</span></span>  <span data-ttu-id="fbb31-123">如果未看到程序集，你可能需要确保安装并显示它们（请参阅[如何：安装 Office 主互操作程序集](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies)）</span><span class="sxs-lookup"><span data-stu-id="fbb31-123">If you do not see the assemblies, you may need to ensure they are installed and displayed (see [How to: Install Office Primary Interop Assemblies](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies))</span></span>  
  
3.  <span data-ttu-id="fbb31-124">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fbb31-124">Click **OK**.</span></span>  
  
### <a name="to-add-necessary-using-directives"></a><span data-ttu-id="fbb31-125">添加必要的 using 指令</span><span class="sxs-lookup"><span data-stu-id="fbb31-125">To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="fbb31-126">在“解决方案资源管理器”中，右键单击“Program.cs”文件，然后单击“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="fbb31-126">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="fbb31-127">将以下 `using` 指令添加到代码文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="fbb31-127">Add the following `using` directives to the top of the code file.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_1.cs)]  
  
### <a name="to-create-a-list-of-bank-accounts"></a><span data-ttu-id="fbb31-128">创建银行帐户列表</span><span class="sxs-lookup"><span data-stu-id="fbb31-128">To create a list of bank accounts</span></span>  
  
1.  <span data-ttu-id="fbb31-129">将以下类定义粘贴到“Program.cs”中的 `Program` 类下。</span><span class="sxs-lookup"><span data-stu-id="fbb31-129">Paste the following class definition into **Program.cs**, under the `Program` class.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_2.cs)]  
  
2.  <span data-ttu-id="fbb31-130">将以下代码添加到 `Main` 方法，以创建包含两个帐户的 `bankAccounts` 列表。</span><span class="sxs-lookup"><span data-stu-id="fbb31-130">Add the following code to the `Main` method to create a `bankAccounts` list that contains two accounts.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_3.cs)]  
  
### <a name="to-declare-a-method-that-exports-account-information-to-excel"></a><span data-ttu-id="fbb31-131">声明将帐户信息导出到 Excel 的方法</span><span class="sxs-lookup"><span data-stu-id="fbb31-131">To declare a method that exports account information to Excel</span></span>  
  
1.  <span data-ttu-id="fbb31-132">将以下方法添加到 `Program` 类以设置 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="fbb31-132">Add the following method to the `Program` class to set up an Excel worksheet.</span></span>  
  
     <span data-ttu-id="fbb31-133">方法 [Add](http://go.microsoft.com/fwlink/?LinkId=210910) 有一个可选参数，用于指定特定的模板。</span><span class="sxs-lookup"><span data-stu-id="fbb31-133">Method [Add](http://go.microsoft.com/fwlink/?LinkId=210910) has an optional parameter for specifying a particular template.</span></span> <span data-ttu-id="fbb31-134">如果希望使用形参的默认值，你可以借助可选形参（[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 中新增）忽略该形参的实参。</span><span class="sxs-lookup"><span data-stu-id="fbb31-134">Optional parameters, new in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], enable you to omit the argument for that parameter if you want to use the parameter's default value.</span></span> <span data-ttu-id="fbb31-135">由于以下代码中未发送任何参数，`Add` 将使用默认模板并创建新的工作簿。</span><span class="sxs-lookup"><span data-stu-id="fbb31-135">Because no argument is sent in the following code, `Add` uses the default template and creates a new workbook.</span></span> <span data-ttu-id="fbb31-136">C# 早期版本中的等效语句要求提供一个占位符参数：`ExcelApp.Workbooks.Add(Type.Missing)`。</span><span class="sxs-lookup"><span data-stu-id="fbb31-136">The equivalent statement in earlier versions of C# requires a placeholder argument: `ExcelApp.Workbooks.Add(Type.Missing)`.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_4.cs)]  
  
2.  <span data-ttu-id="fbb31-137">在 `DisplayInExcel` 的末尾添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="fbb31-137">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="fbb31-138">代码将值插入工作表第一行的前两列。</span><span class="sxs-lookup"><span data-stu-id="fbb31-138">The code inserts values into the first two columns of the first row of the worksheet.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_5.cs)]  
  
3.  <span data-ttu-id="fbb31-139">在 `DisplayInExcel` 的末尾添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="fbb31-139">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="fbb31-140">`foreach` 循环将帐户列表中的信息放入工作表连续行的前两列。</span><span class="sxs-lookup"><span data-stu-id="fbb31-140">The `foreach` loop puts the information from the list of accounts into the first two columns of successive rows of the worksheet.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#7](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_6.cs)]  
  
4.  <span data-ttu-id="fbb31-141">在 `DisplayInExcel` 的末尾添加以下代码以将列宽调整为适合内容。</span><span class="sxs-lookup"><span data-stu-id="fbb31-141">Add the following code at the end of `DisplayInExcel` to adjust the column widths to fit the content.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#13](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_7.cs)]  
  
     <span data-ttu-id="fbb31-142">早期版本的 C# 要求显式强制转换这些操作，因为 `ExcelApp.Columns[1]` 返回 `Object`，`AutoFit` 为 Excel [Range](http://go.microsoft.com/fwlink/?LinkId=210911) 方法。</span><span class="sxs-lookup"><span data-stu-id="fbb31-142">Earlier versions of C# require explicit casting for these operations because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel [Range](http://go.microsoft.com/fwlink/?LinkId=210911) method.</span></span> <span data-ttu-id="fbb31-143">以下各行显示强制转换。</span><span class="sxs-lookup"><span data-stu-id="fbb31-143">The following lines show the casting.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]  
  
     <span data-ttu-id="fbb31-144">如果程序集由 [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 编译器选项引用或者如果 Excel 的“嵌入互操作类型”属性设置为 true，则 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 及更高版本会自动将返回的 `Object` 转换为 `dynamic`。</span><span class="sxs-lookup"><span data-stu-id="fbb31-144">[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], and later versions, converts the returned `Object` to `dynamic` automatically if the assembly is referenced by the [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) compiler option or, equivalently, if the Excel **Embed Interop Types** property is set to true.</span></span> <span data-ttu-id="fbb31-145">True 是此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="fbb31-145">True is the default value for this property.</span></span>  
  
### <a name="to-run-the-project"></a><span data-ttu-id="fbb31-146">运行项目</span><span class="sxs-lookup"><span data-stu-id="fbb31-146">To run the project</span></span>  
  
1.  <span data-ttu-id="fbb31-147">在 `Main` 的末尾添加以下行。</span><span class="sxs-lookup"><span data-stu-id="fbb31-147">Add the following line at the end of `Main`.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_9.cs)]  
  
2.  <span data-ttu-id="fbb31-148">按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="fbb31-148">Press CTRL+F5.</span></span>  
  
     <span data-ttu-id="fbb31-149">出现包含两个帐户数据的 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="fbb31-149">An Excel worksheet appears that contains the data from the two accounts.</span></span>  
  
### <a name="to-add-a-word-document"></a><span data-ttu-id="fbb31-150">添加 Word 文档</span><span class="sxs-lookup"><span data-stu-id="fbb31-150">To add a Word document</span></span>  
  
1.  <span data-ttu-id="fbb31-151">若要说明 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 以及更高版本在其他哪些方面增强了 Office 编程，可以使用以下代码打开 Word 应用程序并创建链接到 Excel 工作表的图标。</span><span class="sxs-lookup"><span data-stu-id="fbb31-151">To illustrate additional ways in which [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], and later versions, enhances Office programming, the following code opens a Word application and creates an icon that links to the Excel worksheet.</span></span>  
  
     <span data-ttu-id="fbb31-152">将方法 `CreateIconInWordDoc`（在此步骤后面提供）粘贴到 `Program` 类中。</span><span class="sxs-lookup"><span data-stu-id="fbb31-152">Paste method `CreateIconInWordDoc`, provided later in this step, into the `Program` class.</span></span> <span data-ttu-id="fbb31-153">`CreateIconInWordDoc` 使用命名参数和可选参数来降低对 [Add](http://go.microsoft.com/fwlink/?LinkId=210937) 和 [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099) 方法调用的复杂性。</span><span class="sxs-lookup"><span data-stu-id="fbb31-153">`CreateIconInWordDoc` uses named and optional arguments to reduce the complexity of the method calls to [Add](http://go.microsoft.com/fwlink/?LinkId=210937) and [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099).</span></span> <span data-ttu-id="fbb31-154">这些调用合并了其他两项新功能，这两项新功能在简化对具有引用参数的 COM 方法的调用的 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 中引入。</span><span class="sxs-lookup"><span data-stu-id="fbb31-154">These calls incorporate two other new features introduced in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] that simplify calls to COM methods that have reference parameters.</span></span> <span data-ttu-id="fbb31-155">首先，你可以将实参发送到引用形参，就像它们是值形参一样。</span><span class="sxs-lookup"><span data-stu-id="fbb31-155">First, you can send arguments to the reference parameters as if they were value parameters.</span></span> <span data-ttu-id="fbb31-156">即，你可以直接发送值，而无需为每个引用参数创建变量。</span><span class="sxs-lookup"><span data-stu-id="fbb31-156">That is, you can send values directly, without creating a variable for each reference parameter.</span></span> <span data-ttu-id="fbb31-157">编译器会生成临时变量以保存参数值，并将在你从调用返回时丢弃变量。</span><span class="sxs-lookup"><span data-stu-id="fbb31-157">The compiler generates temporary variables to hold the argument values, and discards the variables when you return from the call.</span></span> <span data-ttu-id="fbb31-158">其次，你可以忽略参数列表中的 `ref` 关键字。</span><span class="sxs-lookup"><span data-stu-id="fbb31-158">Second, you can omit the `ref` keyword in the argument list.</span></span>  
  
     <span data-ttu-id="fbb31-159">`Add` 方法有四个引用参数，所有引用参数都是可选的。</span><span class="sxs-lookup"><span data-stu-id="fbb31-159">The `Add` method has four reference parameters, all of which are optional.</span></span> <span data-ttu-id="fbb31-160">在 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 或更高版本中，如果希望使用其默认值，可以忽略任何或所有形参的实参。</span><span class="sxs-lookup"><span data-stu-id="fbb31-160">In [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], or later versions, you can omit arguments for any or all of the parameters if you want to use their default values.</span></span> <span data-ttu-id="fbb31-161">在 [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] 以及更早版本中，由于形参是引用形参，因此必须为每个形参提供实参且实参必须是变量。</span><span class="sxs-lookup"><span data-stu-id="fbb31-161">In [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] and earlier versions, an argument must be provided for each parameter, and the argument must be a variable because the parameters are reference parameters.</span></span>  
  
     <span data-ttu-id="fbb31-162">`PasteSpecial` 方法可插入剪贴板的内容。</span><span class="sxs-lookup"><span data-stu-id="fbb31-162">The `PasteSpecial` method inserts the contents of the Clipboard.</span></span> <span data-ttu-id="fbb31-163">该方法有七个引用参数，所有引用参数都是可选的。</span><span class="sxs-lookup"><span data-stu-id="fbb31-163">The method has seven reference parameters, all of which are optional.</span></span> <span data-ttu-id="fbb31-164">以下代码为其中两个形参指定实参：`Link` 用于创建指向剪贴板内容源的链接，`DisplayAsIcon` 用于将链接显示为图标。</span><span class="sxs-lookup"><span data-stu-id="fbb31-164">The following code specifies arguments for two of them: `Link`, to create a link to the source of the Clipboard contents, and `DisplayAsIcon`, to display the link as an icon.</span></span> <span data-ttu-id="fbb31-165">在 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 中，你可以对其中两个形参使用命名实参而忽略其他形参。</span><span class="sxs-lookup"><span data-stu-id="fbb31-165">In [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], you can use named arguments for those two and omit the others.</span></span> <span data-ttu-id="fbb31-166">尽管这些是引用形参，你也不必使用 `ref` 关键字，或者创建变量以实参形式发送。</span><span class="sxs-lookup"><span data-stu-id="fbb31-166">Although these are reference parameters, you do not have to use the `ref` keyword, or to create variables to send in as arguments.</span></span> <span data-ttu-id="fbb31-167">你可以直接发送值。</span><span class="sxs-lookup"><span data-stu-id="fbb31-167">You can send the values directly.</span></span> <span data-ttu-id="fbb31-168">在 [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] 以及早期版本中，你必须为每个引用形参发送变量实参。</span><span class="sxs-lookup"><span data-stu-id="fbb31-168">In [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] and earlier versions, you must send a variable argument for each reference parameter.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#9](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_10.cs)]  
  
     <span data-ttu-id="fbb31-169">在 [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] 或早期版本的语言中，需要以下更复杂的代码。</span><span class="sxs-lookup"><span data-stu-id="fbb31-169">In [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] or earlier versions of the language, the following more complex code is required.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#10](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_11.cs)]  
  
2.  <span data-ttu-id="fbb31-170">在 `Main` 的末尾添加以下语句。</span><span class="sxs-lookup"><span data-stu-id="fbb31-170">Add the following statement at the end of `Main`.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#11](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_12.cs)]  
  
3.  <span data-ttu-id="fbb31-171">在 `DisplayInExcel` 的末尾添加以下语句。</span><span class="sxs-lookup"><span data-stu-id="fbb31-171">Add the following statement at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="fbb31-172">`Copy` 方法可将工作表添加到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="fbb31-172">The `Copy` method adds the worksheet to the Clipboard.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#12](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_13.cs)]  
  
4.  <span data-ttu-id="fbb31-173">按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="fbb31-173">Press CTRL+F5.</span></span>  
  
     <span data-ttu-id="fbb31-174">将出现包含图标的 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="fbb31-174">A Word document appears that contains an icon.</span></span> <span data-ttu-id="fbb31-175">双击该图标以将工作表置于前台。</span><span class="sxs-lookup"><span data-stu-id="fbb31-175">Double-click the icon to bring the worksheet to the foreground.</span></span>  
  
### <a name="to-set-the-embed-interop-types-property"></a><span data-ttu-id="fbb31-176">设置嵌入互操作类型属性</span><span class="sxs-lookup"><span data-stu-id="fbb31-176">To set the Embed Interop Types property</span></span>  
  
1.  <span data-ttu-id="fbb31-177">当调用运行时不需要主互操作程序集 (PIA) 的 COM 类型时，可能实现其他增强。</span><span class="sxs-lookup"><span data-stu-id="fbb31-177">Additional enhancements are possible when you call a COM type that does not require a primary interop assembly (PIA) at run time.</span></span> <span data-ttu-id="fbb31-178">删除 PIA 的依赖项可实现版本独立性并且更易于部署。</span><span class="sxs-lookup"><span data-stu-id="fbb31-178">Removing the dependency on PIAs results in version independence and easier deployment.</span></span> <span data-ttu-id="fbb31-179">有关避免使用 PIA 编程的优点的详细信息，请参阅[演练：嵌入托管程序集中的类型](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)。</span><span class="sxs-lookup"><span data-stu-id="fbb31-179">For more information about the advantages of programming without PIAs, see [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
     <span data-ttu-id="fbb31-180">此外，由于可以通过使用类型 `dynamic`（而非 `Object`）表示 COM 方法必需并返回的类型，因此更易于编程。</span><span class="sxs-lookup"><span data-stu-id="fbb31-180">In addition, programming is easier because the types that are required and returned by COM methods can be represented by using the type `dynamic` instead of `Object`.</span></span> <span data-ttu-id="fbb31-181">具有类型 `dynamic` 的变量在运行时以前均不会计算，从而消除了显式强制转换的需要。</span><span class="sxs-lookup"><span data-stu-id="fbb31-181">Variables that have type `dynamic` are not evaluated until run time, which eliminates the need for explicit casting.</span></span> <span data-ttu-id="fbb31-182">有关更多信息，请参见[使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)。</span><span class="sxs-lookup"><span data-stu-id="fbb31-182">For more information, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>  
  
     <span data-ttu-id="fbb31-183">在 [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] 中，默认行为是嵌入类型信息，而不是使用 PIA。</span><span class="sxs-lookup"><span data-stu-id="fbb31-183">In [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], embedding type information instead of using PIAs is default behavior.</span></span> <span data-ttu-id="fbb31-184">由于该默认行为，因此不需要显式强制转换，之前的几个示例也得到简化。</span><span class="sxs-lookup"><span data-stu-id="fbb31-184">Because of that default, several of the previous examples are simplified because explicit casting is not required.</span></span> <span data-ttu-id="fbb31-185">例如，`worksheet` 中 `DisplayInExcel` 的声明会写为 `Excel._Worksheet workSheet = excelApp.ActiveSheet` 而非 `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`。</span><span class="sxs-lookup"><span data-stu-id="fbb31-185">For example, the declaration of `worksheet` in `DisplayInExcel` is written as `Excel._Worksheet workSheet = excelApp.ActiveSheet` rather than `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`.</span></span> <span data-ttu-id="fbb31-186">在相同方法中对 `AutoFit` 的调用还将要求在不进行默认行为的情况下显式强制转换，因为 `ExcelApp.Columns[1]` 返回 `Object`，并且 `AutoFit` 为 Excel 方法。</span><span class="sxs-lookup"><span data-stu-id="fbb31-186">The calls to `AutoFit` in the same method also would require explicit casting without the default, because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel  method.</span></span> <span data-ttu-id="fbb31-187">以下代码显示强制转换。</span><span class="sxs-lookup"><span data-stu-id="fbb31-187">The following code shows the casting.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#14](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_8.cs)]  
  
2.  <span data-ttu-id="fbb31-188">若要更改默认行为并使用 PIA 代替嵌入类型信息，请展开“解决方案资源管理器”中的“引用”节点，然后选择“Microsoft.Office.Interop.Excel”或“Microsoft.Office.Interop.Word”。</span><span class="sxs-lookup"><span data-stu-id="fbb31-188">To change the default and use PIAs instead of embedding type information, expand the **References** node in **Solution Explorer** and then select **Microsoft.Office.Interop.Excel** or **Microsoft.Office.Interop.Word**.</span></span>  
  
3.  <span data-ttu-id="fbb31-189">如果看不到“属性”窗口，请按“F4”。</span><span class="sxs-lookup"><span data-stu-id="fbb31-189">If you cannot see the **Properties** window, press **F4**.</span></span>  
  
4.  <span data-ttu-id="fbb31-190">在属性列表中找到“嵌入互操作类型”，将其值更改为“False”。</span><span class="sxs-lookup"><span data-stu-id="fbb31-190">Find **Embed Interop Types** in the list of properties, and change its value to **False**.</span></span> <span data-ttu-id="fbb31-191">同样地，你还可以通过在命令提示符下使用 [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 编译器选项代替 [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 进行编译。</span><span class="sxs-lookup"><span data-stu-id="fbb31-191">Equivalently, you can compile by using the [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option instead of [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) at a command prompt.</span></span>  
  
### <a name="to-add-additional-formatting-to-the-table"></a><span data-ttu-id="fbb31-192">将其他格式添加到表格</span><span class="sxs-lookup"><span data-stu-id="fbb31-192">To add additional formatting to the table</span></span>  
  
1.  <span data-ttu-id="fbb31-193">将在 `AutoFit` 中对 `DisplayInExcel` 的两个调用替换为以下语句。</span><span class="sxs-lookup"><span data-stu-id="fbb31-193">Replace the two calls to `AutoFit` in `DisplayInExcel` with the following statement.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#15](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_14.cs)]  
  
     <span data-ttu-id="fbb31-194">[AutoFormat](http://go.microsoft.com/fwlink/?LinkId=210948) 方法有七个值参数，所有引用参数都是可选的。</span><span class="sxs-lookup"><span data-stu-id="fbb31-194">The [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=210948) method has seven value parameters, all of which are optional.</span></span> <span data-ttu-id="fbb31-195">使用命名自变量和可选自变量，你可以为这些自变量中的所有或部分提供自变量，也可以不为它们中的任何一个提供。</span><span class="sxs-lookup"><span data-stu-id="fbb31-195">Named and optional arguments enable you to provide arguments for none, some, or all of them.</span></span> <span data-ttu-id="fbb31-196">在上一条语句中，仅为其中一个形参 `Format` 提供实参。</span><span class="sxs-lookup"><span data-stu-id="fbb31-196">In the previous statement, an argument is supplied for only one of the parameters, `Format`.</span></span> <span data-ttu-id="fbb31-197">由于 `Format` 是参数列表中的第一个参数，因此无需提供参数名称。</span><span class="sxs-lookup"><span data-stu-id="fbb31-197">Because `Format` is the first parameter in the parameter list, you do not have to provide the parameter name.</span></span> <span data-ttu-id="fbb31-198">但是，如果包含参数名称，语句则可能更易于理解，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="fbb31-198">However, the statement might be easier to understand if the parameter name is included, as is shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#16](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_15.cs)]  
  
2.  <span data-ttu-id="fbb31-199">按 Ctrl+F5 查看结果。</span><span class="sxs-lookup"><span data-stu-id="fbb31-199">Press CTRL+F5 to see the result.</span></span> <span data-ttu-id="fbb31-200">其他格式在 [XlRangeAutoFormat](http://go.microsoft.com/fwlink/?LinkId=210967) 枚举中列出。</span><span class="sxs-lookup"><span data-stu-id="fbb31-200">Other formats are listed in the [XlRangeAutoFormat](http://go.microsoft.com/fwlink/?LinkId=210967) enumeration.</span></span>  
  
3.  <span data-ttu-id="fbb31-201">将步骤 1 中的语句与以下代码比较（以下代码显示 [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] 或早期版本中要求的参数）。</span><span class="sxs-lookup"><span data-stu-id="fbb31-201">Compare the statement in step 1 with the following code, which shows the arguments that are required in [!INCLUDE[csharp_orcas_long](~/includes/csharp-orcas-long-md.md)] or earlier versions.</span></span>  
  
     [!code-csharp[csProgGuideOfficeHowTo#17](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_16.cs)]  
  
## <a name="example"></a><span data-ttu-id="fbb31-202">示例</span><span class="sxs-lookup"><span data-stu-id="fbb31-202">Example</span></span>  
 <span data-ttu-id="fbb31-203">以下代码显示完整示例。</span><span class="sxs-lookup"><span data-stu-id="fbb31-203">The following code shows the complete example.</span></span>  
  
 [!code-csharp[csProgGuideOfficeHowTo#18](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-access-office-onterop-objects_17.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fbb31-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbb31-204">See Also</span></span>  
 <xref:System.Type.Missing?displayProperty=nameWithType>  
 [<span data-ttu-id="fbb31-205">动态</span><span class="sxs-lookup"><span data-stu-id="fbb31-205">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
 [<span data-ttu-id="fbb31-206">使用类型 dynamic</span><span class="sxs-lookup"><span data-stu-id="fbb31-206">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [<span data-ttu-id="fbb31-207">命名参数和可选参数</span><span class="sxs-lookup"><span data-stu-id="fbb31-207">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
 [<span data-ttu-id="fbb31-208">如何：在 Office 编程中使用命名参数和可选参数</span><span class="sxs-lookup"><span data-stu-id="fbb31-208">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
