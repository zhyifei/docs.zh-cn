---
title: 自变量“NPer”必须大于零
ms.date: 07/20/2015
f1_keywords:
- vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
ms.openlocfilehash: 86bbf892997ee512b6042ef400e2485edabe731d
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "53773479"
---
# <a name="argument-nper-must-be-greater-than-zero"></a>自变量“NPer”必须大于零
返回一个指定基于定期固定付款和固定利率的年金的期间数的 `Double` 的 `NPer` 函数要求一个大于零的参数。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   检查表达式中参数的拼写是否正确。 拼写错误的变量名可能会隐式创建一个初始化为零的数值变量。  
  
-   检查之前对表达式中的变量进行的操作，尤其是那些从其他过程作为参数传递给该过程的操作。  
  
## <a name="see-also"></a>请参阅  
 [按值和按引用传递自变量](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
