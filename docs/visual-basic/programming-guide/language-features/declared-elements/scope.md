---
title: Visual Basic 中的范围
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: d6692379626d787b728d6e92bd447c4a96e6680e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656290"
---
# <a name="scope-in-visual-basic"></a>Visual Basic 中的范围
*作用域*的已声明的元素是一组的所有代码都可以引用它而无需限定其名称或提供通过[Imports 语句 （.NET Namespace 和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。 元素可在以下级别之一具有作用域：  
  
|级别|描述|  
|-----------|-----------------|  
|块范围|仅在代码中的可用块中，在其中声明|  
|过程范围|适用于在其中声明过程中的所有代码|  
|模块作用域|适用于在模块、 类或结构声明它的所有代码|  
|Namespace 作用域|适用于在其中声明命名空间中的所有代码|  
  
 这些级别的作用域进度从窄 （块） 到最宽 （命名空间），其中*范围最小*意味着可以引用而无需限定元素的代码的最小集。 有关详细信息，请参阅此页上的"级别的作用域"。  
  
## <a name="specifying-scope-and-defining-variables"></a>指定作用域，以及定义变量  
 在声明它时，你指定的元素的范围。 作用域可以依赖于以下因素：  
  
-   在其中声明该元素的区域 （块、 过程、 模块、 类或结构）  
  
-   包含元素的声明的命名空间  
  
-   为元素声明其访问级别  
  
 时务必小心你定义变量具有相同名称但不同的范围内，因为这样做会导致意外的结果。 有关详细信息，请参阅 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。  
  
## <a name="levels-of-scope"></a>级别的作用域  
 编程元素是可在声明它的区域可用。 同一区域中的所有代码中，可以都指无需限定其名称的元素。  
  
### <a name="block-scope"></a>块范围  
 块是一组语句括在启动和终止声明语句，如下所示：  
  
-   `Do` 和 `Loop`  
  
-   `For` [`Each`] 和 `Next`  
  
-   `If` 和 `End If`  
  
-   `Select` 和 `End Select`  
  
-   `SyncLock` 和 `End SyncLock`  
  
-   `Try` 和 `End Try`  
  
-   `While` 和 `End While`  
  
-   `With` 和 `End With`  
  
 如果声明块内的变量，则可以仅在该块中使用它。 在下面的示例中，整数变量的作用域`cube`是之间块`If`和`End If`，和可以不再指`cube`时将执行传递到块之外。  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  即使变量的作用域仅限于一个块，其生存期内仍为整个过程。 如果在过程不止一次进入该块，每个块变量将保留以前的值。 若要避免这种情况中的出现意外的结果，明智的做法是在块的开头的块变量进行初始化。  
  
### <a name="procedure-scope"></a>过程范围  
 声明过程中的元素不可用该过程外。 仅包含声明的过程可以使用它。 在此级别的变量是也称为*局部变量*。 声明它们与[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)、 带有或不带[静态](../../../../visual-basic/language-reference/modifiers/static.md)关键字。  
  
 密切相关过程和块作用域。 如果声明的变量在过程中，而在该过程中的任何块外，你可以将该变量看作具有块范围，其中块就是整个过程。  
  
> [!NOTE]
>  所有本地元素，即使它们是`Static`变量，是专用于在其中它们出现的过程。 你不能声明任何元素使用[公共](../../../../visual-basic/language-reference/modifiers/public.md)过程中的关键字。  
  
### <a name="module-scope"></a>模块作用域  
 为方便起见，单个字词*模块级别*同样适用于模块、 类和结构。 可以通过将任何过程或块外部，但在模块、 类或结构内声明语句放在声明此级别的元素。  
  
 当您在模块级别的声明，你选择的访问级别将确定的作用域。 包含模块、 类或结构的命名空间还会影响范围。  
  
 为其声明的元素[私有](../../../../visual-basic/language-reference/modifiers/private.md)访问级别有在该模块中，每个过程但不是属于另一个模块中的任何代码。 `Dim`在模块级别的语句默认为`Private`如果不使用任何访问级别关键字。 但是，你可以进行的作用域和访问级别更明显使用`Private`中的关键字`Dim`语句。  
  
 在下面的示例中，在模块中定义的所有过程可以都引用的字符串变量`strMsg`。 当调用第二个过程时，它将显示的字符串变量的内容`strMsg`在对话框中。  
  
```  
' Put the following declaration at module level (not in any procedure).  
Private strMsg As String  
' Put the following Sub procedure in the same module.  
Sub initializePrivateVariable()  
    strMsg = "This variable cannot be used outside this module."  
End Sub  
' Put the following Sub procedure in the same module.  
Sub usePrivateVariable()  
    MsgBox(strMsg)  
End Sub  
```  
  
### <a name="namespace-scope"></a>Namespace 作用域  
 如果在模块级别使用的某个元素声明[友元](../../../../visual-basic/language-reference/modifiers/friend.md)或[公共](../../../../visual-basic/language-reference/modifiers/public.md)关键字，它可供整个在其中声明该元素的命名空间的所有过程。 与前面的示例中，字符串变量到以下内容有变更`strMsg`可以通过其声明的命名空间中的任意位置的代码引用。  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 Namespace 作用域包括嵌套的命名空间。 可从命名空间内的元素也会从任何嵌套在该命名空间的命名空间内提供。  
  
 如果你的项目不包含任何[Namespace 语句](../../../../visual-basic/language-reference/statements/namespace-statement.md)s，项目中的所有内容是相同的命名空间中。 在这种情况下，可以将命名空间范围看作项目作用域。 `Public` 模块、 类或结构中的元素也是可用于任何引用其项目的项目。  
  
## <a name="choice-of-scope"></a>选择的作用域  
 在声明变量时，你应时需要牢记以下几点选择其作用域。  
  
### <a name="advantages-of-local-variables"></a>本地变量的优点  
 本地变量为适合于任何类型的临时计算，原因如下：  
  
-   **避免名称冲突。** 本地变量的名称不容易发生冲突。 例如，你可以创建包含名为的变量的多个不同过程`intTemp`。 只要每个`intTemp`声明为局部变量，则每个过程识别其自己的版本的`intTemp`。 任何一个过程可以更改其本地中的值`intTemp`而不会影响`intTemp`其他过程中的变量。  
  
-   **内存消耗。** 仅在正在运行其过程时，本地变量占用的内存。 当过程返回到调用代码，会释放其内存。 与此相反，[共享](../../../../visual-basic/language-reference/modifiers/shared.md)和[静态](../../../../visual-basic/language-reference/modifiers/static.md)变量消耗内存资源，直到你的应用程序停止运行，因此，它们仅在必要时使用。 *实例变量*占用内存时其实例将继续存在，这使它们成为小于效率低于本地变量，但可能比效率更高`Shared`或`Static`变量。  
  
### <a name="minimizing-scope"></a>最小化作用域  
 一般情况下，声明的任何变量或常量，时很好的编程做法，应尽可能窄的范围 （块作用域是范围最小）。 这有助于节省内存，并最大程度减少你错误地引用错误的变量的代码的可能性。 同样，你应将变量声明为[静态](../../../../visual-basic/language-reference/modifiers/static.md)仅当有必要在保留其过程调用之间的值。  
  
## <a name="see-also"></a>请参阅  
 [已声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [如何：控制变量的范围](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [在 Visual Basic 中的生存期](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [在 Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
