---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: e67fe05507c8cb3edd7f46cad19211ba11e3b054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652391"
---
# <a name="-quiet"></a>-quiet
阻止编译器显示与语法相关的错误和警告的代码。  
  
## <a name="syntax"></a>语法  
  
```  
-quiet  
```  
  
## <a name="remarks"></a>备注  
 默认情况，`-quiet` 是无效的。 当编译器报告与语法相关的错误或警告时，它还将输出从源代码行。 对于应用程序分析编译器输出，它可能会更方便编译器输出的诊断的文本。  
  
 在下面的示例中，`Module1`输出包括源代码，而无需在编译时错误`-quiet`。  
  
```vb  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 输出：  
 
```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
``` 
 使用编译`-quiet`，则编译器输出仅如下：  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  `-quiet`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译`T2.vb`并且不显示与语法相关编译器诊断的代码：  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
