---
title: "默认值表（C# 参考）"
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d034c1daf495c50e299fec4c5bf399652dad08ce
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2017
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="9c62f-102">默认值表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9c62f-102">Default values table (C# Reference)</span></span>
<span data-ttu-id="9c62f-103">下表显示默认构造函数返回的值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="9c62f-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="9c62f-104">默认构造函数使用 `new` 运算符进行调用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9c62f-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="9c62f-105">上一语句与如下语句效果相同：</span><span class="sxs-lookup"><span data-stu-id="9c62f-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="9c62f-106">请记住：不允许在 C# 中使用未初始化的变量。</span><span class="sxs-lookup"><span data-stu-id="9c62f-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="9c62f-107">值类型</span><span class="sxs-lookup"><span data-stu-id="9c62f-107">Value type</span></span>|<span data-ttu-id="9c62f-108">默认值</span><span class="sxs-lookup"><span data-stu-id="9c62f-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="9c62f-109">bool</span><span class="sxs-lookup"><span data-stu-id="9c62f-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="9c62f-110">byte</span><span class="sxs-lookup"><span data-stu-id="9c62f-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="9c62f-111">0</span><span class="sxs-lookup"><span data-stu-id="9c62f-111">0</span></span>|
|[<span data-ttu-id="9c62f-112">char</span><span class="sxs-lookup"><span data-stu-id="9c62f-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="9c62f-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="9c62f-113">'\0'</span></span>|
|[<span data-ttu-id="9c62f-114">小数</span><span class="sxs-lookup"><span data-stu-id="9c62f-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="9c62f-115">0 M</span><span class="sxs-lookup"><span data-stu-id="9c62f-115">0M</span></span>|
|[<span data-ttu-id="9c62f-116">double</span><span class="sxs-lookup"><span data-stu-id="9c62f-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="9c62f-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="9c62f-117">0.0D</span></span>|
|[<span data-ttu-id="9c62f-118">enum</span><span class="sxs-lookup"><span data-stu-id="9c62f-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="9c62f-119">表达式 (E)0 生成的值，其中 E 是枚举标识符。</span><span class="sxs-lookup"><span data-stu-id="9c62f-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="9c62f-120">float</span><span class="sxs-lookup"><span data-stu-id="9c62f-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="9c62f-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="9c62f-121">0.0F</span></span>|
|[<span data-ttu-id="9c62f-122">int</span><span class="sxs-lookup"><span data-stu-id="9c62f-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="9c62f-123">0</span><span class="sxs-lookup"><span data-stu-id="9c62f-123">0</span></span>|
|[<span data-ttu-id="9c62f-124">long</span><span class="sxs-lookup"><span data-stu-id="9c62f-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="9c62f-125">0L</span><span class="sxs-lookup"><span data-stu-id="9c62f-125">0L</span></span>|
|[<span data-ttu-id="9c62f-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="9c62f-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="9c62f-127">0</span><span class="sxs-lookup"><span data-stu-id="9c62f-127">0</span></span>|
|[<span data-ttu-id="9c62f-128">short</span><span class="sxs-lookup"><span data-stu-id="9c62f-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="9c62f-129">0</span><span class="sxs-lookup"><span data-stu-id="9c62f-129">0</span></span>|
|[<span data-ttu-id="9c62f-130">struct</span><span class="sxs-lookup"><span data-stu-id="9c62f-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="9c62f-131">通过如下设置生成的值：将所有值类型的字段设置为其默认值，将所有引用类型的字段设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="9c62f-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="9c62f-132">uint</span><span class="sxs-lookup"><span data-stu-id="9c62f-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="9c62f-133">0</span><span class="sxs-lookup"><span data-stu-id="9c62f-133">0</span></span>|
|[<span data-ttu-id="9c62f-134">ulong</span><span class="sxs-lookup"><span data-stu-id="9c62f-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="9c62f-135">0</span><span class="sxs-lookup"><span data-stu-id="9c62f-135">0</span></span>|
|[<span data-ttu-id="9c62f-136">ushort</span><span class="sxs-lookup"><span data-stu-id="9c62f-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="9c62f-137">0</span><span class="sxs-lookup"><span data-stu-id="9c62f-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="9c62f-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c62f-138">See also</span></span>
 [<span data-ttu-id="9c62f-139">C# 参考</span><span class="sxs-lookup"><span data-stu-id="9c62f-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9c62f-140">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9c62f-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9c62f-141">值类型表</span><span class="sxs-lookup"><span data-stu-id="9c62f-141">Value Types Table</span></span>](../../../csharp/language-reference/keywords/value-types-table.md)  
 [<span data-ttu-id="9c62f-142">值类型</span><span class="sxs-lookup"><span data-stu-id="9c62f-142">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="9c62f-143">内置类型表</span><span class="sxs-lookup"><span data-stu-id="9c62f-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="9c62f-144">类型参考表</span><span class="sxs-lookup"><span data-stu-id="9c62f-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
