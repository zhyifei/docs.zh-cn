---
title: 内置类型表 - C# 参考
ms.custom: seodec18
description: 内置 C# 类型的关键字
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 4a54059f288a432cbaf904626cabf4f7bcba7209
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424376"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="29aaf-103">内置类型表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="29aaf-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="29aaf-104">下表显示内置 C# 类型的关键字，即 <xref:System> 命名空间中预定义类型的别名。</span><span class="sxs-lookup"><span data-stu-id="29aaf-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="29aaf-105">C# 类型</span><span class="sxs-lookup"><span data-stu-id="29aaf-105">C# type</span></span>|<span data-ttu-id="29aaf-106">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="29aaf-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="29aaf-107">bool</span><span class="sxs-lookup"><span data-stu-id="29aaf-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-108">byte</span><span class="sxs-lookup"><span data-stu-id="29aaf-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="29aaf-109">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-110">char</span><span class="sxs-lookup"><span data-stu-id="29aaf-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-111">decimal</span><span class="sxs-lookup"><span data-stu-id="29aaf-111">decimal</span></span>](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-112">double</span><span class="sxs-lookup"><span data-stu-id="29aaf-112">double</span></span>](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-113">float</span><span class="sxs-lookup"><span data-stu-id="29aaf-113">float</span></span>](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-114">int</span><span class="sxs-lookup"><span data-stu-id="29aaf-114">int</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-115">uint</span><span class="sxs-lookup"><span data-stu-id="29aaf-115">uint</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-116">long</span><span class="sxs-lookup"><span data-stu-id="29aaf-116">long</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-117">ulong</span><span class="sxs-lookup"><span data-stu-id="29aaf-117">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-118">object</span><span class="sxs-lookup"><span data-stu-id="29aaf-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-119">short</span><span class="sxs-lookup"><span data-stu-id="29aaf-119">short</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-120">ushort</span><span class="sxs-lookup"><span data-stu-id="29aaf-120">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="29aaf-121">string</span><span class="sxs-lookup"><span data-stu-id="29aaf-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="29aaf-122">备注</span><span class="sxs-lookup"><span data-stu-id="29aaf-122">Remarks</span></span>

<span data-ttu-id="29aaf-123">此表中的所有类型，除 `object` 和 `string` 外，皆被称为简单类型。</span><span class="sxs-lookup"><span data-stu-id="29aaf-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
<span data-ttu-id="29aaf-124">C# 类型关键字及其别名可互换。</span><span class="sxs-lookup"><span data-stu-id="29aaf-124">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="29aaf-125">例如，可通过使用以下任意一个声明来声明整型变量：</span><span class="sxs-lookup"><span data-stu-id="29aaf-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>  

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="29aaf-126">使用 [typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator) 运算符以获取表示指定类型的 <xref:System.Type?displayProperty=nameWithType> 实例：</span><span class="sxs-lookup"><span data-stu-id="29aaf-126">Use the [typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="29aaf-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="29aaf-127">See also</span></span>

- [<span data-ttu-id="29aaf-128">C# 参考</span><span class="sxs-lookup"><span data-stu-id="29aaf-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="29aaf-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="29aaf-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="29aaf-130">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="29aaf-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="29aaf-131">值类型</span><span class="sxs-lookup"><span data-stu-id="29aaf-131">Value types</span></span>](value-types.md)
- [<span data-ttu-id="29aaf-132">引用类型</span><span class="sxs-lookup"><span data-stu-id="29aaf-132">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="29aaf-133">默认值表</span><span class="sxs-lookup"><span data-stu-id="29aaf-133">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="29aaf-134">dynamic</span><span class="sxs-lookup"><span data-stu-id="29aaf-134">dynamic</span></span>](dynamic.md)
