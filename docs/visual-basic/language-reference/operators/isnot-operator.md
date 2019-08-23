---
title: IsNot 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966928"
---
# <a name="isnot-operator-visual-basic"></a>IsNot 运算符 (Visual Basic)
比较两个对象引用变量。  
  
## <a name="syntax"></a>语法  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 一个 `Boolean` 值。  
  
 `object1`  
 必需。 任何`Object`变量或表达式。  
  
 `object2`  
 必需。 任何`Object`变量或表达式。  
  
## <a name="remarks"></a>备注  
 `IsNot`运算符确定两个对象引用是否引用不同的对象。 但是, 它不会执行值比较。 如果`object1`和`False` `result` `result` `True`都引用完全相同的对象实例, 则为; 如果不是, 则为; 如果不是, 则为。 `object2`  
  
 `IsNot`与`Is`运算符相反。 的`IsNot`优点是, 您可以避免使用`Not`和`Is`难以理解语法, 这会很难阅读。  
  
 您可以使用`Is`和`IsNot`运算符来测试早期绑定对象和后期绑定对象。  
  
> [!NOTE]
> 运算符不能用于比较从运算符返回的`TypeOf`表达式。 `IsNot` 相反, 必须使用`Not`和`Is`运算符。  
  
## <a name="example"></a>示例  
 下面的代码示例使用`Is`运算符`IsNot`和运算符来完成相同的比较。  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>请参阅

- [Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)
- [TypeOf 运算符](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [如何：测试两个对象是否相同](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
