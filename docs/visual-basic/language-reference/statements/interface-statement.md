---
title: Interface 语句
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: b606f24cf3baa13746834dfbf7ca6b9215fd3558
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348059"
---
# <a name="interface-statement-visual-basic"></a>Interface 语句 (Visual Basic)
声明接口的名称，并引入该接口所包含的成员的定义。  
  
## <a name="syntax"></a>语法  
  
```vb  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`attributelist`|可选。 请参阅[特性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。|  
|`accessmodifier`|可选。 可以是以下各项之一：<br /><br /> -   [公有](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [保护](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [朋友](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [私有](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [受保护的朋友](../../language-reference/modifiers/protected-friend.md)<br/>- [私有保护](../../language-reference/modifiers/private-protected.md)<br /><br /> 请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。|  
|`Shadows`|可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。|  
|`name`|必需。 此接口的名称。 请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|  
|`Of`|可选。 指定这是一个泛型接口。|  
|`typelist`|如果使用 of 关键字，则[为](../../../visual-basic/language-reference/statements/of-clause.md)必需。 此接口的类型参数列表。 根据需要，可以使用 `In` 和 `Out` 泛型修饰符将每个类型参数声明为变体。 请参阅[类型列表](../../../visual-basic/language-reference/statements/type-list.md)。|  
|`Inherits`|可选。 指示此接口继承另一个接口的特性和成员。 请参阅[Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)。|  
|`interfacenames`|如果使用 `Inherits` 语句，则是必需的。 此接口派生自的接口的名称。|  
|`modifiers`|可选。 要定义的接口成员的适当修饰符。|  
|`Property`|可选。 定义一个属性，该属性是接口的成员。|  
|`Function`|可选。 定义一个 `Function` 过程，该过程是接口的成员。|  
|`Sub`|可选。 定义一个 `Sub` 过程，该过程是接口的成员。|  
|`Event`|可选。 定义是接口成员的事件。|  
|`Interface`|可选。 定义一个嵌套在此接口内的接口。 嵌套接口定义必须使用 `End Interface` 语句终止。|  
|`Class`|可选。 定义一个类，该类是接口的成员。 成员类定义必须使用 `End Class` 语句终止。|  
|`Structure`|可选。 定义一个结构，该结构是接口的成员。 成员结构定义必须以 `End Structure` 语句终止。|  
|`membername`|对于定义为接口成员的每个属性、过程、事件、接口、类或结构都是必需的。 成员名。|  
|`End Interface`|终止 `Interface` 定义。|  
  
## <a name="remarks"></a>备注  
 *接口*定义类和结构可以实现的一组成员（如属性和过程）。 接口仅定义成员的签名，而不定义其内部工作原理。  
  
 类或结构通过为接口所定义的每个成员提供代码来实现接口。 最后，当应用程序从该类或结构创建实例时，对象存在并在内存中运行。 有关详细信息，请参阅[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)和[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。  
  
 只能在命名空间或模块级别使用 `Interface`。 这意味着接口的*声明上下文*必须是源文件、命名空间、类、结构、模块或接口，不能是过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 接口默认为[Friend](../../../visual-basic/language-reference/modifiers/friend.md)访问。 您可以使用访问修饰符调整其访问级别。 有关详细信息，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="rules"></a>规则  
  
- **嵌套接口。** 可以在一个接口中定义另一个接口。 外部接口称为*包含接口*，而内部接口称为*嵌套接口*。  
  
- **成员声明。** 将属性或过程声明为某个接口的成员时，只会定义该属性或过程的*签名*。 这包括元素类型（属性或过程）、其参数和参数类型以及其返回类型。 因此，成员定义只使用一行代码，而终止语句，如 `End Function` 或 `End Property` 在接口中无效。  
  
     与此相反，当您定义枚举或结构或者嵌套类或接口时，必须包含其数据成员。  
  
- **成员修饰符。** 定义模块成员时，不能使用任何访问修饰符，也不能指定除[重载](../../../visual-basic/language-reference/modifiers/overloads.md)以外的[共享](../../../visual-basic/language-reference/modifiers/shared.md)或任何过程修饰符。 您可以使用[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)声明任何成员，并且在定义属性时可以使用[默认值](../../../visual-basic/language-reference/modifiers/default.md)，也可以使用[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)或[WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)。  
  
- **继承。** 如果接口使用[Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)，则可以指定一个或多个基接口。 即使两个接口都定义了具有相同名称的成员，也可以从两个接口继承。 如果这样做，则实现代码必须使用名称限定来指定要实现的成员。  
  
     接口不能从具有限制性更强的访问级别的其他接口继承。 例如，`Public` 接口无法从 `Friend` 接口继承。  
  
     接口不能从嵌套在它内的接口继承。  
  
- **部署.** 当类使用[Implements](../../../visual-basic/language-reference/statements/implements-clause.md)语句实现此接口时，它必须实现在接口中定义的每个成员。 而且，实现代码中的每个签名必须与此接口中定义的相应签名完全匹配。 但是，实现代码中成员的名称不必与接口中定义的成员名称匹配。  
  
     当类实现过程时，它无法将过程指定为 `Shared`。  
  
- **默认属性。** 接口最多可以将一个属性指定为其*默认属性*，可以在不使用属性名称的情况下引用它。 您可以通过使用[默认](../../../visual-basic/language-reference/modifiers/default.md)修饰符声明来指定此类属性。  
  
     请注意，这意味着接口仅在继承 "无" 时才可以定义默认属性。  
  
## <a name="behavior"></a>行为  
  
- **访问级别。** 所有接口成员隐式具有[公共](../../../visual-basic/language-reference/modifiers/public.md)访问权限。 定义成员时，不能使用任何访问修饰符。 但是，实现接口的类可以为每个已实现的成员声明一个访问级别。  
  
     如果向变量分配类实例，则其成员的访问级别可依赖于该变量的数据类型是基础接口还是实现类。 下面的示例阐释了这一点。  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     如果通过 `varAsInterface`访问类成员，它们都具有公共访问权限。 但是，如果通过 `varAsClass`访问成员，则 `Sub` 过程 `doSomething` 具有私有访问权限。  
  
- **内.** 接口在其命名空间、类、结构或模块中的作用域内。  
  
     每个接口成员的作用域都是整个接口。  
  
- **生存期.** 接口本身没有生存期，也没有其成员。 如果类实现接口，并将对象创建为该类的实例，则对象在运行它的应用程序中具有生存期。 有关详细信息，请参阅[类语句](../../../visual-basic/language-reference/statements/class-statement.md)中的 "生存期"。  
  
## <a name="example"></a>示例  
 下面的示例使用 `Interface` 语句来定义名为 `thisInterface`的接口，该接口必须通过 `Property` 语句和 `Function` 语句来实现。  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 请注意，`Property` 和 `Function` 语句不会引入以 `End Property` 结尾的块，并在接口内 `End Function`。 接口仅定义其成员的签名。 完全 `Property` 和 `Function` 块显示在实现 `thisInterface`的类中。  
  
## <a name="see-also"></a>另请参阅

- [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)
- [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)
- [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [泛型接口中的变体](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
