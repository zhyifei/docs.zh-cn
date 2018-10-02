---
title: 指针转换（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: db809fa9e086351184adcac43d67f53e9456894c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43777375"
---
# <a name="pointer-conversions-c-programming-guide"></a>指针转换（C# 编程指南）
下表显示预定义隐式指针转换。 隐式转换可能会在许多情况下出现（包括方法调用和赋值语句）。  
  
## <a name="implicit-pointer-conversions"></a>隐式指针转换  
  
|From|到|  
|----------|--------|  
|任何指针类型|void*|  
|null|任何指针类型|  
  
 显式指针转换用于使用强制转换对不包含隐式转换的转换执行操作。 下表显示了这些转换。  
  
## <a name="explicit-pointer-conversions"></a>显式指针转换  
  
|From|到|  
|----------|--------|  
|任何指针类型|其他任何指针类型|  
|sbyte、byte、short、ushort、int、uint、long 或 ulong|任何指针类型|  
|任何指针类型|sbyte、byte、short、ushort、int、uint、long 或 ulong|  
  
## <a name="example"></a>示例  
 在下面的示例中，`int` 的指针将转换为 `byte` 的指针。 请注意，指针指向变量的最低寻址字节。 如果结果连续递增，直到达到 `int` 的大小（4 字节），可显示变量的其余字节。  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [类型](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
