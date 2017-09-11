---
title: "演练︰ 在 Visual Studio (Visual Basic 中) 中嵌入 Microsoft Office 程序集中的类型信息 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 26b44286-5066-4ad4-8e6a-c24902be347c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: c527941d6eae56d66cbede92ced3f66d24937354
ms.contentlocale: zh-cn
ms.lasthandoff: 05/26/2017

---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="5bf91-102">演练︰ 在 Visual Studio (Visual Basic 中) 中嵌入 Microsoft Office 程序集中的类型信息</span><span class="sxs-lookup"><span data-stu-id="5bf91-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="5bf91-103">如果在引用 COM 对象的应用程序中嵌入类型信息，则可以消除对主互操作程序集 (PIA) 的需要。</span><span class="sxs-lookup"><span data-stu-id="5bf91-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="5bf91-104">此外，嵌入的类型信息使您能够实现您的应用程序的版本独立性。</span><span class="sxs-lookup"><span data-stu-id="5bf91-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="5bf91-105">也就是说，您的程序可以编写为使用多个版本的 COM 库的类型，而无需为每个版本的一个特定的 PIA。</span><span class="sxs-lookup"><span data-stu-id="5bf91-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="5bf91-106">这是从 Microsoft Office 库使用对象的应用程序的常见方案。</span><span class="sxs-lookup"><span data-stu-id="5bf91-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="5bf91-107">嵌入类型信息，使程序可以使用不同版本的 Microsoft Office，而无需重新部署该程序或对于每个版本的 Microsoft Office PIA 的不同计算机上的相同内部版本。</span><span class="sxs-lookup"><span data-stu-id="5bf91-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="5bf91-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="5bf91-108">Prerequisites</span></span>  
 <span data-ttu-id="5bf91-109">本演练需要如下内容：</span><span class="sxs-lookup"><span data-stu-id="5bf91-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="5bf91-110">在其安装 Visual Studio 和 Microsoft Excel 的计算机。</span><span class="sxs-lookup"><span data-stu-id="5bf91-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="5bf91-111">另一台计算机在其安装.NET Framework 4 或更高版本和不同版本的 Excel。</span><span class="sxs-lookup"><span data-stu-id="5bf91-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <span data-ttu-id="5bf91-112"><a name="BKMK_createapp"></a>若要创建适用于多个版本的 Microsoft Office 的应用程序</span><span class="sxs-lookup"><span data-stu-id="5bf91-112"><a name="BKMK_createapp"></a> To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="5bf91-113">在其安装 Excel 的计算机上启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="5bf91-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="5bf91-114">在“文件” **** 菜单上，选择“新建” ****、“项目” ****。</span><span class="sxs-lookup"><span data-stu-id="5bf91-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="5bf91-115">在**新项目**对话框中，在**项目类型**窗格中，请确保**Windows**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="5bf91-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="5bf91-116">选择**控制台应用程序**中**模板**窗格。</span><span class="sxs-lookup"><span data-stu-id="5bf91-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="5bf91-117">在**名称**框中，输入`CreateExcelWorkbook`，然后选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="5bf91-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="5bf91-118">创建新项目。</span><span class="sxs-lookup"><span data-stu-id="5bf91-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="5bf91-119">打开 CreateExcelWorkbook 项目的快捷菜单，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="5bf91-119">Open the shortcut menu for the CreateExcelWorkbook project and then choose **Properties**.</span></span> <span data-ttu-id="5bf91-120">选择**引用**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5bf91-120">Choose the **References** tab.</span></span> <span data-ttu-id="5bf91-121">选择 **“添加”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="5bf91-121">Choose the **Add** button.</span></span>  
  
