---
title: Enum 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: 89de51f2551437d102ccdc5a0f1ff5f23b53e47f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="enum-statement-visual-basic"></a>Enum 语句 (Visual Basic)
声明枚举，并定义其成员的值。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a>部件  
  
-   `attributelist`  
  
     可选。 应用于此枚举属性的列表。 必须将括[特性列表](../../../visual-basic/language-reference/statements/attribute-list.md)中命令的尖括号 ("`<`"和"`>`")。  
  
     <xref:System.FlagsAttribute>特性指示实例的枚举的值可以包含多个枚举成员，并且每个成员表示中的枚举值的位字段。  
  
-   `accessmodifier`  
  
     可选。 指定哪些代码可以访问此枚举。 可以是以下各项之一：  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
     你可以指定`Protected``Friend`以允许从中枚举的类、 派生的类中或同一程序集中的代码的访问。  
  
-   `Shadows`  
  
     可选。 指定此枚举重新声明并隐藏具有相同名称的编程元素或在基类中的重载元素集。 你可以指定[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)仅限于在枚举本身，不在它的任何成员。  
  
-   `enumerationname`  
  
     必须的。 枚举的名称。 有关有效的名称的信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。  
  
-   `datatype`  
  
     可选。 在枚举及其所有成员的数据类型。  
  
-   `memberlist`  
  
     必须的。 正在此语句中声明的成员常量的列表。 在单个源代码行上显示多个成员。  
  
     每个`member`具有以下语法和部件： `[<attribute list>] member name [ = initializer ]`  
  
    |部件|描述|  
    |---|---|  
    |`membername`|必须的。 此成员的名称。|  
    |`initializer`|可选。 在编译时计算并将其分配给此成员的表达式。|  
  
-   `End` `Enum`  
  
     终止 `Enum` 块。  
  
## <a name="remarks"></a>备注  
 如果你有一组逻辑上彼此相关的不变值，您可以在枚举中一起定义它们。 这提供为该枚举的成员，可以更方便地记住比它们的值有意义的名称。 然后，你可以在你的代码在很多位置使用枚举成员。  
  
 使用枚举的好处包括：  
  
-   这样可以减少错误引起的转置或键入数字。  
  
-   便于在以后更改值。  
  
-   使代码易于阅读，这意味着它很少出现，将引入错误。  
  
-   确保向前兼容性。 如果你使用枚举，则你的代码就很难如果有人在将来更改成员名称所对应的值失败。  
  
 枚举具有名称、 一个基础的数据类型和一组的成员。 每个成员表示一个常量。  
  
 在类、 结构、 模块或接口级别，在任何过程中，外部声明的枚举是*成员枚举*。 它是类、 结构、 模块或接口声明它的成员。  
  
 成员枚举可以是从任何位置访问其类、 结构、 模块或接口。 代码类之外，结构或模块必须使用限定成员枚举的名称替换该类、 结构或模块的名称。 你可以避免需要通过添加使用完全限定的名[导入](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)到源代码文件的语句。  
  
 在命名空间级别，任何类、 结构、 模块或接口，外部声明的枚举是它在其中出现的命名空间的成员。  
  
 *声明上下文*枚举必须为源文件、 命名空间、 类、 结构、 模块或接口，并且不能为一个过程。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 你可以将特性应用于枚举作为一个整体，但不适用于其成员单独。 属性提供对程序集的元数据的信息。  
  
## <a name="data-type"></a>数据类型  
 `Enum`语句可以声明枚举的数据类型。 每个成员采用枚举的数据类型。 你可以指定`Byte`， `Integer`， `Long`， `SByte`， `Short`， `UInteger`， `ULong`，或`UShort`。  
  
 如果不指定`datatype`枚举，对于每个成员进行的数据类型及其`initializer`。 如果同时指定了`datatype`和`initializer`的数据类型`initializer`必须可转换为`datatype`。 如果既没有`datatype`也不`initializer`存在，则数据类型默认为`Integer`。  
  
