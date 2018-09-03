---
title: = 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 9cd1af400a9afdb7942a49dee7e7f7bb78387f2d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43477927"
---
# <a name="-operator-c-reference"></a>= 运算符（C# 参考）
赋值运算符 (`=`) 在由左操作数表示的存储位置、属性或索引器中存储右操作数的值，并将该值作为结果返回。 操作数类型必须相同（或右操作数必须可隐式转换为左操作数的类型）。  
  
## <a name="remarks"></a>备注  
 赋值运算符无法重载。 但是，可定义类型的隐式转换运算符，这样可将赋值运算符用于这些类型。 有关详细信息，请参阅[使用转换运算符](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 运算符](../../../csharp/language-reference/operators/index.md)
