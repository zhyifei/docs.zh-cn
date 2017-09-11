---
title: "如何︰ 调用命令行编译器 (Visual Basic 中) |Microsoft 文档"
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
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line, arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
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
ms.openlocfilehash: e19bb506b016b774d2c497f8b17d91b35afb3eef
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="2d1e5-102">如何：调用命令行编译器 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d1e5-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="2d1e5-103">可以通过命令行中，也称为 MS-DOS 提示符中键入可执行文件的名称来调用命令行编译器。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="2d1e5-104">如果从默认 Windows 命令提示符下进行编译，您必须键入的可执行文件的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="2d1e5-105">若要覆盖此默认行为，您可以使用[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]命令提示符，或修改 PATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-105">To override this default behavior, you can either use the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="2d1e5-106">同时，可以从任何目录编译通过只需键入编译器的名称。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="2d1e5-107">若要使用 Visual Studio 命令提示编译器调用</span><span class="sxs-lookup"><span data-stu-id="2d1e5-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="2d1e5-108">打开 Microsoft Visual Studio 程序组中的 Visual Studio Tools 程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="2d1e5-109">您可以使用[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]命令提示符下，若要从您的计算机上的任何目录访问编译器，如果安装 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-109">You can use the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="2d1e5-110">调用[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-110">Invoke the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Command Prompt.</span></span>  
  
4.  <span data-ttu-id="2d1e5-111">在命令行中，键入`vbc.exe` *sourceFileName*然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="2d1e5-112">例如，如果您在一个名为目录中存储您的源代码`SourceFiles`，您应打开命令提示符并键入`cd SourceFiles`以更改到此目录。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="2d1e5-113">如果该目录包含一个名为的源代码文件`Source.vb`，您可以通过键入来对其进行编译`vbc.exe Source.vb`。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="2d1e5-114">将 PATH 环境变量设置为编译器的 Windows 命令提示符</span><span class="sxs-lookup"><span data-stu-id="2d1e5-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="2d1e5-115">使用 Windows 搜索功能在您的本地磁盘上查找 Vbc.exe。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="2d1e5-116">编译器所在的目录的确切名称取决于 Windows 目录的位置和版本的[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installed.</span></span> <span data-ttu-id="2d1e5-117">如果您有多个版本的[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]安装，您必须确定要使用 （通常使用最新版本） 的版本。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-117">If you have more than one version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="2d1e5-118">从您**启动**菜单上，用鼠标右键单击**我的电脑**，然后单击**属性**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="2d1e5-119">单击**高级**选项卡上，然后单击**环境变量**。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="2d1e5-120">在**系统**变量窗格，选择**路径**从该列表，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="2d1e5-121">在**编辑系统**变量对话框中，插入点移到中的字符串的末尾**变量值**字段中，键入以分号 （;） 后跟在步骤 1 中找到完整的目录名称。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="2d1e5-122">单击**确定**以确认所做的编辑，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="2d1e5-123">更改 PATH 环境变量后，您可以运行[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器在 Windows 命令提示符从任何计算机上的目录。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-123">After you change the PATH environment variable, you can run the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="2d1e5-124">若要使用 Windows 命令提示符编译器调用</span><span class="sxs-lookup"><span data-stu-id="2d1e5-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="2d1e5-125">从**启动**菜单上单击**附件**文件夹，然后再打开**Windows 命令提示符下**。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="2d1e5-126">在命令行中，键入`vbc.exe` *sourceFileName*然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="2d1e5-127">例如，如果您在一个名为目录中存储您的源代码`SourceFiles`，您应打开命令提示符并键入`cd SourceFiles`以更改到此目录。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="2d1e5-128">如果该目录包含一个名为的源代码文件`Source.vb`，您可以通过键入来对其进行编译`vbc.exe Source.vb`。</span><span class="sxs-lookup"><span data-stu-id="2d1e5-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1e5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d1e5-129">See Also</span></span>  
 <span data-ttu-id="2d1e5-130">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2d1e5-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2d1e5-131"> [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="2d1e5-131"> [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span></span>
