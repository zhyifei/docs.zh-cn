---
title: 其他数据类型
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: cc6262b5bb305bb839917e222d831fa3340a1b14
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346337"
---
# <a name="miscellaneous-data-types-visual-basic"></a>其他数据类型 (Visual Basic)
Visual Basic 提供了多种数据类型，这些数据类型不是面向数字或字符。 而是处理专用数据，如 "是/否" 值、日期/时间值和对象地址。  
  
 有关显示 Visual Basic 数据类型的并行比较的表，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/index.md)。  
  
## <a name="boolean-type"></a>布尔类型  
 [Boolean 数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)是一种无符号值，被解释为 `True` 或 `False`。 其数据宽度取决于实现平台。 如果变量只能包含两个状态值，如 true/false、yes/no 或 on/off，则将其声明为 `Boolean`。  
  
## <a name="date-type"></a>日期类型  
 [日期数据类型](../../../../visual-basic/language-reference/data-types/date-data-type.md)是包含日期和时间信息的64位值。 每个增量表示从公历第1年1月1日开始（12:00 AM）起所用时间的100毫微秒。 如果变量可以包含日期值和/或时间值，则将其声明为 `Date`。  
  
## <a name="object-type"></a>“对象类型”  
 [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)是一个32位地址，它指向应用程序或其他应用程序中的对象实例。 `Object` 变量可以引用应用程序识别的任何对象，或引用任何数据类型的数据。 这包括*值类型*（例如 `Integer`、`Boolean`和结构实例）和*引用类型*（即从 `String` 和 <xref:System.Windows.Forms.Form>等类创建的对象的实例）以及数组实例。  
  
 如果变量存储指向在编译时不知道的类的实例的指针，或者如果该变量可以指向各种数据类型的数据，则将其声明为 `Object`。  
  
 `Object` 数据类型的优点在于，您可以使用它来存储任何数据类型的数据。 缺点是您会产生额外的操作，这些操作需要更长的执行时间，并使应用程序的运行速度更慢。 如果对值类型使用 `Object` 变量，则会产生*装箱*和*取消装箱*。 如果将其用于引用类型，则会产生*后期绑定*。  
  
## <a name="see-also"></a>另请参阅

- [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [数值数据类型](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [字符数据类型](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [早期绑定和后期绑定](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
