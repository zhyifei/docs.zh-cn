---
title: 内置类型表（C# 参考）
description: 内置 C# 类型的关键字
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: fd9ba878d77bdb219542db55bb38023c60c7bec4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507307"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="a5e76-103">内置类型表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a5e76-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="a5e76-104">下表显示内置 C# 类型的关键字，即 <xref:System> 命名空间中预定义类型的别名。</span><span class="sxs-lookup"><span data-stu-id="a5e76-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="a5e76-105">C# 类型</span><span class="sxs-lookup"><span data-stu-id="a5e76-105">C# type</span></span>|<span data-ttu-id="a5e76-106">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="a5e76-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="a5e76-107">bool</span><span class="sxs-lookup"><span data-stu-id="a5e76-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-108">byte</span><span class="sxs-lookup"><span data-stu-id="a5e76-108">byte</span></span>](byte.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="a5e76-109">sbyte</span></span>](sbyte.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-110">char</span><span class="sxs-lookup"><span data-stu-id="a5e76-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-111">decimal</span><span class="sxs-lookup"><span data-stu-id="a5e76-111">decimal</span></span>](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-112">double</span><span class="sxs-lookup"><span data-stu-id="a5e76-112">double</span></span>](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-113">float</span><span class="sxs-lookup"><span data-stu-id="a5e76-113">float</span></span>](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-114">int</span><span class="sxs-lookup"><span data-stu-id="a5e76-114">int</span></span>](int.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-115">uint</span><span class="sxs-lookup"><span data-stu-id="a5e76-115">uint</span></span>](uint.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-116">long</span><span class="sxs-lookup"><span data-stu-id="a5e76-116">long</span></span>](long.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-117">ulong</span><span class="sxs-lookup"><span data-stu-id="a5e76-117">ulong</span></span>](ulong.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-118">object</span><span class="sxs-lookup"><span data-stu-id="a5e76-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-119">short</span><span class="sxs-lookup"><span data-stu-id="a5e76-119">short</span></span>](short.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-120">ushort</span><span class="sxs-lookup"><span data-stu-id="a5e76-120">ushort</span></span>](ushort.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="a5e76-121">string</span><span class="sxs-lookup"><span data-stu-id="a5e76-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="a5e76-122">备注</span><span class="sxs-lookup"><span data-stu-id="a5e76-122">Remarks</span></span>

<span data-ttu-id="a5e76-123">此表中的所有类型，除 `object` 和 `string` 外，皆被称为简单类型。</span><span class="sxs-lookup"><span data-stu-id="a5e76-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
<span data-ttu-id="a5e76-124">C# 类型关键字及其别名可互换。</span><span class="sxs-lookup"><span data-stu-id="a5e76-124">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="a5e76-125">例如，可通过使用以下任意一个声明来声明整型变量：</span><span class="sxs-lookup"><span data-stu-id="a5e76-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>  

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="a5e76-126">使用 [typeof](typeof.md) 运算符以获取表示指定类型的 <xref:System.Type?displayProperty=nameWithType> 实例：</span><span class="sxs-lookup"><span data-stu-id="a5e76-126">Use the [typeof](typeof.md) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="a5e76-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5e76-127">See also</span></span>

- [<span data-ttu-id="a5e76-128">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a5e76-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="a5e76-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a5e76-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a5e76-130">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="a5e76-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a5e76-131">类型引用表</span><span class="sxs-lookup"><span data-stu-id="a5e76-131">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="a5e76-132">值类型</span><span class="sxs-lookup"><span data-stu-id="a5e76-132">Value types</span></span>](value-types.md)
- [<span data-ttu-id="a5e76-133">引用类型</span><span class="sxs-lookup"><span data-stu-id="a5e76-133">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="a5e76-134">默认值表</span><span class="sxs-lookup"><span data-stu-id="a5e76-134">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="a5e76-135">dynamic</span><span class="sxs-lookup"><span data-stu-id="a5e76-135">dynamic</span></span>](dynamic.md)
