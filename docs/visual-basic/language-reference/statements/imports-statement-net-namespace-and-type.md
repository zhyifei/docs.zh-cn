---
title: Imports 语句-.NET 命名空间和类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: a0b7a6a5fd16dc0daa620e6b490ddfdeb0e7c80e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912392"
---
# <a name="imports-statement-net-namespace-and-type"></a>Imports 语句（.NET 命名空间和类型）
允许引用类型名称, 而无需命名空间限定。  
  
## <a name="syntax"></a>语法  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`aliasname`|可选。 *导入别名*或代码可以引用`namespace`的名称, 而不是完全限定字符串。 请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|  
|`namespace`|必需。 要导入的命名空间的完全限定名称。 可以是嵌套到任何级别的命名空间的字符串。|  
|`element`|可选。 命名空间中声明的编程元素的名称。 可以是任何容器元素。|  
  
## <a name="remarks"></a>备注  
 `Imports`语句允许直接引用给定命名空间中包含的类型。  
  
 您可以提供单个命名空间名称或嵌套命名空间的字符串。 每个嵌套命名空间都用句点 (`.`) 从下一个更高的级别命名空间中分离, 如下面的示例所示。  
  
 `Imports System.Collections.Generic`  
  
 每个源文件可以包含任意多`Imports`个语句。 它们必须遵循任何选项声明, 如`Option Strict`语句, 它们必须位于任何编程元素声明 ( `Module`如或`Class`语句) 之前。  
  
 只能在文件`Imports`级别使用。 这意味着, 用于导入的声明上下文必须是一个源文件, 而不能是命名空间、类、结构、模块、接口、过程或块。  
  
 请注意, `Imports`该语句不会使其他项目和程序集中的元素可用于您的项目。 导入不会替代设置引用。 它只是不再需要限定已可用于你的项目的名称。 有关详细信息, 请参阅对已[声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)中的 "导入包含元素"。  
  
> [!NOTE]
> 您可以使用 " `Imports` [引用" 页 ("项目设计器")](/visualstudio/ide/reference/references-page-project-designer-visual-basic)定义隐式语句 (Visual Basic)。 有关详细信息，请参阅[如何：添加或删除导入的命名空间](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)(Visual Basic)。  
  
## <a name="import-aliases"></a>导入别名  
 *导入别名*定义命名空间或类型的别名。 如果需要使用一个或多个命名空间中声明的同名项, 则导入别名非常有用。 有关详细信息和示例, 请参阅对已[声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)中的 "限定元素名称"。  
  
 不应在模块级别使用与相同的名称`aliasname`声明成员。 如果这样做, 则 Visual Basic 编译器仅`aliasname`对已声明的成员使用, 而不再将其识别为导入别名。  
  
 尽管用于声明导入别名的语法与用于导入 XML 命名空间前缀的语法类似, 但结果不同。 导入别名可用作代码中的表达式, 而 XML 命名空间前缀只能在 XML 文本或 XML 轴属性中用作限定元素或属性名的前缀。  
  
### <a name="element-names"></a>元素名称  
 如果提供`element`, 则它必须表示一个*容器元素*, 即一个可以包含其他元素的编程元素。 容器元素包括类、结构、模块、接口和枚举。  
  
 `Imports`语句提供的元素的作用域取决于您是否指定`element`了。 如果仅`namespace`指定, 则该命名空间的所有唯一命名的成员以及该命名空间内的容器元素的成员均可使用而无需进行限定。 如果同时`namespace`指定和`element`, 则仅可使用该元素的成员而无需进行限定。  
  
## <a name="example"></a>示例  
 下面的示例返回 C:\ 中的所有文件夹<xref:System.IO.DirectoryInfo>目录。  
  
 该代码的顶部`Imports`没有语句。 因此, `DirectoryInfo`、 <xref:System.Text.StringBuilder>和<xref:Microsoft.VisualBasic.ControlChars.CrLf>引用均由命名空间完全限定。  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a>示例  
 下面的示例包含`Imports`引用的命名空间的语句。 因此, 无需使用命名空间完全限定类型。  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a>示例  
 下面的示例包含`Imports`为被引用命名空间创建别名的语句。 类型是用别名限定的。  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a>示例  
 下面的示例包含`Imports`为引用的类型创建别名的语句。 别名用于指定类型。  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a>请参阅

- [Namespace 语句](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [引用和 Imports 语句](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports 语句（XML 命名空间）](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [对已声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
