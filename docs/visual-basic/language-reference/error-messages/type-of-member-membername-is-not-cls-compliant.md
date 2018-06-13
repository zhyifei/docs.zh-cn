---
title: 成员类型&#39; &lt;membername&gt; &#39;不符合 CLS
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 5735b5104884a702a649a029116be7446424ec67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595963"
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a>成员类型&#39; &lt;membername&gt; &#39;不符合 CLS
为此成员不是指定的数据类型的一部分[语言独立性和独立于语言的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)。 这不是在您的组件，一个错误，因为[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]和 Visual Basic 支持此数据类型。 但是，在严格符合 cls 的代码中编写的另一个组件可能不支持此数据类型。 此类组件可能不能成功与你的组件进行交互。  
  
 下面的 Visual Basic 数据类型不符合 cls 的：  
  
-   [SByte 数据类型](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 数据类型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 数据类型](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 数据类型](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC40025  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果你的组件只与其他接口[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]组件，或者不与任何其他组件之间的接口，您不需要更改任何内容。  
  
-   如果你没有为编写的组件与交互[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]，你可能能够确定通过反射或从文档，它是否支持此数据类型。 如果是这样，你不需要更改任何内容。  
  
-   如果你与不支持此数据类型的组件交互，你必须将其替换最接近的符合 cls 的类型。 例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。 如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。  
  
-   如果在与自动化或 COM 对象对接，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中不同的数据宽度。 例如，`uint` 在其他环境中通常为 16 位。 如果你的 16 位自变量传递给此类组件，将其声明为`UShort`而不是`UInteger`托管 Visual Basic 代码中。  
  
## <a name="see-also"></a>请参阅  
 [反射](../../../framework/reflection-and-codedom/reflection.md)  
 
