---
title: nameof 表达式 - C# 参考
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: d71acf0cf7d5cdcfa5310455af2120fa1f82d567
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135914"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="070a3-102">nameof 表达式（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="070a3-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="070a3-103">`nameof` 表达式可生成变量、类型或成员的名称作为字符串常量：</span><span class="sxs-lookup"><span data-stu-id="070a3-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="070a3-104">如前面的示例所示，对于类型和命名空间，生成的名称通常不是[完全限定的](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)名称。</span><span class="sxs-lookup"><span data-stu-id="070a3-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="070a3-105">在[逐字标识符](../tokens/verbatim.md)的情况下，`@` 字符不是名称的一部分，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="070a3-105">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="070a3-106">`nameof` 表达式在编译时进行求值，在运行时无效。</span><span class="sxs-lookup"><span data-stu-id="070a3-106">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="070a3-107">可以使用 `nameof` 表达式使参数检查代码更易于维护：</span><span class="sxs-lookup"><span data-stu-id="070a3-107">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="070a3-108">`nameof` 表达式在 C# 6 及更高版本中提供。</span><span class="sxs-lookup"><span data-stu-id="070a3-108">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="070a3-109">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="070a3-109">C# language specification</span></span>

<span data-ttu-id="070a3-110">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [Nameof 表达式](~/_csharplang/spec/expressions.md#nameof-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="070a3-110">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="070a3-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="070a3-111">See also</span></span>

- [<span data-ttu-id="070a3-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="070a3-112">C# reference</span></span>](../index.md)
- [<span data-ttu-id="070a3-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="070a3-113">C# operators</span></span>](index.md)
