---
title: Option Explicit 语句
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
ms.openlocfilehash: 3c70d958fdcbb1782af22c3a4715676abbeeac0c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353789"
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit 语句 (Visual Basic)
Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.  
  
## <a name="syntax"></a>语法  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>部件  
 `On`  
 可选。 Enables `Option Explicit` checking. If `On` or `Off` is not specified, the default is `On`.  
  
 `Off`  
 可选。 Disables `Option Explicit` checking.  
  
## <a name="remarks"></a>备注  
 When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements. If you try to use an undeclared variable name, an error occurs at compile time. The `Option Explicit Off` statement allows implicit declaration of variables.  
  
 使用时，`Option Explicit` 语句必须在文件中任何其他源代码语句之前。  
  
> [!NOTE]
> Setting `Option Explicit` to `Off` is generally not a good practice. 在一个或多个位置拼错变量名称，将会在程序运行时导致意想不到的结果。  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>When an Option Explicit Statement Is Not Present  
 If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used. If the command-line compiler is used, the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>To set Option Explicit in the IDE  
  
1. 在“解决方案资源管理器”中，选择一个项目。 在“项目”菜单上，单击“属性”。  
  
2. 单击“编译”选项卡。  
  
3. Set the value in the **Option Explicit** box.  
  
 When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box. To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**. 在“选项”对话框中，展开“项目和解决方案”，然后单击“VB 默认值”。 The initial default setting in **VB Defaults** is `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>To set Option Explicit on the command line  
  
- Include the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.  
  
## <a name="example"></a>示例  
 The following example uses the `Option Explicit` statement to force explicit declaration of all variables. Attempting to use an undeclared variable causes an error at compile time.  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>请参阅

- [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)
- [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [“选项”对话框 ->“项目”->“Visual Basic 默认值”](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
