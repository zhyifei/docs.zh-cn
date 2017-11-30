---
title: /noconfig
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94d13ccf0168027f4560b980c41e2a001ff503fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="noconfig"></a>/noconfig
指定，编译器不应该自动引用常用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]程序集或导入`System`和`Microsoft.VisualBasic`命名空间。  
  
## <a name="syntax"></a>语法  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a>备注  
 `/noconfig`选项告知编译器不进行编译使用 Vbc.rsp 文件，它位于 Vbc.exe 文件所在的同一目录中。 Vbc.rsp 文件引用常用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]程序集和导入`System`和`Microsoft.VisualBasic`命名空间。 编译器隐式引用 System.dll 程序集，除非`/nostdlib`指定选项。 `/nostdlib`选项告知编译器不能使用 vbc.rsp 进行编译或自动引用 System.dll 程序集。  
  
> [!NOTE]
>  始终引用 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的程序集。  
  
 你可以修改 Vbc.rsp 文件，以指定应包括在每个 Vbc.exe 编译的其他编译器选项 (除非指定`/noconfig`选项)。 有关详细信息，请参阅 [@（指定响应文件）](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)。  
  
 编译器选项传递给处理`vbc`最后一个命令。 因此，在命令行上的任何选项将重写 Vbc.rsp 文件中的相同选项的设置。  
  
> [!NOTE]
>  `/noconfig`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="see-also"></a>另请参阅  
 [/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [@（指定响应文件）](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
