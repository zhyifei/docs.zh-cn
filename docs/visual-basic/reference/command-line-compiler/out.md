---
title: -out （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005328"
---
# <a name="-out-visual-basic"></a>-out （Visual Basic）
指定输出文件的名称。  
  
## <a name="syntax"></a>语法  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`filename`|必需。 编译器创建的输出文件的名称。 如果文件名包含空格，则将该名称括在引号（""）中。|  
  
## <a name="remarks"></a>备注  
 指定要创建的文件的完整名称和扩展名。 如果不这样做，.exe 文件将从包含 `Sub Main` 过程的源代码文件中获取其名称，并且 .dll 文件从第一个源代码文件中获取其名称。  
  
 如果指定不带 .exe 或 .dll 扩展名的文件名，编译器会自动为你添加扩展，具体取决于为 `-target` 编译器选项指定的值。  
  
|在 Visual Studio 集成开发环境中设置|  
|---|  
|1.在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“应用程序” 选项卡。<br />3.修改 "**程序集名称**" 框中的值。|  
  
## <a name="example"></a>示例  
 下面的代码编译 `T2.vb`，并创建 `T2.exe` 的输出文件。  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target （Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
