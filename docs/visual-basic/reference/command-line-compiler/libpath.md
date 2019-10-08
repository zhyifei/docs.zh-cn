---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 8f4e415576562885c9edbd3d2dddbe2a271e9923
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005466"
---
# <a name="-libpath"></a>-libpath
指定引用程序集的位置。  
  
## <a name="syntax"></a>语法  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`dirList`|必需。 以分号分隔的目录列表，如果在当前工作目录（从中调用编译器的目录）或公共语言运行时的系统目录中找不到引用的程序集，则编译器将在该列表中查找。 如果目录名称包含空格，则将该名称括在引号（""）中。|  
  
## <a name="remarks"></a>备注  
 @No__t-0 选项指定由[-reference](../../../visual-basic/reference/command-line-compiler/reference.md)选项引用的程序集的位置。  
  
 编译器按以下顺序搜索未完全限定的程序集引用：  
  
1. 当前工作目录。 该目录为从其调用编译器的目录。  
  
2. 公共语言运行时系统目录。  
  
3. @No__t 指定的目录。  
  
4. 由 LIB 环境变量指定的目录。  
  
 @No__t-0 选项是累加的;多次指定它会追加到以前的任何值。  
  
 使用 `-reference` 可指定程序集引用。  
  
|在 Visual Studio 集成开发环境中设置/libpath|  
|---|  
|1.在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“引用”选项卡。<br />3.单击 "**引用路径 ...** " 按钮。<br />4.在 "**引用路径**" 对话框中，在 "**文件夹：** " 框中输入目录名称。<br />5.单击 "**添加文件夹**"。|  
  
## <a name="example"></a>示例  
 下面的代码编译 `T2.vb` 以创建 .exe 文件。 编译器将在工作目录中的 C：驱动器的根目录中查找，并在 C：驱动器的新程序集目录中查找程序集引用。  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>请参阅

- [.NET 中的程序集](../../../standard/assembly/index.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
