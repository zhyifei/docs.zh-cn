---
title: /reference (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f8c6851802afa818cc80b3f6d7eafc2ef47ac689
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="reference-visual-basic"></a>/reference (Visual Basic)
使编译器将在指定的程序集的类型信息提供给当前正在编译项目。  
  
## <a name="syntax"></a>语法  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`fileList`|必需。 程序集文件名的逗号分隔列表。 如果文件名包含空格，则将名称括在引号内。|  
  
## <a name="remarks"></a>备注  
 你导入的文件必须包含程序集元数据。 仅公共类型都是程序集外部可见的。 [/Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)选项从模块导入元数据。  
  
 如果引用的程序集 （程序集 A） 其本身引用了另一个程序集 (程序集 B)，你在下列情况下需要引用程序集 B:  
  
-   程序集 A 中的类型继承自程序集 B 中的类型或实现程序集 B 中的接口。  
  
-   调用具有程序集 B 中的返回类型或参数类型的字段、属性、事件或方法。  
  
 使用[/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)指定一个或多个程序集引用所在的目录。  
  
 编译器识别出的程序集 （而不是模块） 的类型，必须将它强制解析类型。 如何执行此操作的一个示例是定义类型的实例。 其他方法是可用于解析在编译器的程序集中的类型名称。 例如，如果你从程序集中的类型继承，类型名称然后变得与编译器已知的。  
  
 Vbc.rsp 响应文件，该引用常用文件[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]程序集，默认情况下使用。 使用`/noconfig`如果您不希望编译器使用 Vbc.rsp。  
  
 `/reference` 的缩写形式是 `/r`。  
  
## <a name="example"></a>示例  
 下面的代码编译源文件 `Input.vb` 并引用来自 `Metad1.dll` 和 `Metad2.dll` 的程序集以生成 `Out.exe`。  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
