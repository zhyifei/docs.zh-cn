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
ms.openlocfilehash: 5afc7e4e3a03dfab1288e50e65e5076bdd438f7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="implements-statement"></a>Implements 语句
指定一个或多个接口，或必须在类中实现的接口成员或它在其中出现的结构定义。  
  
## <a name="syntax"></a>语法  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>部件  
 `interfacename`  
 必须的。 其属性、 过程和事件都由相应成员中的类或结构实现接口。  
  
 `interfacemember`  
 必须的。 正在实现的接口的成员。  
  
## <a name="remarks"></a>备注  
 接口是集合接口封装的原型表示的成员 （属性、 过程和事件）。 接口包含仅成员; 的声明类和结构实现这些成员。 有关详细信息，请参阅[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。  
  
 `Implements`语句必须紧跟`Class`或`Structure`语句。  
  
 当实现接口时，则必须实现该接口中声明的所有成员。 省略任何成员被视为可语法错误。 若要实现的单个成员，你可以指定[实现](../../../visual-basic/language-reference/statements/implements-clause.md)关键字 (即独立于`Implements`语句) 声明中的类或结构的成员时。 有关详细信息，请参阅[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。  
  
 类可以使用[私有](../../../visual-basic/language-reference/modifiers/private.md)了只能由强制转换到一个变量中实现的类的实例声明为接口类型的访问的属性和过程，但这些成员的实现。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`Implements`语句来实现接口成员。 它定义一个名为的接口`ICustomerInfo`事件、 属性和过程。 类`customerInfo`实现该接口中定义的所有成员。  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 请注意，类`customerInfo`使用`Implements`语句在单独的源的代码行以指示类实现的所有成员上`ICustomerInfo`接口。 然后，在类中的每个成员使用`Implements`关键字作为其成员声明，以指示，它可实现该接口成员的一部分。  
  
## <a name="example"></a>示例  
 下面的两个过程演示如何使用在前面的示例实现的接口。 若要测试的实现，请将这些过程添加到项目中并调用`testImplements`过程。  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
