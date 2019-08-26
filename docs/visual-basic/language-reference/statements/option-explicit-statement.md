---
title: Option Explicit 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: c027964d185d7f69c0a56a4386bedc2d8f9d2eac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912340"
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit 语句 (Visual Basic)
强制显式声明文件中的所有变量, 或允许隐式声明变量。  
  
## <a name="syntax"></a>语法  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>部件  
 `On`  
 可选。 启用`Option Explicit`检查。 如果`On`未`Off`指定或, 则默认值为`On`。  
  
 `Off`  
 可选。 禁用`Option Explicit`检查。  
  
## <a name="remarks"></a>备注  
 当`Option Explicit On`或`Option Explicit`出现在文件中时, 必须使用`Dim`或`ReDim`语句显式声明所有变量。 如果尝试使用未声明的变量名称, 则会在编译时出现错误。 `Option Explicit Off`语句允许隐式声明变量。  
  
 使用时，`Option Explicit` 语句必须在文件中任何其他源代码语句之前。  
  
> [!NOTE]
> 将`Option Explicit`设置`Off`为通常不是好的做法。 在一个或多个位置拼错变量名称，将会在程序运行时导致意想不到的结果。  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>当选项显式语句不存在时  
 如果源代码不包含`Option Explicit`语句, 则使用 "编译" 页上的 " **Option Explicit** " 设置, 将使用[项目设计器 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 。 如果使用命令行编译器, 则使用[/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)编译器选项。  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>在 IDE 中设置 Option Explicit  
  
1. 在“解决方案资源管理器”中，选择一个项目。 在“项目”菜单上，单击“属性”。  
  
2. 单击“编译”选项卡。  
  
3. 在 "**选项**" 框中设置值。  
  
 创建新项目时, "**编译**" 选项卡上的 " **option explicit** " 设置设置为 " **VB 默认值**" 对话框中的 "选项" "**显式**设置"。 若要访问 " **VB 默认值**" 对话框, 请在 "**工具**" 菜单上单击 "**选项**"。 在“选项”对话框中，展开“项目和解决方案”，然后单击“VB 默认值”。 **VB 默认**设置中的初始默认设置`On`为。  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>在命令行上设置 Option Explicit  
  
- 在**vbc**命令中包含[/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)编译器选项。  
  
## <a name="example"></a>示例  
 下面的示例使用`Option Explicit`语句强制所有变量的显式声明。 尝试使用未声明的变量会导致编译时错误。  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>请参阅

- [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)
- [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [“选项”对话框 ->“项目”->“Visual Basic 默认值”](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
