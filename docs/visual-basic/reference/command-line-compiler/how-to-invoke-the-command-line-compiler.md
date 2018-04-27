---
title: 如何：调用命令行编译器 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f1ccf08ba58fa6af60bd8ffd7cba79b205dc0f3d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="1638b-102">如何：调用命令行编译器 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1638b-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="1638b-103">可以通过在命令行中，也称为 MS-DOS 提示符中键入其可执行文件的名称来调用命令行编译器。</span><span class="sxs-lookup"><span data-stu-id="1638b-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="1638b-104">如果从默认的 Windows 命令提示符下进行编译，你必须键入可执行文件的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="1638b-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="1638b-105">若要覆盖此默认行为，则您可以使用[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]命令提示符下，或修改 PATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="1638b-105">To override this default behavior, you can either use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="1638b-106">同时，可以从任何目录编译通过只需键入编译器的名称。</span><span class="sxs-lookup"><span data-stu-id="1638b-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="1638b-107">若要调用编译器使用 Visual Studio 命令提示符</span><span class="sxs-lookup"><span data-stu-id="1638b-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="1638b-108">打开 Microsoft Visual Studio 程序组中的 Visual Studio Tools 程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="1638b-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="1638b-109">你可以使用[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]访问你的计算机上的任何目录中的编译器，如果安装了 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="1638b-109">You can use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="1638b-110">调用[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]命令提示符。</span><span class="sxs-lookup"><span data-stu-id="1638b-110">Invoke the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt.</span></span>  
  
4.  <span data-ttu-id="1638b-111">在命令行中，键入`vbc.exe` *sourceFileName*然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="1638b-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="1638b-112">例如，如果您在一个名为目录中存储你的源代码`SourceFiles`，会打开命令提示符并键入`cd SourceFiles`更改为该目录。</span><span class="sxs-lookup"><span data-stu-id="1638b-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="1638b-113">如果该目录包含一个名为的源文件`Source.vb`，则无法通过键入对其进行编译`vbc.exe Source.vb`。</span><span class="sxs-lookup"><span data-stu-id="1638b-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="1638b-114">若要向编译器为 Windows 命令提示中设置的 PATH 环境变量</span><span class="sxs-lookup"><span data-stu-id="1638b-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="1638b-115">使用 Windows 搜索功能在您的本地磁盘上找到 Vbc.exe。</span><span class="sxs-lookup"><span data-stu-id="1638b-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="1638b-116">编译器所在的目录的确切名称取决于 Windows 目录的位置和安装了".NET Framework"的版本。</span><span class="sxs-lookup"><span data-stu-id="1638b-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="1638b-117">如果你有多个版本安装了".NET Framework"，你必须确定要使用 （通常使用最新版本） 的版本。</span><span class="sxs-lookup"><span data-stu-id="1638b-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="1638b-118">从你**启动**菜单上，右键单击**我的电脑**，然后单击**属性**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="1638b-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="1638b-119">单击**高级**选项卡上，并依次**环境变量**。</span><span class="sxs-lookup"><span data-stu-id="1638b-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="1638b-120">在**系统**变量窗格中，选择**路径**从该列表并单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="1638b-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="1638b-121">在**编辑系统**变量对话框中，插入点移到中的字符串的末尾**变量值**字段并键入以分号 （;） 跟在步骤 1 中找到的完整目录名称。</span><span class="sxs-lookup"><span data-stu-id="1638b-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="1638b-122">单击**确定**以确认所做的编辑，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="1638b-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="1638b-123">更改 PATH 环境变量后，你可以 Visual Basic 编译器在 Windows 命令提示符处从任何目录运行的计算机上。</span><span class="sxs-lookup"><span data-stu-id="1638b-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="1638b-124">若要调用编译器使用 Windows 命令提示符</span><span class="sxs-lookup"><span data-stu-id="1638b-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="1638b-125">从**启动**菜单上，单击**附件**文件夹，，然后打开**Windows 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="1638b-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="1638b-126">在命令行中，键入`vbc.exe` *sourceFileName*然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="1638b-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="1638b-127">例如，如果您在一个名为目录中存储你的源代码`SourceFiles`，会打开命令提示符并键入`cd SourceFiles`更改为该目录。</span><span class="sxs-lookup"><span data-stu-id="1638b-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="1638b-128">如果该目录包含一个名为的源文件`Source.vb`，则无法通过键入对其进行编译`vbc.exe Source.vb`。</span><span class="sxs-lookup"><span data-stu-id="1638b-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1638b-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="1638b-129">See Also</span></span>  
 [<span data-ttu-id="1638b-130">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="1638b-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1638b-131">条件编译</span><span class="sxs-lookup"><span data-stu-id="1638b-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
