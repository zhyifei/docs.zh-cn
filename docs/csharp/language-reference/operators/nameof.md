---
title: nameof 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: fa858db918cdaf04c757f2741265e359acb74f7b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036355"
---
# <a name="nameof-operator-c-reference"></a><span data-ttu-id="625a8-102">nameof 运算符 -（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="625a8-102">nameof operator (C# reference)</span></span>

<span data-ttu-id="625a8-103">`nameof` 运算符获取变量、类型或成员的名称作为字符串常量：</span><span class="sxs-lookup"><span data-stu-id="625a8-103">The `nameof` operator obtains the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

<span data-ttu-id="625a8-104">如前面的示例所示，对于类型和命名空间，生成的名称通常不是[完全限定的](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)名称。</span><span class="sxs-lookup"><span data-stu-id="625a8-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="625a8-105">`nameof` 运算符在编译时进行求值，在运行时无效。</span><span class="sxs-lookup"><span data-stu-id="625a8-105">The `nameof` operator is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="625a8-106">可以使用 `nameof` 运算符使参数检查代码更易于维护：</span><span class="sxs-lookup"><span data-stu-id="625a8-106">You can use the `nameof` operator to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="625a8-107">`nameof` 运算符在 C# 6 及更高版本中提供。</span><span class="sxs-lookup"><span data-stu-id="625a8-107">The `nameof` operator is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="625a8-108">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="625a8-108">C# language specification</span></span>

<span data-ttu-id="625a8-109">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [Nameof 表达式](~/_csharplang/spec/expressions.md#nameof-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="625a8-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="625a8-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="625a8-110">See also</span></span>

- [<span data-ttu-id="625a8-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="625a8-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="625a8-112">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="625a8-112">C# operators</span></span>](index.md)
