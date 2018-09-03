---
title: ++ 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: a52f614ce1bbfb8e9d9be686b277c1e69f6f9d35
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43399305"
---
# <a name="-operator-c-reference"></a>++ 运算符（C# 参考）
递增运算符 (`++`) 按 1 递增其操作数。 递增运算符可以在其操作数之前或之后出现： `++variable` 和 `variable++`。  
  
## <a name="remarks"></a>备注  
 第一个窗体是前缀递增操作。 操作的结果是操作数递增后的值。  
  
 第二个窗体是后缀递增操作。 操作的结果是操作数递增前的值。  
  
 数值和枚举类型具有预定义的递增运算符。 用户定义的类型可以重载 `++` 运算符。 对整数类型的操作通常可用于枚举。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)
