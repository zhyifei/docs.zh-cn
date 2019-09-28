---
title: AddressOf 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 2ebadf5ded1a23fe46b8e16cf18ae265b5d3c255
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591658"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf 运算符 (Visual Basic)
创建引用特定过程的委托实例。  
  
## <a name="syntax"></a>语法  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>部件  
 `procedurename`  
 必需。 指定新创建的委托所引用的过程。  
  
## <a name="remarks"></a>备注  
 @No__t-0 运算符创建指向 `procedurename` 指定的 sub 或函数的委托。 如果指定的过程是实例方法，则委托同时引用实例和方法。 然后，在调用委托时，将调用指定实例的指定方法。  
  
 @No__t-0 运算符可用作委托构造函数的操作数，或可用于可由编译器确定的委托类型的上下文中。  
  
## <a name="example"></a>示例  
 此示例使用 @no__t 0 运算符来指定一个委托，用于处理按钮的 @no__t 事件。  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>示例  
 下面的示例使用 @no__t 0 运算符来指定线程的启动函数。  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>请参阅

- [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)
