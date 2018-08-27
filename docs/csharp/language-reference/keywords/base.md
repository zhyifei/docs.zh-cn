---
title: base 关键字（C# 参考）
description: 了解 base 关键字，使用它从 C# 中的派生类中访问基类的成员。
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: 8719ab79273701173530760ad1bec837c4f4302d
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934348"
---
# <a name="base-c-reference"></a><span data-ttu-id="bc89b-103">base（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="bc89b-103">base (C# Reference)</span></span>

<span data-ttu-id="bc89b-104">`base` 关键字用于从派生类中访问基类的成员：</span><span class="sxs-lookup"><span data-stu-id="bc89b-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="bc89b-105">调用基类上已被其他方法重写的方法。</span><span class="sxs-lookup"><span data-stu-id="bc89b-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="bc89b-106">指定创建派生类实例时应调用的基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="bc89b-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="bc89b-107">仅允许基类访问在构造函数、实例方法或实例属性访问器中进行。</span><span class="sxs-lookup"><span data-stu-id="bc89b-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="bc89b-108">从静态方法中使用 `base` 关键字是错误的。</span><span class="sxs-lookup"><span data-stu-id="bc89b-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="bc89b-109">所访问的基类是类声明中指定的基类。</span><span class="sxs-lookup"><span data-stu-id="bc89b-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="bc89b-110">例如，如果指定 `class ClassB : ClassA`，则从 ClassB 访问 ClassA 的成员，而不考虑 ClassA 的基类。</span><span class="sxs-lookup"><span data-stu-id="bc89b-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="bc89b-111">示例</span><span class="sxs-lookup"><span data-stu-id="bc89b-111">Example</span></span>

<span data-ttu-id="bc89b-112">在本例中，基类 `Person` 和派生类 `Employee` 都有一个名为 `Getinfo` 的方法。</span><span class="sxs-lookup"><span data-stu-id="bc89b-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="bc89b-113">通过使用 `base` 关键字，可以从派生类中调用基类的 `Getinfo` 方法。</span><span class="sxs-lookup"><span data-stu-id="bc89b-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

<span data-ttu-id="bc89b-114">有关其他示例，请参阅 [new](../../../csharp/language-reference/keywords/new.md)、[virtual](../../../csharp/language-reference/keywords/virtual.md) 和 [override](../../../csharp/language-reference/keywords/override.md)。</span><span class="sxs-lookup"><span data-stu-id="bc89b-114">For additional examples, see [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md), and [override](../../../csharp/language-reference/keywords/override.md).</span></span>

## <a name="example"></a><span data-ttu-id="bc89b-115">示例</span><span class="sxs-lookup"><span data-stu-id="bc89b-115">Example</span></span>

<span data-ttu-id="bc89b-116">本示例显示如何指定在创建派生类实例时调用的基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="bc89b-116">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="bc89b-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="bc89b-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bc89b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc89b-118">See also</span></span>

- [<span data-ttu-id="bc89b-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="bc89b-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="bc89b-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="bc89b-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bc89b-121">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="bc89b-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="bc89b-122">this</span><span class="sxs-lookup"><span data-stu-id="bc89b-122">this</span></span>](../../../csharp/language-reference/keywords/this.md)