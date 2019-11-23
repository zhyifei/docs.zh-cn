---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: fd0875f09bf3ba7211ede500aa0da45f8b7cd2c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344767"
---
# <a name="-define-visual-basic"></a>-define (Visual Basic)
定义条件编译器常数。  
  
## <a name="syntax"></a>语法  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

或

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`symbol`|必须的。 要定义的符号。|  
|`value`|可选。 指派给 `symbol` 的值。 If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks. 如果未指定值，则视为 True。|  
  
## <a name="remarks"></a>备注  
 The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.  
  
 可以将由此选项创建的符号同 `#If`...`Then`...`#Else` 指令一起使用，以对源文件进行条件编译。  
  
 `-d` 是 `-define` 的缩写形式。  
  
 通过使用逗号分隔符号定义，可以用 `-define` 定义多个符号。  
  
|在 Visual Studio 集成开发环境中设置/定义|  
|---|  
|1.  Have a project selected in **Solution Explorer**. 在“项目”菜单上，单击“属性”。 <br />2.  Click the **Compile** tab.<br />3.  Click **Advanced**.<br />4.  Modify the value in the **Custom Constants** box.|  
  
## <a name="example"></a>示例  
 下面的代码定义并使用两个条件编译器常数。  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [#Const 指令](../../../visual-basic/language-reference/directives/const-directive.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
