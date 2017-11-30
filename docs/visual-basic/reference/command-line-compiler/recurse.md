---
title: /recurse
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb69c7c44dcc2e8da5eb8a76f7d22f936a6d948f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="recurse"></a>/recurse
编译源代码文件的指定的目录或项目目录的所有子目录中。  
  
## <a name="syntax"></a>语法  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>参数  
 `dir`  
 可选。 希望从中开始搜索的目录。 如果未指定，在项目目录中开始执行搜索。  
  
 `file`  
 必需。 要搜索的文件。 允许通配符。  
  
## <a name="remarks"></a>备注  
 可以在文件名中使用通配符来编译项目目录中的所有匹配的文件而无需使用`/recurse`。 如果不指定任何输出文件的名称，则编译器将基于上处理的第一个输入文件的输出文件名称。 这通常是在编译时按字母顺序查看的文件列表中的第一个文件。 为此，最好是指定输出文件使用`/out`选项。  
  
> [!NOTE]
>  `/recurse`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译所有[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]当前目录中的文件。  
  
```  
vbc *.vb  
```  
  
 下面的代码编译所有[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]文件中`Test\ABC`目录和它下面的任何目录，然后生成`Test.ABC.dll`。  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ 输出 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
