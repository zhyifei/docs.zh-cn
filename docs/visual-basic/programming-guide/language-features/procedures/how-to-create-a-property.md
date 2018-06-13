---
title: 如何：创建属性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: 6e3faed9880b6417f17ab8fe84bc5162e803c437
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656238"
---
# <a name="how-to-create-a-property-visual-basic"></a>如何：创建属性 (Visual Basic)
括起属性定义之间`Property`语句和`End Property`语句。 在此定义您定义`Get`过程中，`Set`过程中，和/或文件名。 该属性的所有代码均位于这些过程内。  
  
 `Get`过程将检索该属性的值与`Set`过程存储一个值。 如果你想要具有读/写访问的属性，则必须定义这两个过程。 对于只读属性，只需定义`Get`，并为只写属性，只需定义`Set`。  
  
### <a name="to-create-a-property"></a>创建一个属性  
  
1.  在任何属性或过程，之外使用[属性语句](../../../../visual-basic/language-reference/statements/property-statement.md)后, 跟`End Property`语句。  
  
2.  如果该属性接受参数，请按照`Property`关键字的过程中，然后在括号中的参数列表的名称。  
  
3.  括号后跟`As`子句来指定属性的值的数据类型。 必须指定即使对于只写属性的数据类型。  
  
4.  添加`Get`和`Set`于相应过程。 请参阅下面的说明。  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>若要创建 Get 过程，将检索属性值  
  
1.  之间`Property`和`End Property`语句，编写[Get 语句](../../../../visual-basic/language-reference/statements/get-statement.md)后, 跟`End Get`语句。 不需要定义的任意参数`Get`过程。  
  
2.  若要检索的属性的值之间的代码语句放`Get`和`End Get`语句。 此代码还可以包括其他计算和数据操作，除了生成并返回该属性的值。  
  
3.  使用`Return`语句返回属性的值返回到调用代码。  
  
 你必须编写`Get`过程对于读写属性和只读属性。 你无需定义`Get`只写属性的过程。  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>若要创建一个组的过程，它将写入属性的值  
  
1.  之间`Property`和`End Property`语句，编写[Set 语句](../../../../visual-basic/language-reference/statements/set-statement.md)后, 跟`End Set`语句。  
  
2.  在`Set`语句，请按照`Set`使用参数列表在括号中的关键字。 此参数列表必须包含调用代码传递的值至少值参数。 此值参数的默认名称是`Value`，但是如果需要，可以使用其他名称。 值参数必须具有相同的数据类型与属性本身。  
  
3.  将代码语句之间的属性中存储值放`Set`和`End Set`语句。 此代码还可以包括其他计算和除了验证并将该属性的值存储的数据操作。  
  
4.  使用 value 参数以接受调用的代码提供的值。 可以直接在赋值语句中，存储此值，也可以在表达式中使用计算要存储的内部值。  
  
 你必须编写`Set`过程对于读写属性和只写属性。 你无需定义`Set`只读属性的过程。  
  
## <a name="example"></a>示例  
 下面的示例创建一个读/写属性，将为完整的名称存储为两个构成的名称、 名字和姓氏。 当调用的代码读取`fullName`、`Get`过程合并两个构成的名称，并返回的完整名称。 当调用的代码将分配新的完整名称，`Set`过程尝试将其分解为两个构成的名称。 如果找不到空间，它可以将其存储所有项作为第一个名称。  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 下面的示例演示对属性过程的典型调用`fullName`。 第一次调用设置的属性值和第二个调用检索到它。  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [属性过程](./property-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md)  
 [如何：声明具有混合访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [如何：调用 Property 过程](./how-to-call-a-property-procedure.md)  
 [如何： 声明和 Visual Basic 中调用默认属性](./how-to-declare-and-call-a-default-property.md)  
 [如何：在属性中放置值](./how-to-put-a-value-in-a-property.md)  
 [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)
