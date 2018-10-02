---
title: '&gt;&gt; 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 7a2992befcacfdc1d9bb968b611051e15702cca8
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924819"
---
# <a name="gtgt-operator-c-reference"></a>&gt;&gt; 运算符（C# 参考）
右移运算符 (`>>`) 将第一个操作数向右移动第二个操作数指定的位数。  
  
## <a name="remarks"></a>备注  
 如果第一个操作数是 [int](../../../csharp/language-reference/keywords/int.md) 或 [uint](../../../csharp/language-reference/keywords/uint.md)（32 位数），则移位计数由第二个操作数的低序五位给定（第二个操作数 & 0x1f）。  
  
 如果第一个操作数是 [long](../../../csharp/language-reference/keywords/long.md) 或 [ulong](../../../csharp/language-reference/keywords/ulong.md)（64 位数），则移位计数由第二个操作数的低序六位给定（第二个操作数 & 0x3f）。  
  
 如果第一个操作数是 [int](../../../csharp/language-reference/keywords/int.md) 或 [long](../../../csharp/language-reference/keywords/long.md)，则右移是一种算术移位（高阶空位设置为符号位）。 如果第一个操作数的类型为 [uint](../../../csharp/language-reference/keywords/uint.md) 或 [ulong](../../../csharp/language-reference/keywords/ulong.md)，则右移是一种逻辑移位（高序位补零）。  
  
 用户定义的类型可以重载 `>>` 运算符；第一个操作数的类型必须是用户定义的类型，第二个操作数的类型必须是 [int](../../../csharp/language-reference/keywords/int.md)。有关详细信息，请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)。 重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)
