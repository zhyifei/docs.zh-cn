---
title: 默认值表 - C# 参考
ms.custom: seodec18
description: 了解 C# 值类型的默认值。
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: dfab5107d4a0ad14c3ffbfc6a5f3c4317b44d17c
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424225"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="2793a-103">默认值表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2793a-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="2793a-104">下表显示[值类型](value-types.md)的默认值。</span><span class="sxs-lookup"><span data-stu-id="2793a-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="2793a-105">值类型</span><span class="sxs-lookup"><span data-stu-id="2793a-105">Value type</span></span>|<span data-ttu-id="2793a-106">默认值</span><span class="sxs-lookup"><span data-stu-id="2793a-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="2793a-107">bool</span><span class="sxs-lookup"><span data-stu-id="2793a-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="2793a-108">byte</span><span class="sxs-lookup"><span data-stu-id="2793a-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="2793a-109">0</span><span class="sxs-lookup"><span data-stu-id="2793a-109">0</span></span>|
|[<span data-ttu-id="2793a-110">char</span><span class="sxs-lookup"><span data-stu-id="2793a-110">char</span></span>](char.md)|<span data-ttu-id="2793a-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="2793a-111">'\0'</span></span>|
|[<span data-ttu-id="2793a-112">decimal</span><span class="sxs-lookup"><span data-stu-id="2793a-112">decimal</span></span>](decimal.md)|<span data-ttu-id="2793a-113">0M</span><span class="sxs-lookup"><span data-stu-id="2793a-113">0M</span></span>|
|[<span data-ttu-id="2793a-114">double</span><span class="sxs-lookup"><span data-stu-id="2793a-114">double</span></span>](double.md)|<span data-ttu-id="2793a-115">0.0D</span><span class="sxs-lookup"><span data-stu-id="2793a-115">0.0D</span></span>|
|[<span data-ttu-id="2793a-116">enum</span><span class="sxs-lookup"><span data-stu-id="2793a-116">enum</span></span>](enum.md)|<span data-ttu-id="2793a-117">表达式 `(E)0` 生成的值，其中 `E` 是枚举标识符。</span><span class="sxs-lookup"><span data-stu-id="2793a-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="2793a-118">float</span><span class="sxs-lookup"><span data-stu-id="2793a-118">float</span></span>](float.md)|<span data-ttu-id="2793a-119">0.0F</span><span class="sxs-lookup"><span data-stu-id="2793a-119">0.0F</span></span>|
|[<span data-ttu-id="2793a-120">int</span><span class="sxs-lookup"><span data-stu-id="2793a-120">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="2793a-121">0</span><span class="sxs-lookup"><span data-stu-id="2793a-121">0</span></span>|
|[<span data-ttu-id="2793a-122">long</span><span class="sxs-lookup"><span data-stu-id="2793a-122">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="2793a-123">0L</span><span class="sxs-lookup"><span data-stu-id="2793a-123">0L</span></span>|
|[<span data-ttu-id="2793a-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="2793a-124">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="2793a-125">0</span><span class="sxs-lookup"><span data-stu-id="2793a-125">0</span></span>|
|[<span data-ttu-id="2793a-126">short</span><span class="sxs-lookup"><span data-stu-id="2793a-126">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="2793a-127">0</span><span class="sxs-lookup"><span data-stu-id="2793a-127">0</span></span>|
|[<span data-ttu-id="2793a-128">struct</span><span class="sxs-lookup"><span data-stu-id="2793a-128">struct</span></span>](struct.md)|<span data-ttu-id="2793a-129">通过如下设置生成的值：将所有值类型的字段设置为其默认值，将所有引用类型的字段设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="2793a-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="2793a-130">uint</span><span class="sxs-lookup"><span data-stu-id="2793a-130">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="2793a-131">0</span><span class="sxs-lookup"><span data-stu-id="2793a-131">0</span></span>|
|[<span data-ttu-id="2793a-132">ulong</span><span class="sxs-lookup"><span data-stu-id="2793a-132">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="2793a-133">0</span><span class="sxs-lookup"><span data-stu-id="2793a-133">0</span></span>|
|[<span data-ttu-id="2793a-134">ushort</span><span class="sxs-lookup"><span data-stu-id="2793a-134">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="2793a-135">0</span><span class="sxs-lookup"><span data-stu-id="2793a-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="2793a-136">备注</span><span class="sxs-lookup"><span data-stu-id="2793a-136">Remarks</span></span>

<span data-ttu-id="2793a-137">无法在 C# 中使用未初始化的变量。</span><span class="sxs-lookup"><span data-stu-id="2793a-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="2793a-138">可以使用变量类型的默认值对变量进行初始化。</span><span class="sxs-lookup"><span data-stu-id="2793a-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="2793a-139">还可使用类型的默认值来指定方法的[可选参数](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments)的默认值。</span><span class="sxs-lookup"><span data-stu-id="2793a-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="2793a-140">使用[默认值表达式](../../programming-guide/statements-expressions-operators/default-value-expressions.md)生成类型的默认值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="2793a-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="2793a-141">从 C# 7.1 开始，可使用[`default`文本](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference)来初始化变量，使其具有其类型的默认值：</span><span class="sxs-lookup"><span data-stu-id="2793a-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="2793a-142">还可使用无参数构造函数或隐式无参数构造函数来生成值类型的默认值，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="2793a-142">You also can use the parameterless constructor or the implicit parameterless constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="2793a-143">有关构造函数的详细信息，请参阅[构造函数](../../programming-guide/classes-and-structs/constructors.md)一文。</span><span class="sxs-lookup"><span data-stu-id="2793a-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="2793a-144">任何[引用类型](reference-types.md)的默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="2793a-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="2793a-145">[可以为 null 的类型](../../programming-guide/nullable-types/index.md)的默认值是 <xref:System.Nullable%601.HasValue%2A> 属性为 `false` 且未定义 <xref:System.Nullable%601.Value%2A> 属性的实例。</span><span class="sxs-lookup"><span data-stu-id="2793a-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="2793a-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="2793a-146">See also</span></span>

- [<span data-ttu-id="2793a-147">C# 参考</span><span class="sxs-lookup"><span data-stu-id="2793a-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2793a-148">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2793a-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2793a-149">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="2793a-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2793a-150">值类型</span><span class="sxs-lookup"><span data-stu-id="2793a-150">Value types</span></span>](value-types.md)
- [<span data-ttu-id="2793a-151">值类型表</span><span class="sxs-lookup"><span data-stu-id="2793a-151">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="2793a-152">内置类型表</span><span class="sxs-lookup"><span data-stu-id="2793a-152">Built-in types table</span></span>](built-in-types-table.md)
