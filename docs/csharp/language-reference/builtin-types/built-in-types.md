---
title: 内置类型 - C# 参考
description: 了解 C# 内置值类型和引用类型
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 4f748373350ed0596a5f1d595c273243ae3227c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77095293"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="b807c-103">内置类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b807c-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="b807c-104">下表列出了 C# 内置[值](value-types.md)类型：</span><span class="sxs-lookup"><span data-stu-id="b807c-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="b807c-105">C# 类型关键字</span><span class="sxs-lookup"><span data-stu-id="b807c-105">C# type keyword</span></span>|<span data-ttu-id="b807c-106">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="b807c-106">.NET type</span></span>|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

<span data-ttu-id="b807c-107">下表列出了 C# 内置[引用](../keywords/reference-types.md)类型：</span><span class="sxs-lookup"><span data-stu-id="b807c-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="b807c-108">C# 类型关键字</span><span class="sxs-lookup"><span data-stu-id="b807c-108">C# type keyword</span></span>|<span data-ttu-id="b807c-109">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="b807c-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

<span data-ttu-id="b807c-110">在上表中，左侧列中的每个 C# 类型关键字都是相应 .NET 类型的别名。</span><span class="sxs-lookup"><span data-stu-id="b807c-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="b807c-111">它们是可互换的。</span><span class="sxs-lookup"><span data-stu-id="b807c-111">They are interchangeable.</span></span> <span data-ttu-id="b807c-112">例如，以下声明声明了相同类型的变量：</span><span class="sxs-lookup"><span data-stu-id="b807c-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

## <a name="see-also"></a><span data-ttu-id="b807c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b807c-113">See also</span></span>

- [<span data-ttu-id="b807c-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b807c-114">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b807c-115">C# 类型的默认值</span><span class="sxs-lookup"><span data-stu-id="b807c-115">Default values of C# types</span></span>](default-values.md)
- [<span data-ttu-id="b807c-116">`dynamic` 关键字</span><span class="sxs-lookup"><span data-stu-id="b807c-116">`dynamic` keyword</span></span>](reference-types.md#the-dynamic-type)
