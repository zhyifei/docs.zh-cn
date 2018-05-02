---
title: 默认值表（C# 参考）
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
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
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e249dd2f352fe6177f3afbfd089fc4dc9b1b7798
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="3fae4-102">默认值表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3fae4-102">Default values table (C# Reference)</span></span>

<span data-ttu-id="3fae4-103">下表显示默认构造函数返回的值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="3fae4-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="3fae4-104">默认构造函数使用 `new` 运算符进行调用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fae4-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="3fae4-105">上一语句与如下语句效果相同：</span><span class="sxs-lookup"><span data-stu-id="3fae4-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="3fae4-106">请记住：不允许在 C# 中使用未初始化的变量。</span><span class="sxs-lookup"><span data-stu-id="3fae4-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="3fae4-107">值类型</span><span class="sxs-lookup"><span data-stu-id="3fae4-107">Value type</span></span>|<span data-ttu-id="3fae4-108">默认值</span><span class="sxs-lookup"><span data-stu-id="3fae4-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="3fae4-109">bool</span><span class="sxs-lookup"><span data-stu-id="3fae4-109">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="3fae4-110">byte</span><span class="sxs-lookup"><span data-stu-id="3fae4-110">byte</span></span>](byte.md)|<span data-ttu-id="3fae4-111">0</span><span class="sxs-lookup"><span data-stu-id="3fae4-111">0</span></span>|
|[<span data-ttu-id="3fae4-112">char</span><span class="sxs-lookup"><span data-stu-id="3fae4-112">char</span></span>](char.md)|<span data-ttu-id="3fae4-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="3fae4-113">'\0'</span></span>|
|[<span data-ttu-id="3fae4-114">decimal</span><span class="sxs-lookup"><span data-stu-id="3fae4-114">decimal</span></span>](decimal.md)|<span data-ttu-id="3fae4-115">0M</span><span class="sxs-lookup"><span data-stu-id="3fae4-115">0M</span></span>|
|[<span data-ttu-id="3fae4-116">double</span><span class="sxs-lookup"><span data-stu-id="3fae4-116">double</span></span>](double.md)|<span data-ttu-id="3fae4-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="3fae4-117">0.0D</span></span>|
|[<span data-ttu-id="3fae4-118">enum</span><span class="sxs-lookup"><span data-stu-id="3fae4-118">enum</span></span>](enum.md)|<span data-ttu-id="3fae4-119">表达式 (E)0 生成的值，其中 E 是枚举标识符。</span><span class="sxs-lookup"><span data-stu-id="3fae4-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="3fae4-120">float</span><span class="sxs-lookup"><span data-stu-id="3fae4-120">float</span></span>](float.md)|<span data-ttu-id="3fae4-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="3fae4-121">0.0F</span></span>|
|[<span data-ttu-id="3fae4-122">int</span><span class="sxs-lookup"><span data-stu-id="3fae4-122">int</span></span>](int.md)|<span data-ttu-id="3fae4-123">0</span><span class="sxs-lookup"><span data-stu-id="3fae4-123">0</span></span>|
|[<span data-ttu-id="3fae4-124">long</span><span class="sxs-lookup"><span data-stu-id="3fae4-124">long</span></span>](long.md)|<span data-ttu-id="3fae4-125">0L</span><span class="sxs-lookup"><span data-stu-id="3fae4-125">0L</span></span>|
|[<span data-ttu-id="3fae4-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="3fae4-126">sbyte</span></span>](sbyte.md)|<span data-ttu-id="3fae4-127">0</span><span class="sxs-lookup"><span data-stu-id="3fae4-127">0</span></span>|
|[<span data-ttu-id="3fae4-128">short</span><span class="sxs-lookup"><span data-stu-id="3fae4-128">short</span></span>](short.md)|<span data-ttu-id="3fae4-129">0</span><span class="sxs-lookup"><span data-stu-id="3fae4-129">0</span></span>|
|[<span data-ttu-id="3fae4-130">struct</span><span class="sxs-lookup"><span data-stu-id="3fae4-130">struct</span></span>](struct.md)|<span data-ttu-id="3fae4-131">通过如下设置生成的值：将所有值类型的字段设置为其默认值，将所有引用类型的字段设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="3fae4-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="3fae4-132">uint</span><span class="sxs-lookup"><span data-stu-id="3fae4-132">uint</span></span>](uint.md)|<span data-ttu-id="3fae4-133">0</span><span class="sxs-lookup"><span data-stu-id="3fae4-133">0</span></span>|
|[<span data-ttu-id="3fae4-134">ulong</span><span class="sxs-lookup"><span data-stu-id="3fae4-134">ulong</span></span>](ulong.md)|<span data-ttu-id="3fae4-135">0</span><span class="sxs-lookup"><span data-stu-id="3fae4-135">0</span></span>|
|[<span data-ttu-id="3fae4-136">ushort</span><span class="sxs-lookup"><span data-stu-id="3fae4-136">ushort</span></span>](ushort.md)|<span data-ttu-id="3fae4-137">0</span><span class="sxs-lookup"><span data-stu-id="3fae4-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="3fae4-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fae4-138">See also</span></span>
 [<span data-ttu-id="3fae4-139">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3fae4-139">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="3fae4-140">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3fae4-140">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="3fae4-141">值类型表</span><span class="sxs-lookup"><span data-stu-id="3fae4-141">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="3fae4-142">值类型</span><span class="sxs-lookup"><span data-stu-id="3fae4-142">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="3fae4-143">内置类型表</span><span class="sxs-lookup"><span data-stu-id="3fae4-143">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="3fae4-144">类型参考表</span><span class="sxs-lookup"><span data-stu-id="3fae4-144">Reference Tables for Types</span></span>](reference-tables-for-types.md)
