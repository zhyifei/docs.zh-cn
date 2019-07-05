---
title: 如何：使用 Visual C# 功能访问 Office 互操作对象 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- optional parameters [C#], Office programming
- named and optional arguments [C#], Office programming
- dynamic [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
- Office programming [C#]
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
ms.openlocfilehash: 765a150953075cf9afb2dd3bde7a66cfe3ff6eb5
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398167"
---
# <a name="how-to-access-office-interop-objects-by-using-visual-c-features-c-programming-guide"></a><span data-ttu-id="1365c-102">如何：使用 Visual C# 功能访问 Office 互操作对象（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1365c-102">How to: Access Office Interop Objects by Using Visual C# Features (C# Programming Guide)</span></span>

<span data-ttu-id="1365c-103">Visual C# 具有一些功能，可简化对 Office API 对象的访问。</span><span class="sxs-lookup"><span data-stu-id="1365c-103">Visual C# has features that simplify access to Office API objects.</span></span> <span data-ttu-id="1365c-104">这些新功能包括命名实参和可选实参、名为 `dynamic` 的新类型，以及在 COM 方法中将实参传递为引用形参（就像它们是值形参）的功能。</span><span class="sxs-lookup"><span data-stu-id="1365c-104">The new features include named and optional arguments, a new type called `dynamic`, and the ability to pass arguments to reference parameters in COM methods as if they were value parameters.</span></span>

<span data-ttu-id="1365c-105">在本主题中，你将利用这些新功能来编写创建并显示 Microsoft Office Excel 工作表的代码。</span><span class="sxs-lookup"><span data-stu-id="1365c-105">In this topic you will use the new features to write code that creates and displays a Microsoft Office Excel worksheet.</span></span> <span data-ttu-id="1365c-106">然后，你将编写添加包含链接到 Excel 工作表的图标的 Office Word 文档的代码。</span><span class="sxs-lookup"><span data-stu-id="1365c-106">You will then write code to add an Office Word document that contains an icon that is linked to the Excel worksheet.</span></span>

<span data-ttu-id="1365c-107">若要完成本演练，你的计算机上必须安装 Microsoft Office Excel 2007 和 Microsoft Office Word 2007 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1365c-107">To complete this walkthrough, you must have Microsoft Office Excel 2007 and Microsoft Office Word 2007, or later versions, installed on your computer.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a><span data-ttu-id="1365c-108">创建新的控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="1365c-108">To create a new console application</span></span>

1. <span data-ttu-id="1365c-109">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="1365c-109">Start Visual Studio.</span></span>

2. <span data-ttu-id="1365c-110">在 **“文件”** 菜单上，指向 **“新建”** ，然后单击 **“项目”** 。</span><span class="sxs-lookup"><span data-stu-id="1365c-110">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="1365c-111">此时将出现“新建项目”  对话框。</span><span class="sxs-lookup"><span data-stu-id="1365c-111">The **New Project** dialog box appears.</span></span>

3. <span data-ttu-id="1365c-112">在“已安装的模板”  窗格中，展开“Visual C#”  ，然后单击“Windows”  。</span><span class="sxs-lookup"><span data-stu-id="1365c-112">In the **Installed Templates** pane, expand **Visual C#**, and then click **Windows**.</span></span>

4. <span data-ttu-id="1365c-113">查看“新建项目”  对话框的顶部，确保“.NET Framework 4”  （或更高版本）选为目标框架。</span><span class="sxs-lookup"><span data-stu-id="1365c-113">Look at the top of the **New Project** dialog box to make sure that **.NET Framework 4** (or later version) is selected as a target framework.</span></span>

5. <span data-ttu-id="1365c-114">在“模板”  窗格中，单击“控制台应用程序”  。</span><span class="sxs-lookup"><span data-stu-id="1365c-114">In the **Templates** pane, click **Console Application**.</span></span>

6. <span data-ttu-id="1365c-115">在“名称”  字段中键入项目的名称。</span><span class="sxs-lookup"><span data-stu-id="1365c-115">Type a name for your project in the **Name** field.</span></span>

7. <span data-ttu-id="1365c-116">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="1365c-116">Click **OK**.</span></span>

     <span data-ttu-id="1365c-117">新项目将出现在“解决方案资源管理器”  中。</span><span class="sxs-lookup"><span data-stu-id="1365c-117">The new project appears in **Solution Explorer**.</span></span>

## <a name="to-add-references"></a><span data-ttu-id="1365c-118">添加引用</span><span class="sxs-lookup"><span data-stu-id="1365c-118">To add references</span></span>

1. <span data-ttu-id="1365c-119">在“解决方案资源管理器”  中，右键单击你的项目名称，然后单击“添加引用”  。</span><span class="sxs-lookup"><span data-stu-id="1365c-119">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="1365c-120">此时会显示“添加引用”  对话框。</span><span class="sxs-lookup"><span data-stu-id="1365c-120">The **Add Reference** dialog box appears.</span></span>

2. <span data-ttu-id="1365c-121">在“程序集”  页上，在“组件名称”  列表中选择“Microsoft.Office.Interop.Word”  ，然后按住 Ctrl 键并选择“Microsoft.Office.Interop.Excel”  。</span><span class="sxs-lookup"><span data-stu-id="1365c-121">On the **Assemblies**  page, select **Microsoft.Office.Interop.Word** in the **Component Name** list, and then hold down the CTRL key and select **Microsoft.Office.Interop.Excel**.</span></span>  <span data-ttu-id="1365c-122">如果看不到程序集，可能需要确保它们已安装并显示（请参阅[操作说明：安装 Office 主互操作程序集](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies)）</span><span class="sxs-lookup"><span data-stu-id="1365c-122">If you do not see the assemblies, you may need to ensure they are installed and displayed (see [How to: Install Office Primary Interop Assemblies](/visualstudio/vsto/how-to-install-office-primary-interop-assemblies))</span></span>

3. <span data-ttu-id="1365c-123">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="1365c-123">Click **OK**.</span></span>

## <a name="to-add-necessary-using-directives"></a><span data-ttu-id="1365c-124">添加必要的 using 指令</span><span class="sxs-lookup"><span data-stu-id="1365c-124">To add necessary using directives</span></span>

1. <span data-ttu-id="1365c-125">在“解决方案资源管理器”  中，右键单击“Program.cs”  文件，然后单击“查看代码”  。</span><span class="sxs-lookup"><span data-stu-id="1365c-125">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>

2. <span data-ttu-id="1365c-126">将以下 `using` 指令添加到代码文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="1365c-126">Add the following `using` directives to the top of the code file.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#1)]

## <a name="to-create-a-list-of-bank-accounts"></a><span data-ttu-id="1365c-127">创建银行帐户列表</span><span class="sxs-lookup"><span data-stu-id="1365c-127">To create a list of bank accounts</span></span>

1. <span data-ttu-id="1365c-128">将以下类定义粘贴到“Program.cs”  中的 `Program` 类下。</span><span class="sxs-lookup"><span data-stu-id="1365c-128">Paste the following class definition into **Program.cs**, under the `Program` class.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#2)]

2. <span data-ttu-id="1365c-129">将以下代码添加到 `Main` 方法，以创建包含两个帐户的 `bankAccounts` 列表。</span><span class="sxs-lookup"><span data-stu-id="1365c-129">Add the following code to the `Main` method to create a `bankAccounts` list that contains two accounts.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#3)]

## <a name="to-declare-a-method-that-exports-account-information-to-excel"></a><span data-ttu-id="1365c-130">声明将帐户信息导出到 Excel 的方法</span><span class="sxs-lookup"><span data-stu-id="1365c-130">To declare a method that exports account information to Excel</span></span>

1. <span data-ttu-id="1365c-131">将以下方法添加到 `Program` 类以设置 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="1365c-131">Add the following method to the `Program` class to set up an Excel worksheet.</span></span>

     <span data-ttu-id="1365c-132">方法 <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> 有一个可选参数，用于指定特定的模板。</span><span class="sxs-lookup"><span data-stu-id="1365c-132">Method <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> has an optional parameter for specifying a particular template.</span></span> <span data-ttu-id="1365c-133">如果希望使用形参的默认值，你可以借助可选形参（C# 4 中新增）忽略该形参的实参。</span><span class="sxs-lookup"><span data-stu-id="1365c-133">Optional parameters, new in C# 4, enable you to omit the argument for that parameter if you want to use the parameter's default value.</span></span> <span data-ttu-id="1365c-134">由于以下代码中未发送任何参数，`Add` 将使用默认模板并创建新的工作簿。</span><span class="sxs-lookup"><span data-stu-id="1365c-134">Because no argument is sent in the following code, `Add` uses the default template and creates a new workbook.</span></span> <span data-ttu-id="1365c-135">C# 早期版本中的等效语句要求提供一个占位符参数：`ExcelApp.Workbooks.Add(Type.Missing)`。</span><span class="sxs-lookup"><span data-stu-id="1365c-135">The equivalent statement in earlier versions of C# requires a placeholder argument: `ExcelApp.Workbooks.Add(Type.Missing)`.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#4)]

2. <span data-ttu-id="1365c-136">在 `DisplayInExcel` 的末尾添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="1365c-136">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="1365c-137">代码将值插入工作表第一行的前两列。</span><span class="sxs-lookup"><span data-stu-id="1365c-137">The code inserts values into the first two columns of the first row of the worksheet.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#5)]

3. <span data-ttu-id="1365c-138">在 `DisplayInExcel` 的末尾添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="1365c-138">Add the following code at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="1365c-139">`foreach` 循环将帐户列表中的信息放入工作表连续行的前两列。</span><span class="sxs-lookup"><span data-stu-id="1365c-139">The `foreach` loop puts the information from the list of accounts into the first two columns of successive rows of the worksheet.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#7)]

4. <span data-ttu-id="1365c-140">在 `DisplayInExcel` 的末尾添加以下代码以将列宽调整为适合内容。</span><span class="sxs-lookup"><span data-stu-id="1365c-140">Add the following code at the end of `DisplayInExcel` to adjust the column widths to fit the content.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#13)]

     <span data-ttu-id="1365c-141">早期版本的 C# 要求显式强制转换这些操作，因为 `ExcelApp.Columns[1]` 返回 `Object` 且 `AutoFit` 为 Excel <xref:Microsoft.Office.Interop.Excel.Range> 方法。</span><span class="sxs-lookup"><span data-stu-id="1365c-141">Earlier versions of C# require explicit casting for these operations because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel <xref:Microsoft.Office.Interop.Excel.Range> method.</span></span> <span data-ttu-id="1365c-142">以下各行显示强制转换。</span><span class="sxs-lookup"><span data-stu-id="1365c-142">The following lines show the casting.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

     <span data-ttu-id="1365c-143">C# 4 及更高版本自动将返回的 `Object` 转换为 `dynamic`，前提是程序集由 [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 编译器选项引用，或 Excel 的“嵌入互操作类型”  属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="1365c-143">C# 4, and later versions, converts the returned `Object` to `dynamic` automatically if the assembly is referenced by the [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) compiler option or, equivalently, if the Excel **Embed Interop Types** property is set to true.</span></span> <span data-ttu-id="1365c-144">True 是此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="1365c-144">True is the default value for this property.</span></span>

## <a name="to-run-the-project"></a><span data-ttu-id="1365c-145">运行项目</span><span class="sxs-lookup"><span data-stu-id="1365c-145">To run the project</span></span>

1. <span data-ttu-id="1365c-146">在 `Main` 的末尾添加以下行。</span><span class="sxs-lookup"><span data-stu-id="1365c-146">Add the following line at the end of `Main`.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#8)]

2. <span data-ttu-id="1365c-147">按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="1365c-147">Press CTRL+F5.</span></span>

     <span data-ttu-id="1365c-148">出现包含两个帐户数据的 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="1365c-148">An Excel worksheet appears that contains the data from the two accounts.</span></span>

## <a name="to-add-a-word-document"></a><span data-ttu-id="1365c-149">添加 Word 文档</span><span class="sxs-lookup"><span data-stu-id="1365c-149">To add a Word document</span></span>

1. <span data-ttu-id="1365c-150">为了说明 C# 4 及更高版本增强 Office 编程的其他方法，以下代码将打开 Word 应用程序，并创建一个链接到 Excel 工作表的图标。</span><span class="sxs-lookup"><span data-stu-id="1365c-150">To illustrate additional ways in which C# 4, and later versions, enhances Office programming, the following code opens a Word application and creates an icon that links to the Excel worksheet.</span></span>

     <span data-ttu-id="1365c-151">将方法 `CreateIconInWordDoc`（在此步骤后面提供）粘贴到 `Program` 类中。</span><span class="sxs-lookup"><span data-stu-id="1365c-151">Paste method `CreateIconInWordDoc`, provided later in this step, into the `Program` class.</span></span> <span data-ttu-id="1365c-152">`CreateIconInWordDoc` 使用命名参数和可选参数来降低对 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> 和 <xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A> 方法调用的复杂性。</span><span class="sxs-lookup"><span data-stu-id="1365c-152">`CreateIconInWordDoc` uses named and optional arguments to reduce the complexity of the method calls to <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> and <xref:Microsoft.Office.Interop.Word.Selection.PasteSpecial%2A>.</span></span> <span data-ttu-id="1365c-153">这些调用合并了 C# 4 中引入的其他两项新功能，简化了对具有引用参数的 COM 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="1365c-153">These calls incorporate two other new features introduced in C# 4 that simplify calls to COM methods that have reference parameters.</span></span> <span data-ttu-id="1365c-154">首先，你可以将实参发送到引用形参，就像它们是值形参一样。</span><span class="sxs-lookup"><span data-stu-id="1365c-154">First, you can send arguments to the reference parameters as if they were value parameters.</span></span> <span data-ttu-id="1365c-155">即，你可以直接发送值，而无需为每个引用参数创建变量。</span><span class="sxs-lookup"><span data-stu-id="1365c-155">That is, you can send values directly, without creating a variable for each reference parameter.</span></span> <span data-ttu-id="1365c-156">编译器会生成临时变量以保存参数值，并将在你从调用返回时丢弃变量。</span><span class="sxs-lookup"><span data-stu-id="1365c-156">The compiler generates temporary variables to hold the argument values, and discards the variables when you return from the call.</span></span> <span data-ttu-id="1365c-157">其次，你可以忽略参数列表中的 `ref` 关键字。</span><span class="sxs-lookup"><span data-stu-id="1365c-157">Second, you can omit the `ref` keyword in the argument list.</span></span>

     <span data-ttu-id="1365c-158">`Add` 方法有四个引用参数，所有引用参数都是可选的。</span><span class="sxs-lookup"><span data-stu-id="1365c-158">The `Add` method has four reference parameters, all of which are optional.</span></span> <span data-ttu-id="1365c-159">在 C# 4.0 以及更高版本中，如果希望使用其默认值，可以忽略任何或所有形参的实参。</span><span class="sxs-lookup"><span data-stu-id="1365c-159">In C# 4.0 and later versions, you can omit arguments for any or all of the parameters if you want to use their default values.</span></span> <span data-ttu-id="1365c-160">在 C# 3.0 以及更早版本中，由于形参是引用形参，因此必须为每个形参提供实参且实参必须是变量。</span><span class="sxs-lookup"><span data-stu-id="1365c-160">In C# 3.0 and earlier versions, an argument must be provided for each parameter, and the argument must be a variable because the parameters are reference parameters.</span></span>

     <span data-ttu-id="1365c-161">`PasteSpecial` 方法可插入剪贴板的内容。</span><span class="sxs-lookup"><span data-stu-id="1365c-161">The `PasteSpecial` method inserts the contents of the Clipboard.</span></span> <span data-ttu-id="1365c-162">该方法有七个引用参数，所有引用参数都是可选的。</span><span class="sxs-lookup"><span data-stu-id="1365c-162">The method has seven reference parameters, all of which are optional.</span></span> <span data-ttu-id="1365c-163">以下代码为其中两个形参指定实参：`Link` 用于创建指向剪贴板内容源的链接，`DisplayAsIcon` 用于将链接显示为图标。</span><span class="sxs-lookup"><span data-stu-id="1365c-163">The following code specifies arguments for two of them: `Link`, to create a link to the source of the Clipboard contents, and `DisplayAsIcon`, to display the link as an icon.</span></span> <span data-ttu-id="1365c-164">在 C# 4.0 以及更高版本中，你可以对其中两个形参使用命名实参而忽略其他形参。</span><span class="sxs-lookup"><span data-stu-id="1365c-164">In C# 4.0 and later versions, you can use named arguments for those two and omit the others.</span></span> <span data-ttu-id="1365c-165">尽管这些是引用形参，你也不必使用 `ref` 关键字，或者创建变量以实参形式发送。</span><span class="sxs-lookup"><span data-stu-id="1365c-165">Although these are reference parameters, you do not have to use the `ref` keyword, or to create variables to send in as arguments.</span></span> <span data-ttu-id="1365c-166">你可以直接发送值。</span><span class="sxs-lookup"><span data-stu-id="1365c-166">You can send the values directly.</span></span> <span data-ttu-id="1365c-167">在 C# 3.0 以及早期版本中，你必须为每个引用形参提供变量实参。</span><span class="sxs-lookup"><span data-stu-id="1365c-167">In C# 3.0 and earlier versions, you must supply a variable argument for each reference parameter.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#9)]

     <span data-ttu-id="1365c-168">在 C# 3.0 以及早期版本中的语言中，需要以下更复杂的代码。</span><span class="sxs-lookup"><span data-stu-id="1365c-168">In C# 3.0 and earlier versions of the language, the following more complex code is required.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#10)]

2. <span data-ttu-id="1365c-169">在 `Main` 的末尾添加以下语句。</span><span class="sxs-lookup"><span data-stu-id="1365c-169">Add the following statement at the end of `Main`.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#11)]

3. <span data-ttu-id="1365c-170">在 `DisplayInExcel` 的末尾添加以下语句。</span><span class="sxs-lookup"><span data-stu-id="1365c-170">Add the following statement at the end of `DisplayInExcel`.</span></span> <span data-ttu-id="1365c-171">`Copy` 方法可将工作表添加到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="1365c-171">The `Copy` method adds the worksheet to the Clipboard.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#12)]

4. <span data-ttu-id="1365c-172">按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="1365c-172">Press CTRL+F5.</span></span>

     <span data-ttu-id="1365c-173">将出现包含图标的 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="1365c-173">A Word document appears that contains an icon.</span></span> <span data-ttu-id="1365c-174">双击该图标以将工作表置于前台。</span><span class="sxs-lookup"><span data-stu-id="1365c-174">Double-click the icon to bring the worksheet to the foreground.</span></span>

## <a name="to-set-the-embed-interop-types-property"></a><span data-ttu-id="1365c-175">设置嵌入互操作类型属性</span><span class="sxs-lookup"><span data-stu-id="1365c-175">To set the Embed Interop Types property</span></span>

1. <span data-ttu-id="1365c-176">当调用运行时不需要主互操作程序集 (PIA) 的 COM 类型时，可能实现其他增强。</span><span class="sxs-lookup"><span data-stu-id="1365c-176">Additional enhancements are possible when you call a COM type that does not require a primary interop assembly (PIA) at run time.</span></span> <span data-ttu-id="1365c-177">删除 PIA 的依赖项可实现版本独立性并且更易于部署。</span><span class="sxs-lookup"><span data-stu-id="1365c-177">Removing the dependency on PIAs results in version independence and easier deployment.</span></span> <span data-ttu-id="1365c-178">若要详细了解不使用 PIA 编程的优势，请参阅[演练：嵌入托管程序集中的类型](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="1365c-178">For more information about the advantages of programming without PIAs, see [Walkthrough: Embedding Types from Managed Assemblies](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md).</span></span>

     <span data-ttu-id="1365c-179">此外，由于可以通过使用类型 `dynamic`（而非 `Object`）表示 COM 方法必需并返回的类型，因此更易于编程。</span><span class="sxs-lookup"><span data-stu-id="1365c-179">In addition, programming is easier because the types that are required and returned by COM methods can be represented by using the type `dynamic` instead of `Object`.</span></span> <span data-ttu-id="1365c-180">具有类型 `dynamic` 的变量在运行时以前均不会计算，从而消除了显式强制转换的需要。</span><span class="sxs-lookup"><span data-stu-id="1365c-180">Variables that have type `dynamic` are not evaluated until run time, which eliminates the need for explicit casting.</span></span> <span data-ttu-id="1365c-181">有关更多信息，请参见[使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)。</span><span class="sxs-lookup"><span data-stu-id="1365c-181">For more information, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>

     <span data-ttu-id="1365c-182">在 C# 4 中，默认行为是嵌入类型信息，而不是使用 PIA。</span><span class="sxs-lookup"><span data-stu-id="1365c-182">In C# 4, embedding type information instead of using PIAs is default behavior.</span></span> <span data-ttu-id="1365c-183">由于该默认行为，因此不需要显式强制转换，之前的几个示例也得到简化。</span><span class="sxs-lookup"><span data-stu-id="1365c-183">Because of that default, several of the previous examples are simplified because explicit casting is not required.</span></span> <span data-ttu-id="1365c-184">例如，`worksheet` 中 `DisplayInExcel` 的声明会写为 `Excel._Worksheet workSheet = excelApp.ActiveSheet` 而非 `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`。</span><span class="sxs-lookup"><span data-stu-id="1365c-184">For example, the declaration of `worksheet` in `DisplayInExcel` is written as `Excel._Worksheet workSheet = excelApp.ActiveSheet` rather than `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`.</span></span> <span data-ttu-id="1365c-185">在相同方法中对 `AutoFit` 的调用还将要求在不进行默认行为的情况下显式强制转换，因为 `ExcelApp.Columns[1]` 返回 `Object`，并且 `AutoFit` 为 Excel 方法。</span><span class="sxs-lookup"><span data-stu-id="1365c-185">The calls to `AutoFit` in the same method also would require explicit casting without the default, because `ExcelApp.Columns[1]` returns an `Object`, and `AutoFit` is an Excel  method.</span></span> <span data-ttu-id="1365c-186">以下代码显示强制转换。</span><span class="sxs-lookup"><span data-stu-id="1365c-186">The following code shows the casting.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#14)]

2. <span data-ttu-id="1365c-187">若要更改默认行为并使用 PIA 代替嵌入类型信息，请展开“解决方案资源管理器”  中的“引用”  节点，然后选择“Microsoft.Office.Interop.Excel”  或“Microsoft.Office.Interop.Word”  。</span><span class="sxs-lookup"><span data-stu-id="1365c-187">To change the default and use PIAs instead of embedding type information, expand the **References** node in **Solution Explorer** and then select **Microsoft.Office.Interop.Excel** or **Microsoft.Office.Interop.Word**.</span></span>

3. <span data-ttu-id="1365c-188">如果看不到“属性”  窗口，请按“F4”  。</span><span class="sxs-lookup"><span data-stu-id="1365c-188">If you cannot see the **Properties** window, press **F4**.</span></span>

4. <span data-ttu-id="1365c-189">在属性列表中找到“嵌入互操作类型”  ，将其值更改为“False”  。</span><span class="sxs-lookup"><span data-stu-id="1365c-189">Find **Embed Interop Types** in the list of properties, and change its value to **False**.</span></span> <span data-ttu-id="1365c-190">同样地，你还可以通过在命令提示符下使用 [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 编译器选项代替 [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 进行编译。</span><span class="sxs-lookup"><span data-stu-id="1365c-190">Equivalently, you can compile by using the [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option instead of [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) at a command prompt.</span></span>

## <a name="to-add-additional-formatting-to-the-table"></a><span data-ttu-id="1365c-191">将其他格式添加到表格</span><span class="sxs-lookup"><span data-stu-id="1365c-191">To add additional formatting to the table</span></span>

1. <span data-ttu-id="1365c-192">将在 `AutoFit` 中对 `DisplayInExcel` 的两个调用替换为以下语句。</span><span class="sxs-lookup"><span data-stu-id="1365c-192">Replace the two calls to `AutoFit` in `DisplayInExcel` with the following statement.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#15)]

     <span data-ttu-id="1365c-193"><xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> 方法有七个值参数，所有引用参数都是可选的。</span><span class="sxs-lookup"><span data-stu-id="1365c-193">The <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method has seven value parameters, all of which are optional.</span></span> <span data-ttu-id="1365c-194">使用命名自变量和可选自变量，你可以为这些自变量中的所有或部分提供自变量，也可以不为它们中的任何一个提供。</span><span class="sxs-lookup"><span data-stu-id="1365c-194">Named and optional arguments enable you to provide arguments for none, some, or all of them.</span></span> <span data-ttu-id="1365c-195">在上一条语句中，仅为其中一个形参 `Format` 提供实参。</span><span class="sxs-lookup"><span data-stu-id="1365c-195">In the previous statement, an argument is supplied for only one of the parameters, `Format`.</span></span> <span data-ttu-id="1365c-196">由于 `Format` 是参数列表中的第一个参数，因此无需提供参数名称。</span><span class="sxs-lookup"><span data-stu-id="1365c-196">Because `Format` is the first parameter in the parameter list, you do not have to provide the parameter name.</span></span> <span data-ttu-id="1365c-197">但是，如果包含参数名称，语句则可能更易于理解，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="1365c-197">However, the statement might be easier to understand if the parameter name is included, as is shown in the following code.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#16)]

2. <span data-ttu-id="1365c-198">按 Ctrl+F5 查看结果。</span><span class="sxs-lookup"><span data-stu-id="1365c-198">Press CTRL+F5 to see the result.</span></span> <span data-ttu-id="1365c-199">其他格式在 <xref:Microsoft.Office.Interop.Excel.XlRangeAutoFormat> 枚举中列出。</span><span class="sxs-lookup"><span data-stu-id="1365c-199">Other formats are listed in the <xref:Microsoft.Office.Interop.Excel.XlRangeAutoFormat> enumeration.</span></span>

3. <span data-ttu-id="1365c-200">将步骤 1 中的语句与以下代码比较（以下代码显示 C# 3.0 以及早期版本中要求的参数）。</span><span class="sxs-lookup"><span data-stu-id="1365c-200">Compare the statement in step 1 with the following code, which shows the arguments that are required in C# 3.0 and earlier versions.</span></span>

     [!code-csharp[csProgGuideOfficeHowTo#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/program.cs#17)]

## <a name="example"></a><span data-ttu-id="1365c-201">示例</span><span class="sxs-lookup"><span data-stu-id="1365c-201">Example</span></span>

<span data-ttu-id="1365c-202">以下代码显示完整示例。</span><span class="sxs-lookup"><span data-stu-id="1365c-202">The following code shows the complete example.</span></span>

[!code-csharp[csProgGuideOfficeHowTo#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideofficehowto/cs/walkthrough.cs#18)]

## <a name="see-also"></a><span data-ttu-id="1365c-203">请参阅</span><span class="sxs-lookup"><span data-stu-id="1365c-203">See also</span></span>

- <xref:System.Type.Missing?displayProperty=nameWithType>
- [<span data-ttu-id="1365c-204">dynamic</span><span class="sxs-lookup"><span data-stu-id="1365c-204">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)
- [<span data-ttu-id="1365c-205">使用类型 dynamic</span><span class="sxs-lookup"><span data-stu-id="1365c-205">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="1365c-206">命名参数和可选参数</span><span class="sxs-lookup"><span data-stu-id="1365c-206">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="1365c-207">如何：在 Office 编程中使用命名参数和可选参数</span><span class="sxs-lookup"><span data-stu-id="1365c-207">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
