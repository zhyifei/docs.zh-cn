---
title: "&#39;AddressOf &#39;操作数必须是 （不带括号） 方法的名称"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords: BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02c996f1c94250526982e35395288b07db619db7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>&#39;AddressOf &#39;操作数必须是 （不带括号） 方法的名称
`AddressOf` 运算符创建引用特定过程的过程委托实例。 语法如下所示。  
  
 `AddressOf` `procedurename`  
  
 插入参数后面的两边的括号`AddressOf`，不需要。  
  
 **错误 ID:** BC30577  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  删除后面的参数两边的括号`AddressOf`。  
  
2.  请确保参数是方法名称。  
  
## <a name="see-also"></a>另请参阅  
 [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)
