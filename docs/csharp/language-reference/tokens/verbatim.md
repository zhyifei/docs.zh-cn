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
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43562226"
---
# <a name="-c-reference"></a><span data-ttu-id="170f1-102">@（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="170f1-102">@ (C# Reference)</span></span>

<span data-ttu-id="170f1-103">`@` 特殊字符用作原义标识符。</span><span class="sxs-lookup"><span data-stu-id="170f1-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="170f1-104">它具有以下用途：</span><span class="sxs-lookup"><span data-stu-id="170f1-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="170f1-105">使 C# 关键字用作标识符。</span><span class="sxs-lookup"><span data-stu-id="170f1-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="170f1-106">`@` 字符可作为代码元素的前缀，编译器将把此代码元素解释为标识符而非 C# 关键字。</span><span class="sxs-lookup"><span data-stu-id="170f1-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="170f1-107">下面的示例使用 `@` 字符定义其在 `for` 循环中使用的名为 `for` 的标识符。</span><span class="sxs-lookup"><span data-stu-id="170f1-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="170f1-108">指示将原义解释字符串。</span><span class="sxs-lookup"><span data-stu-id="170f1-108">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="170f1-109">`@` 字符在此实例中定义原义标识符。</span><span class="sxs-lookup"><span data-stu-id="170f1-109">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="170f1-110">简单转义序列（如代表反斜杠的 `"\\"`）、十六进制转义序列（如代表大写字母 A 的 `"\x0041"`）和 Unicode 转义序列（如代表大写字母 A 的 `"\u0041"`）都将按字面解释。</span><span class="sxs-lookup"><span data-stu-id="170f1-110">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A), and Unicode escape sequences (such as `"\u0041"` for an uppercase A) are interpreted literally.</span></span> <span data-ttu-id="170f1-111">只有引号转义序列 (`""`) 不会按字面解释；因为它生成单引号。</span><span class="sxs-lookup"><span data-stu-id="170f1-111">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="170f1-112">此外，如果是逐字[内插字符串](interpolated.md)，大括号转义序列（`{{` 和 `}}`）不按字面解释；它们会生成单个大括号字符。</span><span class="sxs-lookup"><span data-stu-id="170f1-112">Additionally, in case of a verbatim [interpolated string](interpolated.md) brace escape sequences (`{{` and `}}`) are not interpreted literally; they produce single brace characters.</span></span> <span data-ttu-id="170f1-113">下面的示例分别使用常规字符串和原义字符串定义两个相同的文件路径。</span><span class="sxs-lookup"><span data-stu-id="170f1-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="170f1-114">这是原义字符串的较常见用法之一。</span><span class="sxs-lookup"><span data-stu-id="170f1-114">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="170f1-115">下面的示例演示定义包含相同字符序列的常规字符串和原义字符串的效果。</span><span class="sxs-lookup"><span data-stu-id="170f1-115">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="170f1-116">使编译器在命名冲突的情况下区分两种属性。</span><span class="sxs-lookup"><span data-stu-id="170f1-116">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="170f1-117">属性是派生自 <xref:System.Attribute> 的类型。</span><span class="sxs-lookup"><span data-stu-id="170f1-117">An attribute is a type that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="170f1-118">其类型名称通常包含后缀 **Attribute**，但编译器不会强制进行此转换。</span><span class="sxs-lookup"><span data-stu-id="170f1-118">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="170f1-119">随后可在代码中按其完整类型名称（例如 `[InfoAttribute]`）或短名称（例如 `[Info]`）引用此属性。</span><span class="sxs-lookup"><span data-stu-id="170f1-119">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="170f1-120">但是，如果两个短名称相同，并且一个类型名称包含 **Attribute** 后缀而另一类型名称不包含，则会出现命名冲突。</span><span class="sxs-lookup"><span data-stu-id="170f1-120">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="170f1-121">例如，由于编译器无法确定将 `Info` 还是 `InfoAttribute` 属性应用于 `Example` 类，因此下面的代码无法编译。</span><span class="sxs-lookup"><span data-stu-id="170f1-121">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Example` class.</span></span>

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

   <span data-ttu-id="170f1-122">如果使用原义标识符标识 `Info` 属性，该示例就可成功进行编译。</span><span class="sxs-lookup"><span data-stu-id="170f1-122">If the verbatim identifier is used to identify the `Info` attribute, the example compiles successfully.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]

## <a name="see-also"></a><span data-ttu-id="170f1-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="170f1-123">See Also</span></span>

- [<span data-ttu-id="170f1-124">C# 参考</span><span class="sxs-lookup"><span data-stu-id="170f1-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="170f1-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="170f1-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="170f1-126">C# 特殊字符</span><span class="sxs-lookup"><span data-stu-id="170f1-126">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)
