---
title: 如何：声明常量 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: ce45e4df7f74cd68bde0fb2adba10197a11edb1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649732"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>如何：声明常量 (Visual Basic)
你使用`Const`语句以声明常量，并将其值设置。 通过声明一个常量，你将有意义的名称分配给一个值。 一旦声明一个常数，它无法修改或分配一个新值。  
  
 声明是固定的过程中或在模块、 类或结构的声明部分。 类或结构级别的常数`Private`默认情况下，但也可能声明为`Public`， `Friend`， `Protected`，或`Protected Friend`的适当级别的代码访问。  
  
 常量必须具有有效的符号名称 （规则是不同于用于创建变量的名称） 和构成的数字或字符串常量和运算符 （但不包括函数调用） 的表达式。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>若要声明常量  
  
-   编写包含访问说明符，声明`Const`关键字和一个表达式，如以下示例所示：  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     当[Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)是`Off`和[Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)是`On`，你必须通过指定数据类型来显式声明常量 (`Boolean`， `Byte`， `Char`， `DateTime`， `Decimal`， `Double`， `Integer`， `Long`， `Short`， `Single`，或`String`)。  
  
     当`Option Infer`是`On`或`Option Strict`是`Off`，你可以声明变量，而无需指定的数据类型`As`子句。 编译器确定常量的表达式的类型的类型。 有关详细信息，请参阅[常量和文本数据类型](constant-and-literal-data-types.md)。  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>若要声明常量具有显式指定的数据类型  
  
-   编写一个包括的声明`As`关键字和显式数据类型，如以下示例所示：  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     虽然你的代码的可读性更高，如果声明仅每行一个常量，您可以在单独的行，声明多个常量。 如果在同一行声明多个常数，它们必须都具有相同的访问级别 (`Public`， `Private`， `Friend`， `Protected`，或`Protected Friend`)。  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>可以在单独的行声明多个常量  
  
-   分隔声明与一个逗号和空格，如以下示例所示：  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>请参阅  
 [Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [常量和文本数据类型](constant-and-literal-data-types.md)  
 [常量概述](constants-overview.md)[如何： 声明常量](how-to-declare-a-constant.md)[用户定义的常量](user-defined-constants.md)[常量和 Literal 数据类型](constant-and-literal-data-types.md) [How to： 组相关的常量值一起](how-to-group-related-constant-values-together.md)[枚举概述](enumerations-overview.md)[如何： 声明枚举](how-to-declare-enumerations.md)[如何： 为枚举成员，请参阅](how-to-refer-to-an-enumeration-member.md)[枚举和名称限定](enumerations-and-name-qualification.md)[如何： 循环访问枚举](how-to-iterate-through-an-enumeration.md)[如何： 确定与枚举值关联的字符串](how-to-determine-the-string-associated-with-an-enumeration-value.md)[何时使用枚举](when-to-use-an-enumeration.md)

 [枚举概述](enumerations-overview.md)  
 [常量概述](constants-overview.md)  
 [如何： 声明枚举](how-to-declare-enumerations.md)  
 [枚举和名称限定](enumerations-and-name-qualification.md)  
 [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)
