---
title: "如何：为 Visual Studio 命令行设置环境变量"
ms.date: 09-29-2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8012e310bb04ec3acef0790f9cd50ed42dd9286a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>如何：为 Visual Studio 命令行设置环境变量

VsDevCmd.bat 文件设置适当的环境变量，以便命令行生成。 有关 VsDevCmd.bat 的详细信息，请参阅[知识库文章 Q248802](http://go.microsoft.com/fwlink/?LinkId=225042)。  

> [!NOTE]
> VsDevCmd.bat 文件是随 Visual Studio 2017 提供一个新文件。 Visual Studio 2015 及更早版本将 VSVARS32.bat 用于相同目的。 此文件已存储在 files\microsoft Visual Studio\\*版本*\Common7\Tools 或 Program Files (x86) \Microsoft Visual Studio\\*版本*\Common7\Tools。
  
如果还具有 Visual Studio 的早期版本的计算机上安装 Visual Studio 的当前版本，你不应运行 VsDevCmd.bat 和 VSVARS32。BAT 不同版本在同一命令提示符窗口中。 相反，你应在自己的窗口中运行适用于每个版本的命令。
  
### <a name="to-run-vsdevcmdbat"></a>若要运行 VsDevCmd.BAT  
  
1.  从**启动**菜单上，打开**VS 2017 的开发人员命令提示符**。  在**Visual Studio 2017**文件夹。
  
2.  将更改为 files\microsoft Visual Studio\\*版本*\\*产品*\Common7\Tools 或 \Program 文件 (x86) \Microsoft Visual Studio\\*版本*\\*产品*安装 \Common7\Tools 子目录。  (*版本*是*2017年*有关最新版本。 *产品*是之一*企业*， *Professional*或*社区*。)
  
3.  通过键入运行 VsDevCmd.bat **VsDevCmd**。  
  
    > [!CAUTION]
    >  VsDevCmd.bat 异计算机到计算机。 不要使用另一台计算机从 VsDevCmd.bat 替换 VsDevCmd.bat 文件丢失或损坏。 而是应重新运行安装程序以替换丢失的文件。  
  
## <a name="see-also"></a>另请参阅  
 [在命令行上使用 csc.exe 生成](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
