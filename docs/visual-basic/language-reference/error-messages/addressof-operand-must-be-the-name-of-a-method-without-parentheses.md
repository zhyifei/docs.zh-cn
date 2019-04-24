---
title: “AddressOf”操作数必须是方法名（不带括号）
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323819"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a>“AddressOf”操作数必须是方法名（不带括号）
`AddressOf` 运算符创建引用特定过程的过程委托实例。 语法如下所示。  
  
 `AddressOf` `procedurename`  
  
 插入参数后面的两边的括号`AddressOf`，当不需要。  
  
 **错误 ID:** BC30577  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 删除后面的参数两边的括号`AddressOf`。  
  
2. 请确保参数是方法名称。  
  
## <a name="see-also"></a>请参阅

- [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)
