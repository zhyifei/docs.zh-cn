---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 045e621f0104c4c958d77d2443c1524b33410b7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650460"
---
# <a name="-win32icon"></a>-win32icon
将.ico 文件插入到输出文件中。 此.ico 文件表示中的输出文件**文件资源管理器**。  
  
## <a name="syntax"></a>语法  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`filename`|要添加到输出文件的.ico 文件。 将文件名括在双引号 ("") 如果它包含空格。|  
  
## <a name="remarks"></a>备注  
 你可以使用 Microsoft Windows 资源编译器 (RC) 创建.ico 文件。 编译 Visual c + + 程序; 时会调用资源编译器.ico 文件是从.rc 文件创建的。 `-win32icon`和`-win32resource`选项互斥。  
  
 请参阅[-linkresource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/linkresource.md)引用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件，或[-资源 (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/resource.md)附加[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件。 请参阅[-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)导入.res 文件。  
  
|若要设置的 Visual Studio IDE 中的 win32icon|  
|---|  
|1.在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“应用程序”  选项卡。<br />3.修改中的值**图标**框。|  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`和将.ico 文件，附加`Rf.ico`。  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
