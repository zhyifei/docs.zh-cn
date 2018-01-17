---
title: "&lt;proceduresignature1&gt;因为它重载不符合 cls 的&lt;proceduresignature2&gt;只能由数组的数组参数类型或数组参数类型的排名，这不同于它"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords: BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d361759471a8edfa97437bd2503cfaa661fb9678
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>&lt;proceduresignature1&gt;因为它重载不符合 cls 的&lt;proceduresignature2&gt;只能由数组的数组参数类型或数组参数类型的排名，这不同于它
过程或属性被标记为`<CLSCompliant(True)>`时它将替代另一个过程或属性，而且它们的参数列表之间的唯一区别是交错数组的嵌套级别或数组的秩。  
  
 在下面的声明中，第二个和第三个声明生成此错误。  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 第二个声明更改原始的一维参数`arrayParam`到数组的数组。 第三个声明更改`arrayParam`到二维数组 （级别 2）。 虽然 Visual Basic 使重载的差异仅在于某项更改，此类重载不符合[语言独立性和独立于语言的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)。  
  
 当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。 此参数没有默认值，必须为其提供一个值。  
  
 如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC40035  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果你需要 CLS 符合性，定义你的重载来通过比仅引用此帮助页上的更改的更多方式方面彼此不同。  
  
-   如果你需要重载，不同只能通过更改引用此帮助页上，删除<xref:System.CLSCompliantAttribute>从其定义或将其标记为`<CLSCompliant(False)>`。  
  
## <a name="see-also"></a>请参阅  
   
 [过程重载](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [重载](../../../visual-basic/language-reference/modifiers/overloads.md)