## <a name="initializing-members"></a>初始化成员  
 `Enum`语句可以初始化中的所选成员的内容`memberlist`。 你使用`initializer`来提供要分配给该成员的表达式。  
  
 如果不指定`initializer`成员，Visual Basic 对其进行初始化为零 (如果它是第一个`member`中`memberlist`)，或通过比前一个更大值`member`。  
  
 在每个提供的表达式`initializer`可以是文本、 已定义，其他常量和已定义，包括以前的此枚举成员的枚举成员的任意组合。 可以使用算术和逻辑运算符来组合这些元素。  
  
 不能使用变量或函数中的`initializer`。 但是，可以使用转换关键字如`CByte`和`CShort`。 你还可以使用`AscW`如果调用与一个常量`String`或`Char`自变量，因为可以在编译时计算的。  
  
 枚举不能具有浮点值。 如果一个成员分配了浮点值和`Option Strict`被设置为 on，则编译器将发生错误。 如果`Option Strict`处于关闭状态，值自动转换为`Enum`类型。  
  
 如果成员的值超出允许的范围的基础的数据类型，或者如果初始化到基础数据类型所允许的最大值的任何成员，则编译器将报告错误。  
  
## <a name="modifiers"></a>修饰符  
 类、 结构、 模块和接口成员枚举默认为公共访问。 你可以调整其访问级别有访问修饰符。 Namespace 成员枚举默认为友元访问权限。 你可以调整其访问级别公共的但不是属于私有或受保护。 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 所有枚举成员都具有公共访问权限，并且不能对它们使用任何访问修饰符。 但是，如果在枚举本身的更受限制的访问级别，指定的枚举访问级别优先。  
  
 默认情况下，所有枚举都是类型，其字段都是常量。 因此`Shared`， `Static`，和`ReadOnly`声明枚举或其成员时，不能使用关键字。  
  
## <a name="assigning-multiple-values"></a>分配多个值  
 枚举通常表示互相排斥的值。 通过包括<xref:System.FlagsAttribute>属性中`Enum`声明中，你可以改为多个将值分配给枚举的实例。 <xref:System.FlagsAttribute>属性指定在枚举视为位域，即一组标志。 这些应用程序称为*按位*枚举。  
  
 当通过使用声明枚举<xref:System.FlagsAttribute>属性中，我们建议你使用的 2，这是、 1、 2、 4、 8、 16 和等等，幂的值。 我们还建议"None"是其值为 0 的成员的名称。 有关其他指南，请参阅<xref:System.FlagsAttribute>和<xref:System.Enum>。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`Enum`语句。 请注意，该成员称为`EggSizeEnum.Medium`，而不是作为`Medium`。  
  
 [!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例中的方法之外，则`Egg`类。 因此，`EggSizeEnum`是作为完全限定`Egg.EggSizeEnum`。  
  
 [!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]  
  
## <a name="example"></a>示例  
 下面的示例使用`Enum`语句以定义一组相关的名为常量值。 在此示例中的值是你可能选择设计数据库的数据输入窗体的颜色。  
  
 [!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]  
  
## <a name="example"></a>示例  
 下面的示例演示包括正数和负数的值。  
  
 [!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]  
  
## <a name="example"></a>示例  
 在下面的示例中，`As`子句用于指定`datatype`的枚举。  
  
 [!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用按位枚举。 可以将多个值分配到的按位枚举的实例。 `Enum`声明包括<xref:System.FlagsAttribute>属性，指示可以将枚举视为一组标志。  
  
 [!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]  
  
## <a name="example"></a>示例  
 下面的示例循环访问枚举。 它使用<xref:System.Enum.GetNames%2A>方法来检索枚举中的成员名称的数组和<xref:System.Enum.GetValues%2A>检索成员值的数组。  
  
 [!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Enum>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [隐式转换和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [常量和枚举](../../../visual-basic/language-reference/constants-and-enumerations.md)
