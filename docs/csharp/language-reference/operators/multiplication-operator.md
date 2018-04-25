---
title: '* 运算符（C# 参考）'
ms.date: 04/04/2018
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
ms.openlocfilehash: 07d06d668ba43ebc3f4fae394d7b6641b122f4a6
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a>* 运算符（C# 参考）
乘法运算符 (`*`) 计算操作数的乘积。 所有数值类型都具有预定义的乘法运算符。  

`*` 还用作取消引用运算符，用于对指针执行读取和写入操作。
  
## <a name="remarks"></a>备注  
 `*` 运算符还用于声明指针类型和取消引用指针。 此运算符仅可用于不安全的上下文，通过使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 关键字表示，且需要 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项。  取消引用运算符也称为间接寻址运算符。  
  
 用户定义的类型可以重载二元 `*` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
