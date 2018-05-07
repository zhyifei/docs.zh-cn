---
title: Visual Basic 限制
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 57378c3aa18a5cc108c10e8654e55803f3cf9052
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="visual-basic-limitations"></a>Visual Basic 限制
早期版本的 Visual Basic 强制执行在代码中，如的变量名，在模块和模块大小允许的变量数的长度的边界。 在 Visual Basic.NET 中，这些限制都放宽了，为你提供更大的自由度中编写和排列你的代码。  
  
 物理限制都依赖更上运行时内存比在编译时的注意事项。 如果你使用较为审慎编程方法，并将大型应用程序中划分为多个类和模块，则遇到了内部的 Visual Basic 限制的可能性很小。  
  
 以下是在极端情况下可能会遇到一些限制：  
  
-   **名称长度。** 没有最大为每个声明的编程元素的名称的字符数。 如果元素名称进行限定，此最大值适用于整个限定字符串。 请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。  
  
-   **行长度。** 没有最多 65535 中的字符代码的源代码在物理行。 如果使用行继续符，则可以能采用逻辑源代码行。 请参阅[如何： 拆分和合并代码中的语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。  
  
-   **数组维度。** 没有可以声明数组的维度的最大数量。 这就限制了多少可用于指定数组元素的索引。 请参阅[数组在 Visual Basic 中的维度](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)。  
  
-   **字符串长度。** 没有最大可以存储在单个字符串中的 Unicode 字符数。 请参阅[字符串数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)。  
  
-   **环境字符串长度。** 没有为 32768 个字符作为命令行参数使用任何环境字符串的最大值。 这是在所有平台上的限制。  
  
## <a name="see-also"></a>请参阅  
 [程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Visual Basic 命名约定](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
