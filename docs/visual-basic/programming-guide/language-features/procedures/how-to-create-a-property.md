---
title: 如何：创建属性
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: ee5a9f687765ce064eb3c3f84218ed36eb916d9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349704"
---
# <a name="how-to-create-a-property-visual-basic"></a>如何：创建属性 (Visual Basic)
将属性定义括在 `Property` 语句和 `End Property` 语句之间。 在此定义中，可以定义 `Get` 过程、`Set` 过程或同时定义这两者。 所有属性的代码都位于这些过程中。  
  
 `Get` 过程检索属性的值，`Set` 过程存储值。 如果希望属性具有读/写访问权限，则必须定义这两个过程。 对于只读属性，仅定义 `Get`，对于只写属性，只定义 `Set`。  
  
### <a name="to-create-a-property"></a>创建属性  
  
1. 在任何属性或过程外部，使用[Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md)，后跟 `End Property` 语句。  
  
2. 如果属性采用参数，请在 `Property` 关键字后跟过程的名称，然后将参数列表括在括号中。  
  
3. 在括号后跟一个 `As` 子句，以指定属性值的数据类型。 即使对于只写属性，也必须指定数据类型。  
  
4. 根据需要添加 `Get` 和 `Set` 过程。 请参阅以下说明。  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>创建检索属性值的 Get 过程  
  
1. 在 `Property` 和 `End Property` 语句之间，编写[Get 语句](../../../../visual-basic/language-reference/statements/get-statement.md)，后跟 `End Get` 语句。 不需要为 `Get` 过程定义任何参数。  
  
2. 将代码语句置于 `Get` 和 `End Get` 语句之间检索属性的值。 除了生成并返回属性的值外，此代码还可以包含其他计算和数据操作。  
  
3. 使用 `Return` 语句将属性的值返回给调用代码。  
  
 必须为读写属性以及只读属性编写 `Get` 过程。 不得为只写属性定义 `Get` 过程。  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>创建写入属性值的 Set 过程  
  
1. 在 `Property` 和 `End Property` 语句之间，编写一个[Set 语句](../../../../visual-basic/language-reference/statements/set-statement.md)，后跟一个 `End Set` 语句。  
  
2. 在 `Set` 语句中，在括号中的参数列表后面跟 `Set` 关键字。 此参数列表必须至少包含调用代码传递的值的值参数。 此值参数的默认名称为 `Value`，但你可以根据需要使用不同的名称。 Value 参数的数据类型必须与属性本身的数据类型相同。  
  
3. 放置代码语句以在 `Set` 和 `End Set` 语句之间的属性中存储值。 除了验证和存储属性值外，此代码还可以包含其他计算和数据操作。  
  
4. 使用 value 参数接受调用代码提供的值。 您可以直接在赋值语句中存储此值，也可以在表达式中使用该值来计算要存储的内部值。  
  
 必须为读写属性和只写属性编写 `Set` 过程。 不得为只读属性定义 `Set` 过程。  
  
## <a name="example"></a>示例  
 下面的示例创建一个读/写属性，该属性将全名存储为两个构成名称，即名字和姓氏。 当调用代码读取 `fullName`时，`Get` 过程合并两个构成名称并返回全名。 当调用代码分配新的全名时，`Set` 过程会尝试将其分成两个构成名称。 如果找不到空间，则会将其存储为名字。  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 下面的示例演示对 `fullName`的属性过程的典型调用。 第一次调用设置属性值，第二次调用将检索它。  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>另请参阅

- [过程](./index.md)
- [属性过程](./property-procedures.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [Visual Basic 中的属性和变量之间的差异](./differences-between-properties-and-variables.md)
- [如何：声明具有混合访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md)
- [如何：调用 Property 过程](./how-to-call-a-property-procedure.md)
- [如何：在 Visual Basic 中声明和调用默认属性](./how-to-declare-and-call-a-default-property.md)
- [如何：在属性中放置值](./how-to-put-a-value-in-a-property.md)
- [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)
