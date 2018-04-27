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
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>如何：调用命令行编译器 (Visual Basic)
可以通过在命令行中，也称为 MS-DOS 提示符中键入其可执行文件的名称来调用命令行编译器。 如果从默认的 Windows 命令提示符下进行编译，你必须键入可执行文件的完全限定的路径。 若要覆盖此默认行为，则您可以使用[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]命令提示符下，或修改 PATH 环境变量。 同时，可以从任何目录编译通过只需键入编译器的名称。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>若要调用编译器使用 Visual Studio 命令提示符  
  
1.  打开 Microsoft Visual Studio 程序组中的 Visual Studio Tools 程序文件夹。  
  
2.  你可以使用[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]访问你的计算机上的任何目录中的编译器，如果安装了 Visual Studio 命令提示符。  
  
3.  调用[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]命令提示符。  
  
4.  在命令行中，键入`vbc.exe` *sourceFileName*然后按 ENTER。  
  
     例如，如果您在一个名为目录中存储你的源代码`SourceFiles`，会打开命令提示符并键入`cd SourceFiles`更改为该目录。 如果该目录包含一个名为的源文件`Source.vb`，则无法通过键入对其进行编译`vbc.exe Source.vb`。  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>若要向编译器为 Windows 命令提示中设置的 PATH 环境变量  
  
1.  使用 Windows 搜索功能在您的本地磁盘上找到 Vbc.exe。  
  
     编译器所在的目录的确切名称取决于 Windows 目录的位置和安装了".NET Framework"的版本。 如果你有多个版本安装了".NET Framework"，你必须确定要使用 （通常使用最新版本） 的版本。  
  
2.  从你**启动**菜单上，右键单击**我的电脑**，然后单击**属性**从快捷菜单。  
  
3.  单击**高级**选项卡上，并依次**环境变量**。  
  
4.  在**系统**变量窗格中，选择**路径**从该列表并单击**编辑**。  
  
5.  在**编辑系统**变量对话框中，插入点移到中的字符串的末尾**变量值**字段并键入以分号 （;） 跟在步骤 1 中找到的完整目录名称。  
  
6.  单击**确定**以确认所做的编辑，然后关闭对话框。  
  
     更改 PATH 环境变量后，你可以 Visual Basic 编译器在 Windows 命令提示符处从任何目录运行的计算机上。  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>若要调用编译器使用 Windows 命令提示符  
  
1.  从**启动**菜单上，单击**附件**文件夹，，然后打开**Windows 命令提示符**。  
  
2.  在命令行中，键入`vbc.exe` *sourceFileName*然后按 ENTER。  
  
     例如，如果您在一个名为目录中存储你的源代码`SourceFiles`，会打开命令提示符并键入`cd SourceFiles`更改为该目录。 如果该目录包含一个名为的源文件`Source.vb`，则无法通过键入对其进行编译`vbc.exe Source.vb`。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
