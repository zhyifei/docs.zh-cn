---
title: 引用类型 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 4b3b1d5b27c3f6a88ce752243ab2d1389b168f0e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634059"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="57905-102">引用类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="57905-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="57905-103">C# 中有两种类型：引用类型和值类型。</span><span class="sxs-lookup"><span data-stu-id="57905-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="57905-104">引用类型的变量存储对其数据（对象）的引用，而值类型的变量直接包含其数据。</span><span class="sxs-lookup"><span data-stu-id="57905-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="57905-105">对于引用类型，两种变量可引用同一对象；因此，对一个变量执行的操作会影响另一个变量所引用的对象。</span><span class="sxs-lookup"><span data-stu-id="57905-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="57905-106">对于值类型，每个变量都具有其自己的数据副本，对一个变量执行的操作不会影响另一个变量（in、ref 和 out 参数变量除外；请参阅 [in](in-parameter-modifier.md)、[ref](ref.md) 和 [out](out-parameter-modifier.md) 参数修饰符）。</span><span class="sxs-lookup"><span data-stu-id="57905-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="57905-107">下列关键字用于声明引用类型：</span><span class="sxs-lookup"><span data-stu-id="57905-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="57905-108">class</span><span class="sxs-lookup"><span data-stu-id="57905-108">class</span></span>](class.md)

- [<span data-ttu-id="57905-109">interface</span><span class="sxs-lookup"><span data-stu-id="57905-109">interface</span></span>](interface.md)

- [<span data-ttu-id="57905-110">delegate</span><span class="sxs-lookup"><span data-stu-id="57905-110">delegate</span></span>](delegate.md)

 <span data-ttu-id="57905-111">C# 也提供了下列内置引用类型：</span><span class="sxs-lookup"><span data-stu-id="57905-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="57905-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="57905-112">dynamic</span></span>](dynamic.md)

- [<span data-ttu-id="57905-113">object</span><span class="sxs-lookup"><span data-stu-id="57905-113">object</span></span>](object.md)

- [<span data-ttu-id="57905-114">string</span><span class="sxs-lookup"><span data-stu-id="57905-114">string</span></span>](string.md)

## <a name="see-also"></a><span data-ttu-id="57905-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="57905-115">See also</span></span>

- [<span data-ttu-id="57905-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="57905-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="57905-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="57905-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="57905-118">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="57905-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="57905-119">类型</span><span class="sxs-lookup"><span data-stu-id="57905-119">Types</span></span>](types.md)
- [<span data-ttu-id="57905-120">值类型</span><span class="sxs-lookup"><span data-stu-id="57905-120">Value Types</span></span>](value-types.md)
