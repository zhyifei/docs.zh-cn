---
title: 函数的返回类型&#39;&lt;过程名称&gt;&#39;不符合 CLS
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: b7704ee63031c38f708a2243e84b880c25fcf819
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594999"
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a>函数的返回类型&#39;&lt;过程名称&gt;&#39;不符合 CLS
A`Function`过程标记为`<CLSCompliant(True)>`但返回类型被标记为`<CLSCompliant(False)>`、 未标记，或不合格，因为它是不符合要求的类型。  
  
 一个过程要符合[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md) (CLS)，必须只使用符合 CLS 的类型。 这适用于参数的类型、返回类型及其所有本地变量的类型。  
  
 下面的 Visual Basic 数据类型不符合 cls 的：  
  
-   [SByte 数据类型](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 数据类型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 数据类型](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 数据类型](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。 此参数没有默认值，必须为其提供一个值。  
  
 如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC40027  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果`Function`过程必须返回此特定的类型，请删除<xref:System.CLSCompliantAttribute>。 该过程不符合 CLS。  
  
-   如果`Function`过程必须符合 cls 的、 返回类型更改为最接近的符合 cls 的类型。 例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。 如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。  
  
-   如果在与自动化或 COM 对象对接，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中不同的数据宽度。 例如，`int` 在其他环境中通常为 16 位。 如果您要将一个 16 位整数退回此类组件，将其声明为`Short`而不是`Integer`托管 Visual Basic 代码中。