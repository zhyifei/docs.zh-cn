---
title: Out（泛型修饰符）(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: 7ba774bfcd629a7518602d4b971e86a690b2dd83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598148"
---
# <a name="out-generic-modifier-visual-basic"></a>Out（泛型修饰符）(Visual Basic)
对于泛型类型参数，`Out`关键字指定的类型是协变。  
  
## <a name="remarks"></a>备注  
 协变使你使用的类型可以比泛型参数指定的类型派生程度更大。 这样可以隐式转换实现变体接口的类以及隐式转换委托类型。  
  
 有关详细信息，请参阅[协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。  
  
## <a name="rules"></a>规则  
 可以在泛型接口和委托中使用 `Out` 关键字。  
  
 在泛型接口中，如果类型参数满足以下条件，则可以声明为协变：  
  
-   类型参数只用作接口方法的返回类型，而不用作方法参数的类型。  
  
    > [!NOTE]
    >  此规则有一个例外。 如果在协变接口中将逆变泛型委托用作方法参数，则可以将协变类型用作此委托的泛型类型参数。 有关协变和逆变泛型委托的详细信息，请参阅[委托中的变体](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)和[对 Func 和 Action 泛型委托使用变体](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)。  
  
-   类型参数不用作接口方法的泛型约束。  
  
 在泛型委托中，类型参数可以声明协变如果它是仅用作方法的返回类型，不用于方法参数。  
  
 引用类型支持协变和逆变，但值类型不支持它们。  
  
 在 Visual Basic 中，不能声明协变的接口中的事件，而不指定委托类型。 此外，协变的接口不能有嵌套类、 枚举或结构，但它们可以有嵌套接口。  
  
## <a name="behavior"></a>行为  
 具有协变类型参数的接口使其方法返回的类型可以比类型参数指定的类型派生程度更大。 例如，因为在 .NET Framework 4 的 <xref:System.Collections.Generic.IEnumerable%601> 中，类型 T 是协变的，所以可以将 `IEnumerabe(Of String)` 类型的对象分配给 `IEnumerable(Of Object)` 类型的对象，而无需使用任何特殊转换方法。  
  
 可以向协变委托分配相同类型的其他委托，不过要使用派生程度更大的泛型类型参数。  
  
## <a name="example"></a>示例  
 下面的示例演示如何声明、扩展和实现协变泛型接口。 它还演示如何对实现协变接口的类使用隐式转换。  
  
 [!code-vb[vbVarianceKeywords#3](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_1.vb)]  
  
## <a name="example"></a>示例  
 以下示例演示如何声明、实例化和调用协变泛型委托。 它还显示如何使用隐式转换为委托类型。  
  
 [!code-vb[vbVarianceKeywords#4](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [泛型接口中的变体](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
