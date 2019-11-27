---
title: Implements 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: e2e279b2c935dd082cbf832265a8ad09e6dffe9e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351154"
---
# <a name="implements-statement"></a>Implements 语句
指定一个或多个接口或接口成员，它们必须在它所出现的类或结构定义中实现。  
  
## <a name="syntax"></a>语法  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>部件  
 `interfacename`  
 必需。 一个接口，其属性、过程和事件由类或结构中的相应成员实现。  
  
 `interfacemember`  
 必需。 正在实现的接口的成员。  
  
## <a name="remarks"></a>备注  
 接口是表示接口封装的成员（属性、过程和事件）的原型的集合。 接口只包含成员的声明;类和结构实现这些成员。 有关更多信息，请参见 [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)中定义的接口的私有 C++ 特定实现。  
  
 `Implements` 语句必须紧跟在 `Class` 或 `Structure` 语句之后。  
  
 实现接口时，必须实现在接口中声明的所有成员。 省略任何成员均视为语法错误。 若要实现单个成员，请在声明类或结构中的成员时指定[Implements](../../../visual-basic/language-reference/statements/implements-clause.md)关键字（与 `Implements` 语句分开）。 有关更多信息，请参见 [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)中定义的接口的私有 C++ 特定实现。  
  
 类可以使用属性和过程的[私有](../../../visual-basic/language-reference/modifiers/private.md)实现，但只能通过将实现类的实例强制转换为声明为接口类型的变量来访问这些成员。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 `Implements` 语句来实现接口的成员。 它使用事件、属性和过程来定义名为 `ICustomerInfo` 的接口。 类 `customerInfo` 实现在接口中定义的所有成员。  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 请注意，类 `customerInfo` 对单独的源代码行使用 `Implements` 语句，以指示类实现了 `ICustomerInfo` 接口的所有成员。 然后，类中的每个成员都使用 `Implements` 关键字作为其成员声明的一部分，以指示它实现了该接口成员。  
  
## <a name="example"></a>示例  
 下面的两个过程演示如何使用在前面的示例中实现的接口。 若要测试实现，请将这些过程添加到项目中，然后调用 `testImplements` 过程。  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>另请参阅

- [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)
- [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)
- [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
