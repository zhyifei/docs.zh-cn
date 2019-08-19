---
title: 内置类型表 - C# 参考
ms.custom: seodec18
description: 内置 C# 类型的关键字
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 61701cc38c38b5e7235fbadb6d2a86e0e66b09ac
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566362"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="46029-103">内置类型表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="46029-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="46029-104">下表显示内置 C# 类型的关键字，即 <xref:System> 命名空间中预定义类型的别名。</span><span class="sxs-lookup"><span data-stu-id="46029-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="46029-105">C# 类型</span><span class="sxs-lookup"><span data-stu-id="46029-105">C# type</span></span>|<span data-ttu-id="46029-106">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="46029-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="46029-107">bool</span><span class="sxs-lookup"><span data-stu-id="46029-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-108">byte</span><span class="sxs-lookup"><span data-stu-id="46029-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="46029-109">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-110">char</span><span class="sxs-lookup"><span data-stu-id="46029-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-111">decimal</span><span class="sxs-lookup"><span data-stu-id="46029-111">decimal</span></span>](../builtin-types/floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-112">double</span><span class="sxs-lookup"><span data-stu-id="46029-112">double</span></span>](../builtin-types/floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-113">float</span><span class="sxs-lookup"><span data-stu-id="46029-113">float</span></span>](../builtin-types/floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-114">int</span><span class="sxs-lookup"><span data-stu-id="46029-114">int</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-115">uint</span><span class="sxs-lookup"><span data-stu-id="46029-115">uint</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-116">long</span><span class="sxs-lookup"><span data-stu-id="46029-116">long</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-117">ulong</span><span class="sxs-lookup"><span data-stu-id="46029-117">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-118">object</span><span class="sxs-lookup"><span data-stu-id="46029-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-119">short</span><span class="sxs-lookup"><span data-stu-id="46029-119">short</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-120">ushort</span><span class="sxs-lookup"><span data-stu-id="46029-120">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="46029-121">string</span><span class="sxs-lookup"><span data-stu-id="46029-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="46029-122">备注</span><span class="sxs-lookup"><span data-stu-id="46029-122">Remarks</span></span>

<span data-ttu-id="46029-123">此表中的所有类型，除 `object` 和 `string` 外，皆被称为简单类型。</span><span class="sxs-lookup"><span data-stu-id="46029-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
<span data-ttu-id="46029-124">.NET 类型及其 C# 类型关键字别名可互换。</span><span class="sxs-lookup"><span data-stu-id="46029-124">The .NET types and their C# type keyword aliases are interchangeable.</span></span> <span data-ttu-id="46029-125">例如，可通过使用以下任意一个声明来声明整型变量：</span><span class="sxs-lookup"><span data-stu-id="46029-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>  

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="46029-126">使用 [typeof](../operators/type-testing-and-cast.md#typeof-operator) 运算符以获取表示指定类型的 <xref:System.Type?displayProperty=nameWithType> 实例：</span><span class="sxs-lookup"><span data-stu-id="46029-126">Use the [typeof](../operators/type-testing-and-cast.md#typeof-operator) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="46029-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="46029-127">See also</span></span>

- [<span data-ttu-id="46029-128">C# 参考</span><span class="sxs-lookup"><span data-stu-id="46029-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="46029-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="46029-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="46029-130">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="46029-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="46029-131">值类型</span><span class="sxs-lookup"><span data-stu-id="46029-131">Value types</span></span>](value-types.md)
- [<span data-ttu-id="46029-132">引用类型</span><span class="sxs-lookup"><span data-stu-id="46029-132">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="46029-133">默认值表</span><span class="sxs-lookup"><span data-stu-id="46029-133">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="46029-134">dynamic</span><span class="sxs-lookup"><span data-stu-id="46029-134">dynamic</span></span>](dynamic.md)
