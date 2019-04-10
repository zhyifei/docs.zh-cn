---
title: 如何：调用命令行编译器 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 67cad0df3f10ff1fa1f6a58546fe150232fe1283
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302798"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="66881-102">如何：调用命令行编译器 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66881-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="66881-103">可以通过在命令行中，也称为 MS-DOS 提示符中键入可执行文件的名称来调用命令行编译器。</span><span class="sxs-lookup"><span data-stu-id="66881-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="66881-104">如果从默认 Windows 命令提示符下进行编译，你必须键入的可执行文件的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="66881-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="66881-105">若要替代此默认行为，可以使用用于 Visual Studio，开发人员命令提示或修改 PATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="66881-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="66881-106">同时，可从任何目录编译只需键入编译器名称。</span><span class="sxs-lookup"><span data-stu-id="66881-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="66881-107">若要调用编译器使用针对 Visual Studio 开发人员命令提示</span><span class="sxs-lookup"><span data-stu-id="66881-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>  
  
1. <span data-ttu-id="66881-108">打开 Microsoft Visual Studio 程序组中的 Visual Studio Tools 程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="66881-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2. <span data-ttu-id="66881-109">可以使用 Visual Studio 开发人员命令提示若要从任何目录访问编译器，在你的计算机，如果安装了 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="66881-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3. <span data-ttu-id="66881-110">用于 Visual Studio 调用开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="66881-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>  
  
4. <span data-ttu-id="66881-111">在命令行中，键入`vbc.exe` *sourceFileName* ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="66881-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="66881-112">例如，如果在名为的目录中存储你的源代码`SourceFiles`，将打开命令提示符并键入`cd SourceFiles`更改为该目录。</span><span class="sxs-lookup"><span data-stu-id="66881-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="66881-113">如果该目录包含名为源文件`Source.vb`，则可以通过键入来对其进行编译`vbc.exe Source.vb`。</span><span class="sxs-lookup"><span data-stu-id="66881-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="66881-114">若要设置为编译器的 Windows 命令提示符下的 PATH 环境变量</span><span class="sxs-lookup"><span data-stu-id="66881-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1. <span data-ttu-id="66881-115">使用 Windows Search 功能在本地磁盘上查找 Vbc.exe。</span><span class="sxs-lookup"><span data-stu-id="66881-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="66881-116">编译器的目录的确切名称取决于 Windows 目录的位置和安装了".NET Framework"的版本。</span><span class="sxs-lookup"><span data-stu-id="66881-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="66881-117">如果有多个版本的安装".NET Framework"，您必须确定要使用 （通常使用最新版本） 的版本。</span><span class="sxs-lookup"><span data-stu-id="66881-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2. <span data-ttu-id="66881-118">从你**启动**菜单中，右键单击**我的电脑**，然后单击**属性**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="66881-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3. <span data-ttu-id="66881-119">单击**高级**选项卡，然后依次**环境变量**。</span><span class="sxs-lookup"><span data-stu-id="66881-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4. <span data-ttu-id="66881-120">在中**系统**变量窗格中，选择**路径**从列表中单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="66881-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5. <span data-ttu-id="66881-121">在**编辑系统**变量的对话框中，将插入点移动到中字符串的末尾**变量值**字段并键入分号 （;） 后接在步骤 1 中找到完整的目录名称。</span><span class="sxs-lookup"><span data-stu-id="66881-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6. <span data-ttu-id="66881-122">单击**确定**以确认所做的编辑，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="66881-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="66881-123">更改 PATH 环境变量后，你可以运行 Visual Basic 编译器在 Windows 命令提示符从任何目录的计算机上。</span><span class="sxs-lookup"><span data-stu-id="66881-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="66881-124">若要调用编译器使用 Windows 命令提示符</span><span class="sxs-lookup"><span data-stu-id="66881-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1. <span data-ttu-id="66881-125">从**启动**菜单上单击**附件**文件夹，，然后打开**Windows 命令提示符下**。</span><span class="sxs-lookup"><span data-stu-id="66881-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2. <span data-ttu-id="66881-126">在命令行中，键入`vbc.exe` *sourceFileName* ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="66881-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="66881-127">例如，如果在名为的目录中存储你的源代码`SourceFiles`，将打开命令提示符并键入`cd SourceFiles`更改为该目录。</span><span class="sxs-lookup"><span data-stu-id="66881-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="66881-128">如果该目录包含名为源文件`Source.vb`，则可以通过键入来对其进行编译`vbc.exe Source.vb`。</span><span class="sxs-lookup"><span data-stu-id="66881-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66881-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="66881-129">See also</span></span>

- [<span data-ttu-id="66881-130">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="66881-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="66881-131">条件编译</span><span class="sxs-lookup"><span data-stu-id="66881-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