5.  <span data-ttu-id="5bf91-122">在**.NET**选项卡上，选择最新版本的`Microsoft.Office.Interop.Excel`。</span><span class="sxs-lookup"><span data-stu-id="5bf91-122">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="5bf91-123">例如， **Microsoft.Office.Interop.Excel 14.0.0.0**。</span><span class="sxs-lookup"><span data-stu-id="5bf91-123">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="5bf91-124">选择“确定” **** 按钮。</span><span class="sxs-lookup"><span data-stu-id="5bf91-124">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="5bf91-125">在列表中的引用的**CreateExcelWorkbook**项目中，选择为引用`Microsoft.Office.Interop.Excel`在上一步中添加。</span><span class="sxs-lookup"><span data-stu-id="5bf91-125">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="5bf91-126">在**属性**窗口中，请确保`Embed Interop Types`属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="5bf91-126">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5bf91-127">在本演练中创建的应用程序运行不同版本的 Microsoft Office 由于嵌入的互操作类型信息。</span><span class="sxs-lookup"><span data-stu-id="5bf91-127">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="5bf91-128">如果`Embed Interop Types`属性设置为`False`，必须包括每个版本的应用程序将使用运行 Microsoft Office PIA。</span><span class="sxs-lookup"><span data-stu-id="5bf91-128">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="5bf91-129">打开 Module1.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="5bf91-129">Open the Module1.vb file.</span></span> <span data-ttu-id="5bf91-130">用下面的代码替换文件中的代码︰</span><span class="sxs-lookup"><span data-stu-id="5bf91-130">Replace the code in the file with the following code:</span></span>  
  
    ```vb  
    Imports Excel = Microsoft.Office.Interop.Excel  
  
    Module Module1  
  
        Sub Main()  
            Dim values = {4, 6, 18, 2, 1, 76, 0, 3, 11}  
  
            CreateWorkbook(values, "C:\SampleFolder\SampleWorkbook.xls")  
        End Sub  
  
        Sub CreateWorkbook(ByVal values As Integer(), ByVal filePath As String)  
            Dim excelApp As Excel.Application = Nothing  
            Dim wkbk As Excel.Workbook  
            Dim sheet As Excel.Worksheet  
  
            Try  
                ' Start Excel and create a workbook and worksheet.  
                excelApp = New Excel.Application  
                wkbk = excelApp.Workbooks.Add()  
                sheet = CType(wkbk.Sheets.Add(), Excel.Worksheet)  
                sheet.Name = "Sample Worksheet"  
  
                ' Write a column of values.  
                ' In the For loop, both the row index and array index start at 1.  
                ' Therefore the value of 4 at array index 0 is not included.  
                For i = 1 To values.Length - 1  
                    sheet.Cells(i, 1) = values(i)  
                Next  
  
                ' Suppress any alerts and save the file. Create the directory   
                ' if it does not exist. Overwrite the file if it exists.  
                excelApp.DisplayAlerts = False  
                Dim folderPath = My.Computer.FileSystem.GetParentPath(filePath)  
                If Not My.Computer.FileSystem.DirectoryExists(folderPath) Then  
                    My.Computer.FileSystem.CreateDirectory(folderPath)  
                End If  
                wkbk.SaveAs(filePath)  
        Catch  
  
            Finally  
                sheet = Nothing  
                wkbk = Nothing  
  
                ' Close Excel.  
                excelApp.Quit()  
                excelApp = Nothing  
            End Try  
  
        End Sub  
    End Module  
    ```  
  
8.  <span data-ttu-id="5bf91-131">保存项目。</span><span class="sxs-lookup"><span data-stu-id="5bf91-131">Save the project.</span></span>  
  
9. <span data-ttu-id="5bf91-132">按 CTRL + F5 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="5bf91-132">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="5bf91-133">验证是否已在示例代码中指定的位置创建 Excel 工作簿︰ C:\SampleFolder\SampleWorkbook.xls。</span><span class="sxs-lookup"><span data-stu-id="5bf91-133">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <span data-ttu-id="5bf91-134"><a name="BKMK_publishapp"></a>若要将应用发布到在其安装 Microsoft Office 的不同版本的计算机</span><span class="sxs-lookup"><span data-stu-id="5bf91-134"><a name="BKMK_publishapp"></a> To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="5bf91-135">打开由 Visual Studio 中本演练中创建的项目。</span><span class="sxs-lookup"><span data-stu-id="5bf91-135">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="5bf91-136">在**生成**菜单上，选择**发布 CreateExcelWorkbook**。</span><span class="sxs-lookup"><span data-stu-id="5bf91-136">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="5bf91-137">按照发布向导创建应用程序的可安装版本的步骤。</span><span class="sxs-lookup"><span data-stu-id="5bf91-137">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="5bf91-138">有关详细信息，请参阅[发布向导 （在 Visual Studio 中的 Office 开发）](https://msdn.microsoft.com/library/bb625071)。</span><span class="sxs-lookup"><span data-stu-id="5bf91-138">For more information, see [Publish Wizard (Office Development in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span></span>  
  
3.  <span data-ttu-id="5bf91-139">在其安装.NET Framework 4 或更高版本和不同版本的 Excel 的计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="5bf91-139">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="5bf91-140">完成安装后，运行安装的程序。</span><span class="sxs-lookup"><span data-stu-id="5bf91-140">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="5bf91-141">验证是否已在示例代码中指定的位置创建 Excel 工作簿︰ C:\SampleFolder\SampleWorkbook.xls。</span><span class="sxs-lookup"><span data-stu-id="5bf91-141">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf91-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bf91-142">See Also</span></span>  
 <span data-ttu-id="5bf91-143">[演练︰ 在 Visual Studio (Visual Basic 中) 中嵌入托管程序集中的类型](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md) </span><span class="sxs-lookup"><span data-stu-id="5bf91-143">[Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md) </span></span>  
<span data-ttu-id="5bf91-144"> [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)</span><span class="sxs-lookup"><span data-stu-id="5bf91-144"> [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)</span></span>

