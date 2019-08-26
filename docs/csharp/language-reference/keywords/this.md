---
title: this 关键字 - C# 参考
ms.custom: seodec18
description: this 关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 4a3342e73fef3effd54f72e68283eb6085eef5b5
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608444"
---
# <a name="this-c-reference"></a><span data-ttu-id="84efc-103">this（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="84efc-103">this (C# Reference)</span></span>

<span data-ttu-id="84efc-104">`this` 关键字指代类的当前实例，还可用作扩展方法的第一个参数的修饰符。</span><span class="sxs-lookup"><span data-stu-id="84efc-104">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>

> [!NOTE]
> <span data-ttu-id="84efc-105">本文介绍 `this` 在类实例中的用法。</span><span class="sxs-lookup"><span data-stu-id="84efc-105">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="84efc-106">若要深入了解它在扩展方法中的用法，请参阅[扩展方法](../../programming-guide/classes-and-structs/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="84efc-106">For more information about its use in extension methods, see [Extension Methods](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="84efc-107">以下是 `this` 的常见用法：</span><span class="sxs-lookup"><span data-stu-id="84efc-107">The following are common uses of `this`:</span></span>

- <span data-ttu-id="84efc-108">限定类似名称隐藏的成员，例如：</span><span class="sxs-lookup"><span data-stu-id="84efc-108">To qualify members hidden by similar names, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- <span data-ttu-id="84efc-109">将对象作为参数传递给方法，例如：</span><span class="sxs-lookup"><span data-stu-id="84efc-109">To pass an object as a parameter to other methods, for example:</span></span>

  ```csharp
  CalcTax(this);
  ```

- <span data-ttu-id="84efc-110">声明索引器，例如：</span><span class="sxs-lookup"><span data-stu-id="84efc-110">To declare indexers, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

<span data-ttu-id="84efc-111">静态成员函数，因为它们存在于类级别且不属于对象，不具有 `this` 指针。</span><span class="sxs-lookup"><span data-stu-id="84efc-111">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="84efc-112">在静态方法中引用 `this` 是错误的。</span><span class="sxs-lookup"><span data-stu-id="84efc-112">It is an error to refer to `this` in a static method.</span></span>

## <a name="example"></a><span data-ttu-id="84efc-113">示例</span><span class="sxs-lookup"><span data-stu-id="84efc-113">Example</span></span>

<span data-ttu-id="84efc-114">在此示例中，`this` 用于限定类似名称隐藏的 `Employee` 类成员、`name` 和 `alias`。</span><span class="sxs-lookup"><span data-stu-id="84efc-114">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="84efc-115">它还用于将某个对象传递给属于其他类的方法 `CalcTax`。</span><span class="sxs-lookup"><span data-stu-id="84efc-115">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="84efc-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="84efc-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="84efc-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="84efc-117">See also</span></span>

- [<span data-ttu-id="84efc-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="84efc-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="84efc-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="84efc-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="84efc-120">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="84efc-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="84efc-121">base</span><span class="sxs-lookup"><span data-stu-id="84efc-121">base</span></span>](base.md)
- [<span data-ttu-id="84efc-122">方法</span><span class="sxs-lookup"><span data-stu-id="84efc-122">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
