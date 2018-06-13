---
title: 已禁用函数求值，因为前一个函数求值超时
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 6231d48f3f90d8e436dc80bf4670886c1d030387
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587643"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>已禁用函数求值，因为前一个函数求值超时
由于以前的函数求值的操作已超时，已禁用函数求值。若要重新启用函数求值，请再次单步执行或重新启动调试。  
  
 在 Visual Studio 调试器中，表达式指定一个过程调用，但另一个计算已超时。  
  
 超时的过程调用的可能原因包括无限循环或*无限循环*。 有关详细信息，请参阅[为...下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)。  
  
 一个无限循环的特殊情况是*递归*。 有关详细信息，请参阅[递归过程](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)。  
  
 **错误 ID:** BC30957  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  如果可能，请确定前一个函数求值是什么以及引起超时。否则，你可能会再次遇到此错误。  
  
2.  请再次，调试器单步执行或终止并重新启动调试。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中进行调试](/visualstudio/debugger/debugging-in-visual-studio)  
 [使用调试器浏览代码](/visualstudio/debugger/navigating-through-code-with-the-debugger)
