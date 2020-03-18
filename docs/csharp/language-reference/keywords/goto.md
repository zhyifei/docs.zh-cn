---
title: goto 语句 - C# 参考
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 076f793e880a7b4d1e8872d80e88c44cdf077541
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715275"
---
# <a name="goto-c-reference"></a>goto（C# 参考）

`goto` 语句将程序控制直接传递给标记语句。

`goto` 的一个通常用法是将控制传递给特定的 switch-case 标签或 `switch` 语句中的默认标签。

`goto` 语句还用于跳出深嵌套循环。

## <a name="example"></a>示例

下面的示例演示了 `goto` 在 [switch](switch.md) 语句中的使用。

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a>示例

下面的示例演示了使用 `goto` 跳出嵌套循环。

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>另请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
- [goto 语句 (C++)](/cpp/cpp/goto-statement-cpp)
