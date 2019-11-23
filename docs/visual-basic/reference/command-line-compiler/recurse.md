---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 71613af0f1c319801296180d49dbacfedf0ceca4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005258"
---
# <a name="-recurse"></a>-recurse
在指定目录或项目目录的所有子目录中编译源代码文件。  
  
## <a name="syntax"></a>语法  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>参数  
 `dir`  
 可选。 希望从中开始搜索的目录。 如果未指定，则从项目目录中开始搜索。  
  
 `file`  
 必需。 要搜索的文件。 允许通配符。  
  
## <a name="remarks"></a>备注  
 可以在文件名中使用通配符来编译项目目录中的所有匹配文件，而无需使用 `-recurse`。 如果未指定输出文件名，编译器将基于处理的第一个输入文件的输出文件名。 这通常是按字母顺序查看时所编译文件列表中的第一个文件。 出于此原因，最好使用 `-out` 选项来指定输出文件。  
  
> [!NOTE]
> `-recurse` 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 以下命令编译当前目录中的所有 Visual Basic 文件。  
  
```console
vbc *.vb  
```  
  
 以下命令编译 `Test\ABC` 目录及其下的所有目录中的所有 Visual Basic 文件，然后生成 `Test.ABC.dll`。  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-out （Visual Basic）](../../../visual-basic/reference/command-line-compiler/out.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
