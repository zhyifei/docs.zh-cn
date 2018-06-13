---
title: 演练：在 Visual Studio 中嵌入 Microsoft Office 程序集中的类型信息 (C#)
ms.date: 07/20/2015
ms.assetid: 3320e866-01f1-4b7f-8932-049a7b2d2a9b
ms.openlocfilehash: 8e7eb5c797ca87f87950d530112ec64f1327ae0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324520"
---
# <a name="walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-visual-studio-c"></a><span data-ttu-id="59a6e-102">演练：在 Visual Studio 中嵌入 Microsoft Office 程序集中的类型信息 (C#)</span><span class="sxs-lookup"><span data-stu-id="59a6e-102">Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="59a6e-103">如果在引用 COM 对象的应用程序中嵌入类型信息，则无需使用主互操作程序集 (PIA)。</span><span class="sxs-lookup"><span data-stu-id="59a6e-103">If you embed type information in an application that references COM objects, you can eliminate the need for a primary interop assembly (PIA).</span></span> <span data-ttu-id="59a6e-104">此外，利用嵌入的类型信息可实现应用程序的版本独立性。</span><span class="sxs-lookup"><span data-stu-id="59a6e-104">Additionally, the embedded type information enables you to achieve version independence for your application.</span></span> <span data-ttu-id="59a6e-105">也就是说，可将程序编写为使用多个 COM 库版本中的类型，而无需使用每个版本的特定 PIA。</span><span class="sxs-lookup"><span data-stu-id="59a6e-105">That is, your program can be written to use types from multiple versions of a COM library without requiring a specific PIA for each version.</span></span> <span data-ttu-id="59a6e-106">对于使用 Microsoft Office 库中对象的应用程序，这是一种常用方案。</span><span class="sxs-lookup"><span data-stu-id="59a6e-106">This is a common scenario for applications that use objects from Microsoft Office libraries.</span></span> <span data-ttu-id="59a6e-107">通过嵌入类型信息，程序的同一个生成可以使用不同计算机上的不同 Microsoft Office 版本，而无需为 Microsoft Office 的每个版本重新部署该程序或 PIA。</span><span class="sxs-lookup"><span data-stu-id="59a6e-107">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers without the need to redeploy either the program or the PIA for each version of Microsoft Office.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a><span data-ttu-id="59a6e-108">系统必备</span><span class="sxs-lookup"><span data-stu-id="59a6e-108">Prerequisites</span></span>  
 <span data-ttu-id="59a6e-109">本演练需要如下内容：</span><span class="sxs-lookup"><span data-stu-id="59a6e-109">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="59a6e-110">安装有 Visual Studio 和 Microsoft Excel 的计算机。</span><span class="sxs-lookup"><span data-stu-id="59a6e-110">A computer on which Visual Studio and Microsoft Excel are installed.</span></span>  
  
-   <span data-ttu-id="59a6e-111">安装有 .NET Framework 4 或更高版本和其他 Excel 版本的另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="59a6e-111">A second computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
##  <a name="BKMK_createapp"></a> <span data-ttu-id="59a6e-112">创建适用于多个 Microsoft Office 版本的应用程序</span><span class="sxs-lookup"><span data-stu-id="59a6e-112">To create an application that works with multiple versions of Microsoft Office</span></span>  
  
1.  <span data-ttu-id="59a6e-113">在安装有 Excel 的计算机上启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="59a6e-113">Start Visual Studio on a computer on which Excel is installed.</span></span>  
  
2.  <span data-ttu-id="59a6e-114">在“文件”  菜单上，选择“新建” 、“项目” 。</span><span class="sxs-lookup"><span data-stu-id="59a6e-114">On the **File** menu, choose **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="59a6e-115">在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。</span><span class="sxs-lookup"><span data-stu-id="59a6e-115">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="59a6e-116">在“模板”窗格中，选择“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="59a6e-116">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="59a6e-117">在“新建项目”框中，输入 `CreateExcelWorkbook`，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="59a6e-117">In the **Name** box, enter `CreateExcelWorkbook`, and then choose the **OK** button.</span></span> <span data-ttu-id="59a6e-118">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="59a6e-118">The new project is created.</span></span>  
  
4.  <span data-ttu-id="59a6e-119">在“解决方案资源管理器”中，打开“引用”文件夹的快捷菜单，然后选择“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="59a6e-119">In **Solution Explorer**, open the shortcut menu for the **References** folder and then choose **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="59a6e-120">在“.NET”选项卡上，选择最新版本的 `Microsoft.Office.Interop.Excel`。</span><span class="sxs-lookup"><span data-stu-id="59a6e-120">On the **.NET** tab, choose the most recent version of `Microsoft.Office.Interop.Excel`.</span></span> <span data-ttu-id="59a6e-121">例如 **Microsoft.Office.Interop.Excel 14.0.0.0**。</span><span class="sxs-lookup"><span data-stu-id="59a6e-121">For example, **Microsoft.Office.Interop.Excel 14.0.0.0**.</span></span> <span data-ttu-id="59a6e-122">选择“确定”  按钮。</span><span class="sxs-lookup"><span data-stu-id="59a6e-122">Choose the **OK** button.</span></span>  
  
6.  <span data-ttu-id="59a6e-123">在 **CreateExcelWorkbook** 项目的引用列表中，选择上一步添加的 `Microsoft.Office.Interop.Excel` 引用。</span><span class="sxs-lookup"><span data-stu-id="59a6e-123">In the list of references for the **CreateExcelWorkbook** project, select the reference for `Microsoft.Office.Interop.Excel` that you added in the previous step.</span></span> <span data-ttu-id="59a6e-124">在“属性”窗口中，确保 `Embed Interop Types` 属性已设置为 `True`。</span><span class="sxs-lookup"><span data-stu-id="59a6e-124">In the **Properties** window, make sure that the `Embed Interop Types` property is set to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59a6e-125">由于嵌入的互操作类型信息，本演练中创建的应用程序可与不同的 Microsoft Office 版本一起运行。</span><span class="sxs-lookup"><span data-stu-id="59a6e-125">The application created in this walkthrough runs with different versions of Microsoft Office because of the embedded interop type information.</span></span> <span data-ttu-id="59a6e-126">如果 `Embed Interop Types` 属性设置为 `False`，则必须为与应用程序一起运行的每个 Microsoft Office 版本添加一个 PIA。</span><span class="sxs-lookup"><span data-stu-id="59a6e-126">If the `Embed Interop Types` property is set to `False`, you must include a PIA for each version of Microsoft Office that the application will run with.</span></span>  
  
7.  <span data-ttu-id="59a6e-127">打开 **Program.cs** 文件。</span><span class="sxs-lookup"><span data-stu-id="59a6e-127">Open the **Program.cs** file.</span></span> <span data-ttu-id="59a6e-128">用下面的代码替换文件中的代码：</span><span class="sxs-lookup"><span data-stu-id="59a6e-128">Replace the code in the file with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.IO;  
    using Excel = Microsoft.Office.Interop.Excel;  
  
    namespace CreateExcelWorkbook  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                int[] values = {4, 6, 18, 2, 1, 76, 0, 3, 11};  
  
                CreateWorkbook(values, @"C:\SampleFolder\SampleWorkbook.xls");  
            }  
  
            static void CreateWorkbook(int[] values, string filePath)  
            {  
                Excel.Application excelApp = null;  
                Excel.Workbook wkbk;  
                Excel.Worksheet sheet;  
  
                try  
                {  
                        // Start Excel and create a workbook and worksheet.  
                        excelApp = new Excel.Application();  
                        wkbk = excelApp.Workbooks.Add();  
                        sheet = wkbk.Sheets.Add() as Excel.Worksheet;  
                        sheet.Name = "Sample Worksheet";  
  
                        // Write a column of values.  
                        // In the For loop, both the row index and array index start at 1.  
                        // Therefore the value of 4 at array index 0 is not included.  
                        for (int i = 1; i < values.Length; i++)  
                        {  
                            sheet.Cells[i, 1] = values[i];  
                        }  
  
                        // Suppress any alerts and save the file. Create the directory   
                        // if it does not exist. Overwrite the file if it exists.  
                        excelApp.DisplayAlerts = false;  
                        string folderPath = Path.GetDirectoryName(filePath);  
                        if (!Directory.Exists(folderPath))  
                        {  
                            Directory.CreateDirectory(folderPath);  
                        }  
                        wkbk.SaveAs(filePath);  
                }  
                catch  
                {  
                }  
                finally  
                {  
                    sheet = null;  
                    wkbk = null;  
  
                    // Close Excel.  
                    excelApp.Quit();  
                    excelApp = null;  
                }  
            }  
        }  
    }  
    ```  
  
8.  <span data-ttu-id="59a6e-129">保存项目。</span><span class="sxs-lookup"><span data-stu-id="59a6e-129">Save the project.</span></span>  
  
9. <span data-ttu-id="59a6e-130">按 Ctrl+F5 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="59a6e-130">Press CTRL+F5 to build and run the project.</span></span> <span data-ttu-id="59a6e-131">验证是否已在示例代码中指定的位置创建 Excel 工作簿：C:\SampleFolder\SampleWorkbook.xls。</span><span class="sxs-lookup"><span data-stu-id="59a6e-131">Verify that an Excel workbook has been created at the location specified in the example code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
##  <a name="BKMK_publishapp"></a> <span data-ttu-id="59a6e-132">将应用程序发布到安装有不同 Microsoft Office 版本的计算机</span><span class="sxs-lookup"><span data-stu-id="59a6e-132">To publish the application to a computer on which a different version of Microsoft Office is installed</span></span>  
  
1.  <span data-ttu-id="59a6e-133">在 Visual Studio 中打开本演练创建的项目。</span><span class="sxs-lookup"><span data-stu-id="59a6e-133">Open the project created by this walkthrough in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="59a6e-134">在“生成”菜单上，选择“发布 CreateExcelWorkbook”。</span><span class="sxs-lookup"><span data-stu-id="59a6e-134">On the **Build** menu, choose **Publish CreateExcelWorkbook**.</span></span> <span data-ttu-id="59a6e-135">按照发布向导的步骤创建应用程序的可安装版本。</span><span class="sxs-lookup"><span data-stu-id="59a6e-135">Follow the steps of the Publish Wizard to create an installable version of the application.</span></span> <span data-ttu-id="59a6e-136">有关详细信息，请参阅[发布向导（Visual Studio 中的 Office 开发）](https://msdn.microsoft.com/library/bb625071)。</span><span class="sxs-lookup"><span data-stu-id="59a6e-136">For more information, see [Publish Wizard (Office Development in Visual Studio)](https://msdn.microsoft.com/library/bb625071).</span></span>  
  
3.  <span data-ttu-id="59a6e-137">在安装有 .NET Framework 4 或更高版本和另一个 Excel 版本的计算机上，安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="59a6e-137">Install the application on a computer on which the .NET Framework 4 or higher and a different version of Excel are installed.</span></span>  
  
4.  <span data-ttu-id="59a6e-138">完成安装后，运行安装的程序。</span><span class="sxs-lookup"><span data-stu-id="59a6e-138">When the installation is finished, run the installed program.</span></span>  
  
5.  <span data-ttu-id="59a6e-139">验证是否已在示例代码中指定的位置创建了 Excel 工作簿：C:\SampleFolder\SampleWorkbook.xls。</span><span class="sxs-lookup"><span data-stu-id="59a6e-139">Verify that an Excel workbook has been created at the location specified in the sample code: C:\SampleFolder\SampleWorkbook.xls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a6e-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="59a6e-140">See Also</span></span>  
 [<span data-ttu-id="59a6e-141">演练：在 Visual Studio 中嵌入托管程序集中的类型 (C#)</span><span class="sxs-lookup"><span data-stu-id="59a6e-141">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
 [<span data-ttu-id="59a6e-142">/link（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="59a6e-142">/link (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)
