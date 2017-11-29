---
title: "类型的参数 &#39;&lt;parametername&gt;&#39; 不是符合 CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords: BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1c495a21603f1977bd0f0630104f75ab02728928
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="type-of-parameter-39ltparameternamegt39-is-not-cls-compliant"></a>类型的参数 &#39;&lt;parametername&gt;&#39; 不是符合 CLS
一个过程标记为`<CLSCompliant(True)>`但具有标记为的类型声明参数`<CLSCompliant(False)>`、 未标记，或不合格，因为它是不符合要求的类型。  
  
 一个过程要符合[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3) (CLS)，必须只使用符合 CLS 的类型。 这适用于参数的类型、返回类型及其所有本地变量的类型。  
  
 以下 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 数据类型不符合 CLS：  
  
-   [SByte 数据类型](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 数据类型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong 数据类型](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort 数据类型](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。 此参数没有默认值，必须为其提供一个值。  
  
 如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC40028  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果该过程必须采用这种特定类型的参数，请删除<xref:System.CLSCompliantAttribute>。 该过程不符合 CLS。  
  
-   如果该过程必须符合 CLS，更改此参数的类型为最接近的符合 cls 的类型。 例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。 如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。  
  
-   如果在与自动化或 COM 对象对接，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中不同的数据宽度。 例如，`int` 在其他环境中通常为 16 位。 如果接受此类组件中的一个 16 位整数，则在托管的 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 代码中将其声明为 `Short` 而不是 `Integer`。  
  
## <a name="see-also"></a>另请参阅  
 [\<PAVE 通过 > 编写符合 Cls 的代码](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
