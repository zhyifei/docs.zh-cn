---
title: 序号无效
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 28f78161e14604c1f59872801855ccc918faec58
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299249"
---
# <a name="ordinal-is-not-valid"></a>序号无效
对动态链接库 (DLL) 的调用指示应使用数字而不是过程名称，是使用`#num`语法。 此错误具有以下可能的原因：  
  
-   尝试将转换`#num`为序号失败的表达式。  
  
-   `#num`指定 DLL 中未指定任何函数。  
  
-   类型库中有一个无效的声明，从而导致无效的序号的内部使用。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 请确保表达式表示的有效数字，或按名称调用该过程。  
  
2. 请确保`#num`标识 DLL 中有效的函数。  
  
3. 隔离导致问题的代码添加注释的过程调用。 编写`Declare`语句过程中，并将问题报告给类型库供应商联系。  
  
## <a name="see-also"></a>请参阅

- [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)
