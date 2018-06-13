---
title: 默认值表（C# 参考）
description: 了解默认构造函数返回的值类型的默认值。
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218785"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="98742-103">默认值表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="98742-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="98742-104">下表显示默认构造函数返回的值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="98742-104">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="98742-105">默认构造函数使用 `new` 运算符进行调用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98742-105">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="98742-106">上一语句与如下语句效果相同：</span><span class="sxs-lookup"><span data-stu-id="98742-106">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="98742-107">请记住：不允许在 C# 中使用未初始化的变量。</span><span class="sxs-lookup"><span data-stu-id="98742-107">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="98742-108">值类型</span><span class="sxs-lookup"><span data-stu-id="98742-108">Value type</span></span>|<span data-ttu-id="98742-109">默认值</span><span class="sxs-lookup"><span data-stu-id="98742-109">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="98742-110">bool</span><span class="sxs-lookup"><span data-stu-id="98742-110">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="98742-111">byte</span><span class="sxs-lookup"><span data-stu-id="98742-111">byte</span></span>](byte.md)|<span data-ttu-id="98742-112">0</span><span class="sxs-lookup"><span data-stu-id="98742-112">0</span></span>|
|[<span data-ttu-id="98742-113">char</span><span class="sxs-lookup"><span data-stu-id="98742-113">char</span></span>](char.md)|<span data-ttu-id="98742-114">'\0'</span><span class="sxs-lookup"><span data-stu-id="98742-114">'\0'</span></span>|
|[<span data-ttu-id="98742-115">decimal</span><span class="sxs-lookup"><span data-stu-id="98742-115">decimal</span></span>](decimal.md)|<span data-ttu-id="98742-116">0M</span><span class="sxs-lookup"><span data-stu-id="98742-116">0M</span></span>|
|[<span data-ttu-id="98742-117">double</span><span class="sxs-lookup"><span data-stu-id="98742-117">double</span></span>](double.md)|<span data-ttu-id="98742-118">0.0D</span><span class="sxs-lookup"><span data-stu-id="98742-118">0.0D</span></span>|
|[<span data-ttu-id="98742-119">enum</span><span class="sxs-lookup"><span data-stu-id="98742-119">enum</span></span>](enum.md)|<span data-ttu-id="98742-120">表达式 (E)0 生成的值，其中 E 是枚举标识符。</span><span class="sxs-lookup"><span data-stu-id="98742-120">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="98742-121">float</span><span class="sxs-lookup"><span data-stu-id="98742-121">float</span></span>](float.md)|<span data-ttu-id="98742-122">0.0F</span><span class="sxs-lookup"><span data-stu-id="98742-122">0.0F</span></span>|
|[<span data-ttu-id="98742-123">int</span><span class="sxs-lookup"><span data-stu-id="98742-123">int</span></span>](int.md)|<span data-ttu-id="98742-124">0</span><span class="sxs-lookup"><span data-stu-id="98742-124">0</span></span>|
|[<span data-ttu-id="98742-125">long</span><span class="sxs-lookup"><span data-stu-id="98742-125">long</span></span>](long.md)|<span data-ttu-id="98742-126">0L</span><span class="sxs-lookup"><span data-stu-id="98742-126">0L</span></span>|
|[<span data-ttu-id="98742-127">sbyte</span><span class="sxs-lookup"><span data-stu-id="98742-127">sbyte</span></span>](sbyte.md)|<span data-ttu-id="98742-128">0</span><span class="sxs-lookup"><span data-stu-id="98742-128">0</span></span>|
|[<span data-ttu-id="98742-129">short</span><span class="sxs-lookup"><span data-stu-id="98742-129">short</span></span>](short.md)|<span data-ttu-id="98742-130">0</span><span class="sxs-lookup"><span data-stu-id="98742-130">0</span></span>|
|[<span data-ttu-id="98742-131">struct</span><span class="sxs-lookup"><span data-stu-id="98742-131">struct</span></span>](struct.md)|<span data-ttu-id="98742-132">通过如下设置生成的值：将所有值类型的字段设置为其默认值，将所有引用类型的字段设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="98742-132">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="98742-133">uint</span><span class="sxs-lookup"><span data-stu-id="98742-133">uint</span></span>](uint.md)|<span data-ttu-id="98742-134">0</span><span class="sxs-lookup"><span data-stu-id="98742-134">0</span></span>|
|[<span data-ttu-id="98742-135">ulong</span><span class="sxs-lookup"><span data-stu-id="98742-135">ulong</span></span>](ulong.md)|<span data-ttu-id="98742-136">0</span><span class="sxs-lookup"><span data-stu-id="98742-136">0</span></span>|
|[<span data-ttu-id="98742-137">ushort</span><span class="sxs-lookup"><span data-stu-id="98742-137">ushort</span></span>](ushort.md)|<span data-ttu-id="98742-138">0</span><span class="sxs-lookup"><span data-stu-id="98742-138">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="98742-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="98742-139">See also</span></span>
 [<span data-ttu-id="98742-140">C# 参考</span><span class="sxs-lookup"><span data-stu-id="98742-140">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="98742-141">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="98742-141">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="98742-142">值类型表</span><span class="sxs-lookup"><span data-stu-id="98742-142">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="98742-143">值类型</span><span class="sxs-lookup"><span data-stu-id="98742-143">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="98742-144">内置类型表</span><span class="sxs-lookup"><span data-stu-id="98742-144">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="98742-145">类型参考表</span><span class="sxs-lookup"><span data-stu-id="98742-145">Reference Tables for Types</span></span>](reference-tables-for-types.md)
