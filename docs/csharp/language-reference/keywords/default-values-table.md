---
title: 默认值表 - C# 引用
ms.custom: seodec18
description: 了解 C# 类型的默认值。
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 23fba8269670156000cb68b3aa07ae7c770eada1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627739"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="127f4-103">默认值表（C# 引用）</span><span class="sxs-lookup"><span data-stu-id="127f4-103">Default values table (C# reference)</span></span>

<span data-ttu-id="127f4-104">下表显示 C# 类型的默认值：</span><span class="sxs-lookup"><span data-stu-id="127f4-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="127f4-105">类型</span><span class="sxs-lookup"><span data-stu-id="127f4-105">Type</span></span>|<span data-ttu-id="127f4-106">默认值</span><span class="sxs-lookup"><span data-stu-id="127f4-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="127f4-107">任何引用类型</span><span class="sxs-lookup"><span data-stu-id="127f4-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="127f4-108">任何[内置整数数值类型](../builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="127f4-108">Any [built-in integral numeric type](../builtin-types/integral-numeric-types.md)</span></span>|<span data-ttu-id="127f4-109">0（零）</span><span class="sxs-lookup"><span data-stu-id="127f4-109">0 (zero)</span></span>|
|<span data-ttu-id="127f4-110">任何[内置浮点型数值类型](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="127f4-110">Any [built-in floating-point numeric type](../builtin-types/floating-point-numeric-types.md)</span></span>|<span data-ttu-id="127f4-111">0（零）</span><span class="sxs-lookup"><span data-stu-id="127f4-111">0 (zero)</span></span>|
|[<span data-ttu-id="127f4-112">bool</span><span class="sxs-lookup"><span data-stu-id="127f4-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="127f4-113">char</span><span class="sxs-lookup"><span data-stu-id="127f4-113">char</span></span>](char.md)|<span data-ttu-id="127f4-114">`'\0'` (U + 0000)</span><span class="sxs-lookup"><span data-stu-id="127f4-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="127f4-115">enum</span><span class="sxs-lookup"><span data-stu-id="127f4-115">enum</span></span>](enum.md)|<span data-ttu-id="127f4-116">表达式 `(E)0` 生成的值，其中 `E` 是枚举标识符。</span><span class="sxs-lookup"><span data-stu-id="127f4-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="127f4-117">struct</span><span class="sxs-lookup"><span data-stu-id="127f4-117">struct</span></span>](struct.md)|<span data-ttu-id="127f4-118">通过如下设置生成的值：将所有值类型的字段设置为其默认值，将所有引用类型的字段设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="127f4-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="127f4-119">任何[可以为 null 的值类型](../../programming-guide/nullable-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="127f4-119">Any [nullable value type](../../programming-guide/nullable-types/index.md)</span></span>|<span data-ttu-id="127f4-120"><xref:System.Nullable%601.HasValue%2A> 属性为 `false` 且 <xref:System.Nullable%601.Value%2A> 属性未定义的实例。</span><span class="sxs-lookup"><span data-stu-id="127f4-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="127f4-121">该默认值也称为可以为 null 的值类型的 null 值  。</span><span class="sxs-lookup"><span data-stu-id="127f4-121">That default value is also known as the *null* value of the nullable value type.</span></span>|

<span data-ttu-id="127f4-122">使用[默认值表达式](../../programming-guide/statements-expressions-operators/default-value-expressions.md)生成类型的默认值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="127f4-122">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="127f4-123">从 C# 7.1 开始，可使用[`default`文本](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference)来初始化变量，使其具有其类型的默认值：</span><span class="sxs-lookup"><span data-stu-id="127f4-123">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="127f4-124">对于值类型，隐式无参数构造函数还可生成类型的默认值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="127f4-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a><span data-ttu-id="127f4-125">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="127f4-125">C# language specification</span></span>

<span data-ttu-id="127f4-126">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="127f4-126">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="127f4-127">默认值</span><span class="sxs-lookup"><span data-stu-id="127f4-127">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="127f4-128">默认构造函数</span><span class="sxs-lookup"><span data-stu-id="127f4-128">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="127f4-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="127f4-129">See also</span></span>

- [<span data-ttu-id="127f4-130">C# 参考</span><span class="sxs-lookup"><span data-stu-id="127f4-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="127f4-131">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="127f4-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="127f4-132">内置类型表</span><span class="sxs-lookup"><span data-stu-id="127f4-132">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="127f4-133">构造函数</span><span class="sxs-lookup"><span data-stu-id="127f4-133">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
