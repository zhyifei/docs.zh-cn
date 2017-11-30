---
title: "无效模式字符串"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f824a5844d6d2b365358030119826266a4b42ef3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="invalid-pattern-string"></a>无效模式字符串
在搜索的 `Like` 操作中指定的模式字符串无效。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  查看列表中表达式的有效字符。  
  
2.  在模式范围内，请确保起始范围字符小于结束范围字符，如 `[a-z]`中所示。  
  
3.  在模式范围内，请确保不存在彼此相邻的多个连字符，如 `[a--z]`中所示。  
  
4.  以右括号结束模式范围。  
  
## <a name="see-also"></a>另请参阅  
 [Like 运算符](../../visual-basic/language-reference/operators/like-operator.md)
