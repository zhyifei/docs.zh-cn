---
title: '* 运算符（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 64c32def0935f4347f9aaccc2865b9cd33dd8a70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>* 运算符（C# 参考）
乘法运算符 (`*`)，用于计算其操作数的乘积。  此外，取消引用运算符，用于读取和写入指针。  
  
## <a name="remarks"></a>备注  
 所有数值类型都具有预定义的乘法运算符。  
  
 `*` 运算符还用于声明指针类型和取消引用指针。 此运算符仅可用于不安全的上下文，通过使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 关键字表示，且需要 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项。  取消引用运算符也称为间接寻址运算符。  
  
 用户定义的类型可以重载二元 `*` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
