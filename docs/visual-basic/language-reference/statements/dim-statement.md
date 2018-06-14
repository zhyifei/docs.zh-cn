---
title: Dim 语句 (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: b3384b771748a1f2c9e841407042f81ce6ebe76d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234722"
---
# <a name="dim-statement-visual-basic"></a>Dim 语句 (Visual Basic)
声明，并为一个或多个变量分配存储空间。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a>部件  
  
-   `attributelist`  
  
     可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。  
  
-   `accessmodifier`  
  
     可选。 可以是以下各项之一：  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [受保护的友元](../../language-reference/modifiers/protected-friend.md)
    
    - [私有受保护](../../language-reference/modifiers/private-protected.md)

     请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
-   `Shared`  
  
     可选。 请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。  
  
-   `Shadows`  
  
     可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。  
  
-   `Static`  
  
     可选。 请参阅[静态](../../../visual-basic/language-reference/modifiers/static.md)。  
  
-   `ReadOnly`  
  
     可选。 请参阅[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。  
  
-   `WithEvents`  
  
     可选。 指定的这些引用可以引发事件的类的实例的对象变量。 请参阅[WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)。  
  
-   `variablelist`  
  
     必须的。 正在此语句中声明的变量的列表。  
  
     `variable [ , variable ... ]`  
  
     每个 `variable` 都具有以下语法和部件：  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |部件|描述|  
    |---|---|  
    |`variablename`|必须的。 变量的名称。 请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|  
    |`boundslist`|可选。 一个数组变量的每个维度的边界的列表。|  
    |`New`|可选。 创建类的新实例时`Dim`语句在运行时。|  
    |`datatype`|可选。 变量的数据类型。|  
    |`With`|可选。 引入了对象初始值设定项列表。|  
    |`propertyname`|可选。 类中的属性的名称进行的实例。|  
    |`propinitializer`|需要在之后`propertyname`=。 指出计算并将其分配给属性名的表达式。|  
    |`initializer`|可选如果`New`未指定。 计算并将其创建时分配给变量的表达式。|  
  
## <a name="remarks"></a>备注  
 Visual Basic 编译器使用`Dim`语句来确定变量的数据类型和其他信息，例如哪些代码可以访问该变量。 下面的示例声明一个变量以保存`Integer`值。  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 你可以指定任何数据类型或枚举、 结构、 类或接口的名称。  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 对于引用类型，你使用`New`关键字来创建类的新实例或结构指定的数据类型。 如果你使用`New`，您不使用初始值设定项表达式。 相反，你提供自变量，如有必要，将从其创建变量的类的构造函数。  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 你可以声明过程、 块、 类、 结构或模块中的变量。 不能声明源文件、 命名空间或接口中的变量。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 在模块级别，在任何过程中，外部声明的变量是*成员变量*或*字段*。 成员变量是在其类、 结构或模块整个范围内。 在过程级别声明的变量是*局部变量*。 本地变量为仅在它们的过程或块内的作用域中。  
  
 以下访问修饰符用于声明变量的过程之外： `Public`， `Protected`， `Friend`， `Protected Friend`，和`Private`。 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 `Dim`关键字是可选的并且通常忽略如果你指定任何以下修饰符： `Public`， `Protected`， `Friend`， `Protected Friend`， `Private`， `Shared`， `Shadows`， `Static`，`ReadOnly`，或`WithEvents`。  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 如果`Option Explicit`是 （默认值），编译器要求声明为你使用每个变量。 有关详细信息，请参阅[Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md)。  
  
## <a name="specifying-an-initial-value"></a>指定的初始值  
 创建时，你可以将值赋给变量。 对于值类型，你使用*初始值设定项*来提供要分配给变量的表达式。 表达式计算结果必须为一个常数，可以在编译时计算。  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 如果指定一个初始值设定项，并且数据类型中未指定`As`子句，*类型推理*用于推断初始值设定项中的数据类型。 在下面的示例中，同时`num1`和`num2`强类型为整数。 在第二个声明中，类型推理推断出类型 3 的值。  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 类型推理在过程级别适用。 它不适用于类、 结构、 模块或接口中的过程之外。 有关类型推理的详细信息，请参阅[Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)和[本地类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。  
  
 有关数据类型或初始值设定项未指定时，会发生什么情况的信息，请参阅[默认数据类型和值](../../../visual-basic/language-reference/statements/dim-statement.md#default)本主题中更高版本。  
  
 你可以使用*对象初始值设定项*声明命名类型和匿名类型的实例。 下面的代码创建的实例`Student`类，并使用对象初始值设定项来初始化属性。  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 有关对象初始值设定项的详细信息，请参阅[如何： 使用对象初始值设定项声明对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)，[对象初始值设定项： 命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)，和[匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="declaring-multiple-variables"></a>声明多个变量  
 您可以声明一个声明语句中的多个变量用括号指定为每个，并按照每个数组名称的变量名称。 以逗号分隔多个变量。  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 如果声明多个变量具有一个`As`子句，也不能提供该组的变量的初始值设定项。  
  
 你可以通过使用单独指定为不同的变量的不同的数据类型`As`子句为每个声明的变量。 每个变量采用中第一个指定的数据类型`As`子句遇到后其`variablename`一部分。  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>数组  
 你可以声明一个变量以保存*数组*，后者可以容纳多个值。 若要指定变量包含一个数组，请按照其`variablename`后面紧跟一对括号。 有关数组的详细信息，请参阅[数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)。  
  
 你可以指定的下限和上限的数组的每个维度。 若要执行此操作，包括`boundslist`在括号内。 为每个维度，`boundslist`指定上限和下限 （可选）。 下限始终为零，或不指定它是否。 每个索引可能会不同于通过其上界值零。  
  
 下面的两个语句是等效的。 每个语句声明数组 21`Integer`元素。 访问数组时，索引可能会不同于 0 到 20。  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 下面的语句声明类型的一个二维数组`Double`。 数组有 6 列 (5 + 1) 每个 4 行 (3 + 1)。 请注意，上限表示的索引，不维的长度的最大可能值。 维度的长度为上边界加 1。  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 数组可以有 1 到 32 的维度。  
  
 你可以将所有边界在一个数组声明以留空。 如果这样做，数组将具有你指定的维度数，但不会被初始化。 它具有的值`Nothing`之前至少初始化的某些元素。 `Dim`语句必须指定用于所有维度或任何维度的边界。  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 如果数组具有多个维度，必须包含以逗号分隔括号以指示维度数。  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 你可以声明*零长度数组*通过声明一个要为-1 的数组的维度。 包含一个零长度数组的变量不具有值`Nothing`。 零长度数组所需的某些公共语言运行时函数。 如果你尝试访问这样的数组，则会发生运行时异常。 有关详细信息，请参阅[数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)。  
  
 可以通过使用数组文本初始化的数组的值。 若要执行此操作，括住的初始化值用括号 (`{}`)。  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 对于多维数组，每个单独的维度的初始化括在外部的维度中的大括号中。 按行优先顺序来指定元素。  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 有关数组文本的详细信息，请参阅[数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)。  
  
##  <a name="default"></a> 默认数据类型和值  
 下表描述了指定 `Dim` 语句中数据类型和初始值设定项的各种组合的结果。  
  
|是否指定数据类型？|是否指定初始值设定项？|示例|结果|  
|---|---|---|---|  
|否|否|`Dim qty`|如果[Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)为 off （默认），则变量设置为`Nothing`。<br /><br /> 如果 `Option Strict` 处于打开状态，则发生编译时错误。|  
|否|是|`Dim qty = 5`|如果[Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)位于 （默认值），则变量采用数据类型的初始值设定项。 请参阅[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。<br /><br /> 如果 `Option Infer` 和 `Option Strict` 均处于关闭状态，则变量采用 `Object` 的数据类型。<br /><br /> 如果 `Option Infer` 处于关闭状态但 `Option Strict` 处于打开状态，则发生编译时错误。|  
|是|否|`Dim qty As Integer`|将变量初始化为数据类型的默认值。 请参阅本节后面的表。|  
|是|是|`Dim qty  As Integer = 5`|如果初始值设定项的数据类型不可转换为指定数据类型，则会发生编译时错误。|  
  
 如果你指定的数据类型，但不是指定初始值设定项，Visual Basic 将变量初始化为其数据类型的默认值。 下表显示的默认初始化值。  
  
|数据类型|默认值|  
|---|---|  
|所有数值类型 (包括`Byte`和`SByte`)|0|  
|`Char`|二进制 0|  
|所有引用类型 (包括`Object`， `String`，和所有数组)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|1 年 1 月 1 日 12:00 AM (01/01/0001 12:00:00 AM)|  
  
 一个结构的每个元素初始化就像它是单独的变量。 如果你声明一个数组的长度，但不是初始化它的元素，每个元素将初始化就像它是单独的变量。  
  
## <a name="static-local-variable-lifetime"></a>静态本地变量的生存期  
 A`Static`本地变量具有比在其中声明该过程的更长的生存期。 变量的生存期的边界依赖于过程的声明位置，以及是否有`Shared`。  
  
|过程声明|初始化变量|变量停止现有|  
|---|---|---|  
|模块中|在首次调用该过程|当程序停止执行|  
|在类或结构，过程是 `Shared`|第一次该过程称为某个特定实例上或对类或结构本身|当程序停止执行|  
|在类或结构，过程并不 `Shared`|第一次特定实例上调用过程|当垃圾回收 (GC) 释放该实例|  
  
## <a name="attributes-and-modifiers"></a>特性和修饰符  
 仅对成员变量上，而不是本地变量，你可以应用特性。 属性提供信息对程序集的元数据，这并没有意义的临时存储，例如本地变量。  
  
 在模块级别，不能使用`Static`修饰符来声明变量的成员。 在过程级别，不能使用`Shared`， `Shadows`， `ReadOnly`， `WithEvents`，或任何访问修饰符来声明本地变量。  
  
 你可以指定哪些代码可以通过提供访问变量`accessmodifier`。 类和模块成员 （任何过程） 之外的变量默认为私有访问，并使用结构成员变量默认的公共访问权限。 你可以调整其访问级别有访问修饰符。 不能在 （过程） 中的本地变量上使用访问修饰符。  
  
 你可以指定`WithEvents`仅在成员变量上，而不是上一个过程中本地变量。 如果指定`WithEvents`，该变量的数据类型必须是特定类类型，不`Object`。 你不能声明具有数组`WithEvents`。 有关事件的详细信息，请参阅[事件](../../../visual-basic/programming-guide/language-features/events/index.md)。  
  
> [!NOTE]
>  代码类之外，结构或模块必须限定该类、 结构或模块的名称的成员变量的名称。 之外的过程或块不能引用该过程或块中任何本地变量的代码。  
  
## <a name="releasing-managed-resources"></a>释放托管的资源  
 .NET Framework 垃圾回收器释放托管资源而无需您采取任何额外编码。 但是，你可以强制资源的托管资源而不是等待垃圾回收器释放。  
  
 如果一个类持有特别有价值且稀缺资源 （如数据库连接或文件句柄），你可能不想等待下一步的垃圾回收，以清理不再使用的类实例。 类可以实现<xref:System.IDisposable>接口提供一种方法来释放垃圾回收之前的资源。 实现该接口的类公开`Dispose`可以调用以进行强制宝贵的资源以立即释放的方法。  
  
 `Using`语句获取资源、 执行一组语句，然后释放资源的过程进行自动化。 但是，必须实现资源<xref:System.IDisposable>接口。 有关详细信息，请参阅 [Using 语句](../../../visual-basic/language-reference/statements/using-statement.md)。  
  
## <a name="example"></a>示例  
 下面的示例通过使用声明变量`Dim`语句使用各种选项。  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例列出介于 1 和 30 之间的质数。 代码注释中描述了本地变量的作用域。  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a>示例  
 在下面的示例中，`speedValue`在类级别声明变量。 `Private`关键字用于声明变量。 中的任何过程可以访问此变量`Car`类。  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
 [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [“项目设计器”->“编译”页 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [变量声明](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [对象初始值设定项：命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [对象初始值设定项：命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [如何：使用对象初始值设定项声明对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
