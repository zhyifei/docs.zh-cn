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
ms.openlocfilehash: be8ddb7f9ba08535d12890d1c5c82a9b7b485f3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597355"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
指定过程参数是一个指定类型的元素的可选数组。 `ParamArray` 可以仅在参数列表的最后一个参数上使用。  
  
## <a name="remarks"></a>备注  
 `ParamArray` 可以将任意数量的参数传递给过程。 A`ParamArray`始终使用声明参数[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)。  
  
 你可以提供一个或多个自变量`ParamArray`参数传递的适当的数据的数组类型，则以逗号分隔列表的值，或执行任何操作根本。 有关详细信息，请参阅"调用 ParamArray"[参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)。  
  
> [!IMPORTANT]
>  每当你处理数组可以是无限期地大型，没有无限大某种内部容量的你的应用程序的风险。 如果你接受从调用代码的参数数组，应测试它的长度，并采取适当的措施，如果你的应用程序太大。  
  
 `ParamArray` 修饰符可用于下面的上下文中：  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>请参阅  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)  
 [参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
