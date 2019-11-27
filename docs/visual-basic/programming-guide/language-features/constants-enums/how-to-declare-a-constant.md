---
title: 如何：声明常量
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
ms.openlocfilehash: 5054d4a4fc02d8bd22efceb01770fc54167d8cb3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347469"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>如何：声明常量 (Visual Basic)
使用 `Const` 语句声明一个常数并设置其值。 通过声明常量，可为一个值指定一个有意义的名称。 声明常量后，不能对其进行修改或赋予新值。  
  
 您可以在过程中或模块、类或结构的声明部分中声明常数。 默认情况下，类或结构级别常量是 `Private` 的，但也可以声明为适当级别的代码访问的 `Public`、`Friend`、`Protected`或 `Protected Friend`。  
  
 常数必须具有有效的符号名称（这些规则与用于创建变量名称的规则相同）以及由数值或字符串常量和运算符组成的表达式（但不包含函数调用）。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>声明常量  
  
- 编写包含访问说明符、`Const` 关键字和表达式的声明，如下面的示例所示：  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     当[选项推断](../../../../visual-basic/language-reference/statements/option-infer-statement.md)为 `Off` 并且[option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) `On`时，必须通过指定数据类型（`Boolean`、`Byte`、`Char`、`DateTime`、`Decimal`、`Double`、`Integer`、`Long`、`Short`、`Single`或 `String`）显式声明常量。  
  
     如果 `Option Infer` `On` 或 `Option Strict` `Off`，则可以声明常量，而无需使用 `As` 子句指定数据类型。 编译器将确定表达式的类型的常量类型。 有关详细信息，请参阅[常量和文本数据类型](constant-and-literal-data-types.md)。  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>声明具有显式声明的数据类型的常数  
  
- 编写包含 `As` 关键字和显式数据类型的声明，如以下示例中所示：  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     可以在单个行上声明多个常数，不过，如果每行只声明一个常数，代码的可读性就会更高。 如果在一行上声明多个常量，它们必须具有相同的访问级别（`Public`、`Private`、`Friend`、`Protected`或 `Protected Friend`）。  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>在单个行上声明多个常量  
  
- 使用逗号和空格分隔声明，如下面的示例所示：  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>另请参阅

- [Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)
- [常量和文本数据类型](constant-and-literal-data-types.md)
- [常量概述](constants-overview.md)
- [如何：声明常量](how-to-declare-a-constant.md)
- [用户定义的常量](user-defined-constants.md)
- [常量和文本数据类型](constant-and-literal-data-types.md)
- [如何：将相关的常量值组合在一起](how-to-group-related-constant-values-together.md)
- [枚举概述](enumerations-overview.md)
- [如何：声明枚举](how-to-declare-enumerations.md)
- [如何：引用枚举成员](how-to-refer-to-an-enumeration-member.md)
- [枚举和名称限定](enumerations-and-name-qualification.md)
- [如何：循环访问枚举](how-to-iterate-through-an-enumeration.md)
- [如何：确定与枚举值关联的字符串](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [何时使用枚举](when-to-use-an-enumeration.md)

- [枚举概述](enumerations-overview.md)
- [常量概述](constants-overview.md)
- [如何：声明枚举](how-to-declare-enumerations.md)
- [枚举和名称限定](enumerations-and-name-qualification.md)
- [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)
