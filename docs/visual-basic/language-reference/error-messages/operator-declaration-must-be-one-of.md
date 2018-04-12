---
title: '运算符声明必须是: +、-，*，-，-，^， &amp;，Like、 Mod，和，或 Xor，不是， &lt; &lt;， &gt; &gt;，=， &lt; &gt;， &lt;， &lt;=、 &gt;&gt;= CType，为 true 时，IsFalse'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a>运算符声明必须是: +、-，*，\,/，^， &amp;，Like、 Mod，和，或 Xor，不是， &lt; &lt;， &gt; &gt;...
您可以声明仅有资格享受重载的运算符。 下表列出可以声明的运算符。  
  
|类型|运算符|  
|----------|---------------|  
|一元|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|二进制|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|转换（一元）|`CType`|  
  
 请注意，`=`二元列表中的运算符是比较运算符，而不是赋值运算符。  
  
 **错误 ID:** BC33000  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  从一组可重载运算符中选择一个运算符。  
  
2.  如果你需要重载无法直接重载的运算符这一功能，请创建用于获取适当参数并返回适当值的 `Function` 过程。  
  
## <a name="see-also"></a>另请参阅  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [如何：定义转换运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
