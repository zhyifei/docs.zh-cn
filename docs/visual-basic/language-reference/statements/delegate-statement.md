---
title: Delegate 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
ms.openlocfilehash: 662d2c3c0767adfe406e0a6f1b1e6dccd704e795
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354077"
---
# <a name="delegate-statement"></a>Delegate 语句
用于声明委托。 委托是一种引用类型，引用类型的 `Shared` 方法或对象的实例方法。 任何具有匹配参数和返回类型的过程都可以用于创建此委托类的实例。 稍后可以通过委托实例调用该过程。  
  
## <a name="syntax"></a>语法  
  
```vb  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`attrlist`|可选。 应用于此委托的特性的列表。 用逗号分隔多个属性。 必须将[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)用尖括号括起来（"`<`" 和 "`>`"）。|  
|`accessmodifier`|可选。 指定哪些代码可以访问委托。 可以是以下各项之一：<br /><br /> - [公共](../../../visual-basic/language-reference/modifiers/public.md)。 可以访问声明委托的元素的任何代码都可以访问它。<br />-   [受保护](../../../visual-basic/language-reference/modifiers/protected.md)。 只有委托的类或派生类中的代码可以访问它。<br />-   [朋友](../../../visual-basic/language-reference/modifiers/friend.md)。 只有同一程序集中的代码才能访问该委托。<br />- [专用](../../../visual-basic/language-reference/modifiers/private.md)。 只有声明委托的元素中的代码才能访问它。<br /><br /> 仅 - [受保护的 Friend](../../language-reference/modifiers/protected-friend.md) ：委托的类、派生类或同一程序集内的代码可以访问该委托。 <br />仅 - 委托的类中或同一程序集中的派生类中的[私有受保护](../../language-reference/modifiers/private-protected.md)代码可以访问该委托。 |  
|`Shadows`|可选。 指示此委托重新声明并隐藏基类中具有相同名称的编程元素或重载元素集。 可以与任何其他类型一起隐藏任何类型的已声明元素。<br /><br /> 隐藏的元素不可在隐藏它的派生类中使用（除了从隐藏元素不可访问的位置）。 例如，如果 `Private` 元素隐藏了基类元素，则没有权限访问 `Private` 元素的代码将改为访问基类元素。|  
|`Sub`|可选，但必须出现 `Sub` 或 `Function`。 将此过程声明为不返回值的委托 `Sub` 过程。|  
|`Function`|可选，但必须出现 `Sub` 或 `Function`。 将此过程声明为委托 `Function` 返回值的过程。|  
|`name`|必需。 委托类型的名称;遵循标准变量命名约定。|  
|`typeparamlist`|可选。 此委托的类型参数列表。 多个类型参数之间用逗号分隔。 根据需要，可以使用 `In` 和 `Out` 泛型修饰符将每个类型参数声明为变体。 必须将[类型列表](../../../visual-basic/language-reference/statements/type-list.md)括在括号内，并将其与 `Of` 关键字一起引入。|  
|`parameterlist`|可选。 调用时传递给过程的参数的列表。 必须将[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)括在括号中。|  
|`type`|如果指定 `Function` 过程，则为必需。 返回值的数据类型。|  
  
## <a name="remarks"></a>备注  
 `Delegate` 语句定义委托类的参数和返回类型。 任何具有匹配参数和返回类型的过程都可以用于创建此委托类的实例。 然后，可以通过调用委托的 `Invoke` 方法，稍后通过委托实例调用该过程。  
  
 委托可以在命名空间、模块、类或结构级别进行声明，但不能在过程中声明。  
  
 每个委托类均可定义将对象方法指定传递到的构造函数。 委托构造函数的自变量必须是对方法的引用或 lambda 表达式。  
  
 若要指定对方法的引用，请使用以下语法：  
  
 `AddressOf` [`expression`.]`methodname`  
  
 `expression` 的编译时类型必须是类或接口的名称，此类或接口包含指定名称的方法，其签名与委托类的签名一致。 `methodname` 可以是共享方法，也可以是实例方法。 即使为类的默认方法创建委托，`methodname` 也不是可选的。  
  
 若要指定 lambda 表达式，请使用以下语法：  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 函数的签名必须与委托类型的签名一致。 有关 lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
 有关委托的详细信息，请参阅[委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `Delegate` 语句声明一个用于对两个数字进行操作并返回一个数字的委托。 `DelegateTest` 方法获取此类型的委托的一个实例，并使用该实例对一对数字进行操作。  
  
 [!code-vb[VbVbalrDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>另请参阅

- [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [如何：使用泛型类](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
