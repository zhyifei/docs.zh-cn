---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004643"
---
# <a name="-win32icon"></a>-win32icon
在输出文件中插入 .ico 文件。 此 .ico 文件表示**文件资源管理器**中的输出文件。  
  
## <a name="syntax"></a>语法  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>参数  
  
|术语|Definition|  
|---|---|  
|`filename`|要添加到输出文件的 .ico 文件。 如果文件名包含空格，请将文件名用引号（""）引起来。|  
  
## <a name="remarks"></a>备注  
 您可以使用 Microsoft Windows 资源编译器（RC）创建 .ico 文件。 在编译视觉对象C++程序时，将调用资源编译器;.ico 文件是从 .rc 文件创建的。 `-win32icon` 和 `-win32resource` 选项是互斥的。  
  
 请参阅[-linkresource （Visual Basic）](../../../visual-basic/reference/command-line-compiler/linkresource.md)以引用 .NET Framework 资源文件或[-resource （Visual Basic）](../../../visual-basic/reference/command-line-compiler/resource.md)来附加 .NET Framework 资源文件。 请参阅[-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)以导入 .res 文件。  
  
|在 Visual Studio IDE 中设置-win32icon|  
|---|  
|1. 在**解决方案资源管理器**中选择了一个项目。 在“项目”菜单上，单击“属性”。 <br />2. 单击 "**应用程序**" 选项卡。<br />3. 修改**图标**框中的值。|  
  
## <a name="example"></a>示例  
 下面的代码编译 `In.vb` 并附加 .ico 文件，`Rf.ico`。  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
