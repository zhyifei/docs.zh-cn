---
title: 无效模式字符串
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 4905f74683989d8e1a2b041a8af4af4d7432ffab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33635640"
---
# <a name="invalid-pattern-string"></a>无效模式字符串
在搜索的 `Like` 操作中指定的模式字符串无效。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  查看列表中表达式的有效字符。  
  
2.  在模式范围内，请确保起始范围字符小于结束范围字符，如 `[a-z]`中所示。  
  
3.  在模式范围内，请确保不存在彼此相邻的多个连字符，如 `[a--z]`中所示。  
  
4.  以右括号结束模式范围。  
  
## <a name="see-also"></a>请参阅  
 [Like 运算符](../../visual-basic/language-reference/operators/like-operator.md)
