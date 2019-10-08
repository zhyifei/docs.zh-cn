---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005444"
---
# <a name="-noconfig"></a>-noconfig
指定编译器不应自动引用常用的 .NET Framework 程序集，也不会导入 @no__t 的命名空间和 @no__t。  
  
## <a name="syntax"></a>语法  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>备注  
 @No__t-0 选项告知编译器不要用 Vbc 文件（该文件位于 dcdiag.exe 文件所在的目录中）进行编译。 Vbc 文件引用常用 .NET Framework 程序集，并导入 @no__t 和 @no__t 命名空间。 除非指定 `-nostdlib` 选项，否则编译器将隐式引用 System.object 程序集。 @No__t-0 选项指示编译器不能用 Vbc 进行编译或自动引用 System.object 程序集。  
  
> [!NOTE]
> Mscorlib 和 Microsoft. .dll 程序集始终被引用。  
  
 您可以修改 Vbc 文件以指定应包括在每个 Vbc 编译中的其他编译器选项（指定 `-noconfig` 选项时除外）。 有关详细信息，请参阅 [@（指定响应文件）](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)。  
  
 编译器会处理最后传递到 `vbc` 命令的选项。 因此，命令行上的任何选项都将覆盖 Vbc 文件中相同选项的设置。  
  
> [!NOTE]
> 在 Visual Studio 开发环境中，不能使用 `-noconfig` 选项;仅当从命令行进行编译时，它才可用。  
  
## <a name="see-also"></a>请参阅

- [-nostdlib （Visual Basic）](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [@（指定响应文件）](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-reference （Visual Basic）](../../../visual-basic/reference/command-line-compiler/reference.md)
