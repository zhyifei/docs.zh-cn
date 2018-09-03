---
title: == 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: d9d7dcf3b38939e681fb51d6c674151cee78b3d0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43421107"
---
# <a name="-operator-c-reference"></a>== 运算符（C# 参考）
对于预定义的值类型，如果其操作数的值相等，则相等运算符 (`==`) 返回 true，否则返回 `false`。 对于 [string](../../../csharp/language-reference/keywords/string.md) 外的引用类型，如果两个操作数引用同一对象，则 `==` 会返回 `true`。 对于 `string` 类型，`==` 会比较字符串的值。  
  
## <a name="remarks"></a>备注  
 用户定义的值类型可以重载 `==` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。 用户定义的引用类型情况也相似，但是默认情况下，`==` 的行为如上述预定义和用户定义的引用类型所述。 如果已重载 `==`，则必须同时重载 [!=](../../../csharp/language-reference/operators/not-equal-operator.md)。 对整数类型的操作通常可用于枚举。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)
