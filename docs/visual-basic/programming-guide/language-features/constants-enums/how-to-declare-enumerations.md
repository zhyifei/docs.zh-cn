---
title: 如何：声明枚举
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 042aea045313bcaf3832274acf1000f87a084b72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354049"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>如何：声明枚举 (Visual Basic)
在类或模块的声明部分中，使用 `Enum` 语句创建枚举。 不能在方法中声明枚举。 若要指定适当的访问级别，请使用 `Private`、`Protected`、`Friend`或 `Public`。  
  
 `Enum` 类型具有名称、基础类型和字段集，每个字段都表示一个常量。 该名称必须是有效的 Visual Basic .NET 限定符。 基础类型必须是整数类型之一-`Byte`、`Short`、`Long` 或 `Integer`。 默认值为 `Integer`。 枚举总是强类型化的，并且不能与整数类型互换。  
  
 枚举的值不能为浮点值。 如果为枚举分配了 `Option Strict On`的浮点值，则会产生编译器错误。 如果 `Off``Option Strict`，则该值会自动转换为 `Enum` 类型。  
  
 有关名称的信息，以及如何使用 `Imports` 语句使名称限定不必要，请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。  
  
### <a name="to-declare-an-enumeration"></a>声明枚举  
  
1. 编写包含代码访问级别、`Enum` 关键字和有效名称的声明，如下面的示例所示，其中每个都声明了不同的 `Enum`。  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. 定义枚举中的常量。 默认情况下，枚举中的第一个常量被初始化为 `0`，后面的常量被初始化为比上一个常数大1的值。 例如，下面的枚举 `Days`包含一个名为 `Sunday` 的常量，该常量的值为 `0`、一个名为 `Monday`、值为 `1`、一个名为 `Tuesday`、值为 `2`的常量等。  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. 可以使用赋值语句将值显式分配给枚举中的常量。 可以分配任何整数值，包括负数。 例如，您可能希望值小于零的常量表示错误条件。 在以下枚举中，会将值显式赋给常量 `Invalid` `–1`，并为常量 `Sunday` 分配值 `0`。 由于它是枚举中的第一个常数，因此 `Saturday` 也初始化为 `0`值。 `1` `Monday` 的值（一个大于 `Sunday`的值）;`Tuesday` 的值 `2`等。  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>将枚举声明为显式类型  
  
- 使用 `As` 子句指定枚举的类型，如下面的示例中所示。  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>另请参阅

- [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [如何：引用枚举成员](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [如何：在 Visual Basic 中循环访问枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [如何：确定与枚举值关联的字符串](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [何时使用枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [常量概述](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [常量和文本数据类型](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)
