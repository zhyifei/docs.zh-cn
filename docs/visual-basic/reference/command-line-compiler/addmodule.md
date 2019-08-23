---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 0e0915a2534f950cec074632a59750c3f96b679d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962460"
---
# <a name="-addmodule"></a>-addmodule
使编译器让指定文件中的所有类型信息可供当前正在编译的项目使用。  
  
## <a name="syntax"></a>语法  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>自变量  
 `fileList`  
 必需。 包含元数据但不包含程序集清单的文件的逗号分隔列表。 包含空格的文件名应括在引号 ("") 中。  
  
## <a name="remarks"></a>备注  
 `fileList`参数列出的文件必须`-target:module`使用选项创建, 或与另一个编译器等效于`-target:module`。  
  
 添加的`-addmodule`所有模块在运行时必须位于与输出文件相同的目录中。 也就是说, 您可以在编译时在任何目录中指定一个模块, 但该模块必须在运行时在应用程序目录中。 如果不是, 则<xref:System.TypeLoadException>会出现错误。  
  
 如果指定 (隐式或显式) 除`-target:module` with `-addmodule`之外的任何[目标 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)选项, 则传递到`-addmodule`的文件将成为项目的程序集的一部分。 需要一个程序集来运行包含一个或多个添加了`-addmodule`文件的输出文件。  
  
 使用[/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)从包含程序集的文件导入元数据。  
  
> [!NOTE]
> 此`-addmodule`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="example"></a>示例  
 下面的代码将创建一个模块。  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 下面的代码将导入模块的类型。  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 当你运行`t1`时, 它`802`将输出。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
