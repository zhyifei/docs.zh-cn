---
title: 其他数据类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 9261a02f3dc286dc37b3073158ccc0c151030fe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="miscellaneous-data-types-visual-basic"></a>其他数据类型 (Visual Basic)
Visual Basic 提供不是针对数字或字符的几种数据类型。 相反，它们处理专用数据如是/否值、 日期/时间值和对象地址。  
  
 显示 Visual Basic 数据类型的并排显示比较的表，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。  
  
## <a name="boolean-type"></a>布尔值类型  
 [布尔数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)是解释为无符号的值`True`或`False`。 其数据宽度取决于实现的平台。 如果变量可以包含如 true/false，只有两种状态值是/否，或打开/关闭，将其声明为`Boolean`。  
  
## <a name="date-type"></a>日期类型  
 [日期数据类型](../../../../visual-basic/language-reference/data-types/date-data-type.md)是包含日期和时间信息的 64 位值。 每个增量表示 (12:00 AM) 中的开始后所用时间的 100 纳秒的 1 公历日历中每 1 年月 1 日。 如果日期值和 / 或时间值，可以包含一个变量，将其声明为`Date`。  
  
## <a name="object-type"></a>对象类型  
 [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)是指向对象实例在你的应用程序或某个其他应用程序中的 32 位地址。 `Object`变量可以引用你的应用程序识别的任何对象或任何数据类型的数据。 同时包含这*值类型*，如`Integer`， `Boolean`，和结构实例和*引用类型*，这是实例创建的对象从类如`String`和<xref:System.Windows.Forms.Form>，以及数组实例。  
  
 如果变量存储指向你不知道在编译时，类的实例或者它可以指向各种数据类型的数据，将其声明为`Object`。  
  
 利用`Object`数据类型是，可以使用它来存储任何数据类型的数据。 其缺点在于，会产生额外的操作需要更多的执行时间，使得你的应用程序执行速度减慢。 如果你使用`Object`变量为值类型，你会产生*装箱*和*取消装箱*。 如果你使用它为引用类型，则会引发*后期绑定*。  
  
## <a name="see-also"></a>请参阅  
 [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [数值数据类型](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [字符数据类型](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [早期绑定和后期绑定](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
