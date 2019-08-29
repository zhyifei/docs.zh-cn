---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964391"
---
# <a name="-noconfig"></a>-noconfig
指定编译器不应自动引用常用 .NET Framework 程序集或导入`System`和`Microsoft.VisualBasic`命名空间。  
  
## <a name="syntax"></a>语法  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>备注  
 `-noconfig`选项告诉编译器不要用 vbc 文件 (位于 dcdiag.exe 文件所在的目录中) 进行编译。 Vbc 文件引用常用的 .NET Framework 程序集, 并导入`System`和`Microsoft.VisualBasic`命名空间。 除非指定了`-nostdlib`选项, 否则编译器将隐式引用 system.object 程序集。 `-nostdlib`选项告诉编译器不要用 Vbc 编译, 或自动引用 system.object 程序集。  
  
> [!NOTE]
> Mscorlib 和 Microsoft. .dll 程序集始终被引用。  
  
 您可以修改 vbc 文件以指定应包括在每个 Vbc 编译中的其他编译器选项 (指定`-noconfig`选项时除外)。 有关详细信息，请参阅 [@（指定响应文件）](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)。  
  
 编译器会处理最后传递给`vbc`命令的选项。 因此, 命令行上的任何选项都将覆盖 Vbc 文件中相同选项的设置。  
  
> [!NOTE]
> 此`-noconfig`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="see-also"></a>请参阅

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [@（指定响应文件）](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
