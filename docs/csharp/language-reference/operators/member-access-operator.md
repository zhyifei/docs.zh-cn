---
title: . 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: a59f69d0349a054c8c2a5b701b8f63df113a6580
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333715"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="44bdb-103">.</span><span class="sxs-lookup"><span data-stu-id="44bdb-103">.</span></span> <span data-ttu-id="44bdb-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="44bdb-104">operator (C# Reference)</span></span>

<span data-ttu-id="44bdb-105">点运算符 (`.`) 用于成员访问。</span><span class="sxs-lookup"><span data-stu-id="44bdb-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="44bdb-106">点运算符指定类型或命名空间的成员。</span><span class="sxs-lookup"><span data-stu-id="44bdb-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="44bdb-107">例如，点运算符用于访问 .NET Framework 类库中的特定方法：</span><span class="sxs-lookup"><span data-stu-id="44bdb-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>

[!code-csharp[csRefOperators#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#16)]

<span data-ttu-id="44bdb-108">例如，请考虑以下类：</span><span class="sxs-lookup"><span data-stu-id="44bdb-108">For example, consider the following class:</span></span>

[!code-csharp[csRefOperators#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#17)]

[!code-csharp[csRefOperators#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#18)]

<span data-ttu-id="44bdb-109">变量 `s` 具有两个成员（`a` 和 `b`）；若要对其进行访问，请使用点运算符：</span><span class="sxs-lookup"><span data-stu-id="44bdb-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>

[!code-csharp[csRefOperators#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#19)]

<span data-ttu-id="44bdb-110">点还用于构成限定名称，即为指定它们所属的命名空间或接口等的名称。</span><span class="sxs-lookup"><span data-stu-id="44bdb-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>

[!code-csharp[csRefOperators#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#20)]

<span data-ttu-id="44bdb-111">using 指令使某些名称限定变成可选：</span><span class="sxs-lookup"><span data-stu-id="44bdb-111">The using directive makes some name qualification optional:</span></span>

[!code-csharp[csRefOperators#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#21)]

<span data-ttu-id="44bdb-112">但如果标识符不明确，则必须对其进行限定：</span><span class="sxs-lookup"><span data-stu-id="44bdb-112">But when an identifier is ambiguous, it must be qualified:</span></span>

[!code-csharp[csRefOperators#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="44bdb-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="44bdb-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="44bdb-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="44bdb-114">See also</span></span>

- [<span data-ttu-id="44bdb-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="44bdb-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="44bdb-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="44bdb-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="44bdb-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="44bdb-117">C# Operators</span></span>](index.md)