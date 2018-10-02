---
title: ~ 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 8af25217f9e7e66796192783a0b8e3415604dc90
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510106"
---
# <a name="-operator-c-reference"></a>~ 运算符（C# 参考）
`~` 运算符对其操作数执行按位求补运算，这对反转每一个位都有影响。 按位求补运算符针对 [int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md) 和 [ulong](../../../csharp/language-reference/keywords/ulong.md) 进行了预定义。  
  
> [!NOTE]
>  `~` 符号还用于声明终结器。 有关详细信息，请参阅[终结器](../../../csharp/programming-guide/classes-and-structs/destructors.md)。  
  
## <a name="remarks"></a>备注  
 用户定义的类型可以重载 `~` 运算符。 有关详细信息，请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)。 对整数类型的操作通常可用于枚举。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)  
- [终结器](../../../csharp/programming-guide/classes-and-structs/destructors.md)
