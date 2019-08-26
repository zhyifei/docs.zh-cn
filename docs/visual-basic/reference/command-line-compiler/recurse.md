---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 4281c7bf5a7972d323e1e649aaef437c7ee901ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956262"
---
# <a name="-recurse"></a>-recurse
在指定目录或项目目录的所有子目录中编译源代码文件。  
  
## <a name="syntax"></a>语法  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>自变量  
 `dir`  
 可选。 希望从中开始搜索的目录。 如果未指定, 则从项目目录中开始搜索。  
  
 `file`  
 必需。 要搜索的文件。 允许通配符。  
  
## <a name="remarks"></a>备注  
 你可以在文件名中使用通配符, 以便在不使用`-recurse`的情况下编译项目目录中的所有匹配文件。 如果未指定输出文件名, 编译器将基于处理的第一个输入文件的输出文件名。 这通常是按字母顺序查看时所编译文件列表中的第一个文件。 出于此原因, 最好使用`-out`选项指定输出文件。  
  
> [!NOTE]
> 此`-recurse`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="example"></a>示例  
 以下命令编译当前目录中的所有 Visual Basic 文件。  
  
```console
vbc *.vb  
```  
  
 以下命令编译目录中的`Test\ABC`所有 Visual Basic 文件以及它下面的所有目录, 然后生成。 `Test.ABC.dll`  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
