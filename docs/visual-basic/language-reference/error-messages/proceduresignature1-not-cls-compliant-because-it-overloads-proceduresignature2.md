---
title: <proceduresignature1> 不符合 CLS，因为它重载仅在数组参数类型的数组或数组参数类型的秩方面与它不同的 <proceduresignature2>
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 6143ebfbe7f131b0e196e531ed4282c8333be4ea
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250173"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>\<proceduresignature1 > 不符合 CLS，因为它重载 \<只是数组参数类型的数组或数组参数类型的秩不同的 proceduresignature2 >

当过程或属性重写另一个过程或属性，并且其参数列表之间的唯一区别是交错数组或数组排名的嵌套级别时，将标记为 `<CLSCompliant(True)>`。
  
 在下面的声明中，第二个和第三个声明生成此错误：
  
 `Overloads Sub ProcessArray(arrayParam() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam()() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`  
  
 第二个声明将原始的一维参数 `arrayParam` 更改为数组的数组。 第三个声明会将 `arrayParam` 更改为二维数组（秩为2）。 虽然 Visual Basic 允许重载只是这些更改之一不同，但这种重载不符合[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md)（CLS）。  
  
 当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。 此参数没有默认值，必须为其提供一个值。  
  
 如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID：** BC40035  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 如果你需要 CLS 符合性，请将你的重载定义为与其他方法不同，而不只是此帮助页上提到的更改。
- 如果要求重载只是此帮助页上提到的更改不同，请从其定义中删除 <xref:System.CLSCompliantAttribute> 或将其标记为 `<CLSCompliant(False)>`。
  
## <a name="see-also"></a>另请参阅

- [过程重载](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [Overloads](../modifiers/overloads.md)
