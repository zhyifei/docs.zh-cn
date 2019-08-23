---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: 8fc5d1afd9e9723e6b3c58e100b0519ef8fdfab4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968365"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
指定过程参数采用指定类型的可选元素数组。 `ParamArray`只能在参数列表的最后一个参数上使用。  
  
## <a name="remarks"></a>备注  
 `ParamArray`允许将任意数量的参数传递给过程。 始终使用[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)声明参数。`ParamArray`  
  
 可以通过以下方式向`ParamArray`参数提供一个或多个参数: 传递适当数据类型的数组、以逗号分隔的值列表, 或根本不提供任何参数。 有关详细信息, 请参阅[参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)中的 "调用 ParamArray"。  
  
> [!IMPORTANT]
> 无论何时处理可能会无限大的阵列, 都有 overrunning 应用程序的一些内部容量的风险。 如果接受来自调用代码的参数数组, 则应测试其长度, 如果应用程序太大, 则应采取适当的措施。  
  
 `ParamArray` 修饰符可用于下面的上下文中：  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>请参阅

- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
