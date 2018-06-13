---
title: 类型列表 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 5fbb07154fce27feb257b431c1726446b42fbfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605285"
---
# <a name="type-list-visual-basic"></a>类型列表 (Visual Basic)
指定*类型参数*为*泛型*编程元素。 用逗号分隔多个参数。 下面是一个类型参数的语法。  
  
## <a name="syntax"></a>语法  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`genericmodifier`|可选。 可仅在泛型接口和委托。 你可以声明类型协变使用[出](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)关键字或通过使用逆变[中](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)关键字。 请参阅 [协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。|  
|`typename`|必须的。 类型参数的名称。 这是一个占位符，将替换为相应类型参数所提供的定义类型。|  
|`constraintlist`|可选。 约束可以为提供的数据类型的要求列表`typename`。 如果你有多个约束，则将它们括在大括号中 (`{ }`)，并用逗号分隔。 你必须使用引入此约束列表[作为](../../../visual-basic/language-reference/statements/as-clause.md)关键字。 你使用`As`一次，在列表的开头。|  
  
## <a name="remarks"></a>备注  
 每个泛型的编程元素必须采用至少一个类型参数。 类型参数是为特定类型的占位符 (*构造的元素*) 客户端代码在创建泛型类型的实例时指定。 你可以定义的泛型类、 结构、 接口、 过程或委托。  
  
 有关何时定义泛型类型的详细信息，请参阅[Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)。 对类型参数名称的详细信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。  
  
## <a name="rules"></a>规则  
  
-   **括号。** 如果提供类型参数列表，则必须将它括在括号内，并且你必须使用引入列表[的](../../../visual-basic/language-reference/statements/of-clause.md)关键字。 你使用`Of`一次，在列表的开头。  
  
-   **约束。** 一份*约束*的类型参数可以在任意组合中包含以下各项：  
  
    -   任意数量的接口。 提供的类型必须实现每个接口，此列表中。  
  
    -   最多一个类。 提供的类型必须从该类继承。  
  
    -   `New` 关键字。 提供的类型必须公开一个泛型类型可以访问的无参数构造函数。 这是你将通过一个或多个接口的类型参数约束的情况下很有用。 实现接口的类型不一定会公开一个构造函数，，具体取决于构造函数的访问级别，泛型类型中的代码可能不能访问它。  
  
    -   任一`Class`关键字或`Structure`关键字。 `Class`关键字约束用于需要传递给它的任何类型自变量是引用类型，例如字符串、 数组或委托，或从类创建对象的泛型类型参数。 `Structure`关键字约束的泛型类型参数要求传递给它的任何类型自变量是值类型，例如结构、 枚举或基本数据类型。 不能同时包含这两者`Class`和`Structure`在同一个`constraintlist`。  
  
     提供的类型必须满足中包括每个要求`constraintlist`。  
  
     每个类型参数约束均独立于其他类型参数的约束。  
  
## <a name="behavior"></a>行为  
  
-   **编译时替换。** 时从泛型的编程元素创建构造的类型，提供每个类型参数已定义的类型。 Visual Basic 编译器就会替换该类型提供的每个匹配项`typename`泛型元素内。  
  
-   **没有约束。** 如果不指定任何类型参数上的约束，你的代码仅限于运算和成员受[Object 数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)为该类型参数。  
  
## <a name="example"></a>示例  
 下面的示例演示一个泛型字典类，包括将新项添加到字典中的主干函数的主干定义。  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a>示例  
 因为`dictionary`是泛型类型，使用它的代码，可以创建多个对象，每个具有相同的功能，但作用于不同的数据类型。 下面的示例演示的创建的代码行`dictionary`对象`String`条目和`Integer`密钥。  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a>示例  
 下面的示例演示了由前面的示例生成等效的主干定义。  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
 [New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)  
 [在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Object 数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [如何：使用泛型类](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
