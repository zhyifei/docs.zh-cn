---
title: '@（C# 参考）'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7dbab5a743b4f9fed759210e8410cd6e3459efac
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44135934"
---
# <a name="-c-reference"></a>@（C# 参考）

`@` 特殊字符用作原义标识符。 它具有以下用途：

1. 使 C# 关键字用作标识符。 `@` 字符可作为代码元素的前缀，编译器将把此代码元素解释为标识符而非 C# 关键字。 下面的示例使用 `@` 字符定义其在 `for` 循环中使用的名为 `for` 的标识符。

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. 指示将原义解释字符串。 `@` 字符在此实例中定义原义标识符。 简单转义序列（如代表反斜杠的 `"\\"`）、十六进制转义序列（如代表大写字母 A 的 `"\x0041"`）和 Unicode 转义序列（如代表大写字母 A 的 `"\u0041"`）都将按字面解释。 只有引号转义序列 (`""`) 不会按字面解释；因为它生成单引号。 此外，如果是逐字[内插字符串](interpolated.md)，大括号转义序列（`{{` 和 `}}`）不按字面解释；它们会生成单个大括号字符。 下面的示例分别使用常规字符串和原义字符串定义两个相同的文件路径。 这是原义字符串的较常见用法之一。

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   下面的示例演示定义包含相同字符序列的常规字符串和原义字符串的效果。

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. 使编译器在命名冲突的情况下区分两种属性。 属性是派生自 <xref:System.Attribute> 的类型。 其类型名称通常包含后缀 **Attribute**，但编译器不会强制进行此转换。 随后可在代码中按其完整类型名称（例如 `[InfoAttribute]`）或短名称（例如 `[Info]`）引用此属性。 但是，如果两个短名称相同，并且一个类型名称包含 **Attribute** 后缀而另一类型名称不包含，则会出现命名冲突。 例如，由于编译器无法确定将 `Info` 还是 `InfoAttribute` 属性应用于 `Example` 类，因此下面的代码无法编译。

   ```csharp
   using System;

   [AttributeUsage(AttributeTargets.Class)]
   public class Info : Attribute
   {
      private string information;
      
      public Info(string info)
      {
          information = info;
      }
   }

   [AttributeUsage(AttributeTargets.Method)]
   public class InfoAttribute : Attribute
   {
      private string information;
      
      public InfoAttribute(string info)
      {
          information = info;
      }
   }

   [Info("A simple executable.")]
   public class Example
   {
      [InfoAttribute("The entry point.")]
      public static void Main()
      {
      }
   }
   ```  

   如果使用原义标识符标识 `Info` 属性，该示例就可成功进行编译。

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]

## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 特殊字符](../../../csharp/language-reference/tokens/index.md)
