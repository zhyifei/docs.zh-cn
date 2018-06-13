---
title: 错误的 DLL 调用约定
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: d8c7f7aea46162215115689305f4010cb513b020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583833"
---
# <a name="bad-dll-calling-convention"></a>错误的 DLL 调用约定
自变量传递给动态链接库 (DLL) 必须完全匹配所需要的例程。 调用约定处理数量、 类型和参数的顺序。 程序可能在错误的类型或数量的参数被传递的 DLL 中调用例程。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保所有自变量类型与要调用的例程声明中指定一致。  
  
2.  请确保您要传递要调用的例程的声明中指定的参数的相同数目。  
  
3.  如果 DLL 例程需要按值的自变量，请确保`ByVal`例程的声明中为这些参数指定。  
  
## <a name="see-also"></a>请参阅  
 [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Call 语句](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)
