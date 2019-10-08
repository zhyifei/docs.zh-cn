---
title: -imports （Visual Basic）
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 929e24a1ffd02d4e21ab1b925ddd59050b5d3cc4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005573"
---
# <a name="-imports-visual-basic"></a>-imports （Visual Basic）
从指定的程序集导入命名空间。  
  
## <a name="syntax"></a>语法  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`namespaceList`|必需。 要导入的命名空间的逗号分隔列表。|  
  
## <a name="remarks"></a>备注  
 @No__t-0 选项将导入在当前源文件集中或从任何引用的程序集内定义的任何命名空间。  
  
 使用 `-imports` 指定的命名空间中的成员可用于编译中的所有源代码文件。 使用[Imports 语句（.Net 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)可在单个源代码文件中使用命名空间。  
  
|在 Visual Studio 集成开发环境中设置/imports|  
|---|  
|1.在 **“解决方案资源管理器”** 中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“引用”选项卡。<br />3.在 "**添加用户导入**" 按钮旁的框中输入命名空间名称。<br />4.单击 "**添加用户导入**" 按钮。|  
  
## <a name="example"></a>示例  
 当指定 @no__t 时，以下代码将编译。 如果没有此方法，则成功编译需要在源代码文件的开头包含 `Imports System.Globalization` 语句，或者属性完全限定为 `System.Globalization.CultureInfo.CurrentCulture.Name`。

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [引用和 Imports 语句](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
