---
title: Namespace 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
ms.openlocfilehash: 15d8d8185d895502df594bbd931443af604bef67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604857"
---
# <a name="namespace-statement"></a>Namespace 语句
声明命名空间的名称，并使遵循声明在该命名空间中进行编译的源代码。  
  
## <a name="syntax"></a>语法  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a>部件  
 Global  
 可选。 允许你定义超出你的项目的根命名空间的命名空间。 请参阅[在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)。  
  
 `name`  
 必须的。 用于标识命名空间的唯一名称。 必须是有效的 Visual Basic 标识符。 有关详细信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。  
  
 `componenttypes`  
 可选。 构成命名空间的元素。 这些组件包括但不限于枚举、 结构、 接口、 类、 模块、 委托和其他命名空间。  
  
 `End Namespace`  
 终止`Namespace`块。  
  
## <a name="remarks"></a>备注  
 命名空间用作组织的系统。 它们提供了如何进行分类和呈现公开给其他程序和应用程序的编程元素。 请注意，命名空间不是*类型*在类或结构的意义上，你不能声明编程元素具有一个命名空间的数据类型。  
  
 所有的编程元素声明后`Namespace`语句属于该命名空间。 Visual Basic 继续编译为最后一个声明命名空间的元素，直到它遇到上述任何一`End Namespace`语句或另一个`Namespace`语句。  
  
 如果已定义一个命名空间，甚至在项目之外，你可以向其添加编程元素。 若要执行此操作，请使用`Namespace`语句来直接 Visual Basic 要编译到该命名空间的元素。  
  
 你可以使用`Namespace`语句只能在文件或命名空间级别。 这意味着*声明上下文*命名空间必须为源文件或另一个命名空间，并且不能为类、 结构、 模块、 接口或过程。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 您可以声明在另一个命名空间。 没有可以声明，但请记住，当其他代码访问最内部的命名空间中声明的元素，它必须使用限定字符串，其中包含嵌套层次结构中的所有命名空间名称的嵌套的级别严格限制。  
  
## <a name="access-level"></a>访问级别  
 命名空间将其视为好像它们具有`Public`访问级别。 从任何位置中同一项目的代码、 其他引用该项目的项目和项目中生成的任何程序集，可以访问命名空间。  
  
 在命名空间级别，这意味着命名空间中但不是在任何其他元素内声明的编程元素可以具有`Public`或`Friend`访问。 如果未指定，使用此类的访问级别元素`Friend`默认情况下。 可以在命名空间级别声明的元素包括类、 结构、 模块、 接口、 枚举和委托。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
## <a name="root-namespace"></a>根 Namespace  
 基于项目中的所有命名空间名称*根命名空间*。 Visual Studio 针对项目中的所有代码，将项目名称指定为默认根命名空间。 例如，如果项目命名为 `Payroll`，则其编程元素属于命名空间 `Payroll`。 如果你声明`Namespace funding`，该命名空间的全名是`Payroll.funding`。  
  
 如果你想要指定现有的命名空间中`Namespace`语句，如在泛型列表类示例中，你可以将根命名空间设置为 null 值。 若要执行此操作，请单击**项目属性**从**项目**菜单，然后再清除**根命名空间**条目，以便此框为空。 如果您不未在泛型列表的类示例执行此操作，将需要 Visual Basic 编译器`System.Collections.Generic`作为新的命名空间在项目中`Payroll`，使用的完整名称`Payroll.System.Collections.Generic`。  
  
 或者，可以使用`Global`关键字来引用在项目外部定义的命名空间的元素。 这样可使您保留您的根命名空间的项目名称。 这可以减少的无意中将编程元素以及现有命名空间的机会。 有关详细信息，请参阅中的"全局关键字中完全限定名称"一节[在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)。  
  
 `Global`关键字还可在一个 Namespace 语句中。 这将允许你定义项目根命名空间之外的命名空间。 有关详细信息，请参阅"全局关键字中 Namespace 语句"一节中的[在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)。  
  
 **故障排除。** 根命名空间可能会导致发生意外的命名空间名称的串联。 如果你对进行引用在项目外部定义的命名空间，Visual Basic 编译器可以 construe 它们作为根命名空间中的嵌套命名空间。 在这种情况下，编译器无法识别已在外部命名空间中定义的任何类型。 若要避免此问题，请设置为"根 Namespace，"中所述的 null 值的根命名空间，或使用`Global`来访问的外部命名空间元素的关键字。  
  
## <a name="attributes-and-modifiers"></a>特性和修饰符  
 不能将属性应用到命名空间。 属性提供信息对程序集的元数据，这并没有意义对于源分类器，例如命名空间。  
  
 不能应用到命名空间的任何访问或过程修饰符或任何其他修饰符。 因为它是一种类型，则这些修饰符没有意义。  
  
## <a name="example"></a>示例  
 下面的示例声明两个命名空间，嵌套在另一个。  
  
 [!code-vb[VbVbalrStatements#43](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例声明多个嵌套的命名空间在单独的行，并且等效于前面的示例。  
  
 [!code-vb[VbVbalrStatements#41](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_2.vb)]  
  
## <a name="example"></a>示例  
 以下示例访问前面的示例中定义的类。  
  
 [!code-vb[VbVbalrStatements#42](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_3.vb)]  
  
## <a name="example"></a>示例  
 下面的示例定义一个新的泛型列表类的主干并将其添加到<xref:System.Collections.Generic?displayProperty=nameWithType>命名空间。  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>请参阅  
 [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [已声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)
