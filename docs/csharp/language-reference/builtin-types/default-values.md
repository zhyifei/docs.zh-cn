---
title: C# 类型的默认值 - C# 参考
description: 了解 C# 类型的默认值，例如 bool、char、int、float 和 double 等。
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 5e34d291ec15c738f3bc9409df321ede454b6710
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507251"
---
# <a name="default-values-of-c-types-c-reference"></a><span data-ttu-id="64100-103">C# 类型的默认值（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="64100-103">Default values of C# types (C# reference)</span></span>

<span data-ttu-id="64100-104">下表显示 C# 类型的默认值：</span><span class="sxs-lookup"><span data-stu-id="64100-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="64100-105">类型</span><span class="sxs-lookup"><span data-stu-id="64100-105">Type</span></span>|<span data-ttu-id="64100-106">默认值</span><span class="sxs-lookup"><span data-stu-id="64100-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="64100-107">任何引用类型</span><span class="sxs-lookup"><span data-stu-id="64100-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="64100-108">任何[内置整数数值类型](integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="64100-108">Any [built-in integral numeric type](integral-numeric-types.md)</span></span>|<span data-ttu-id="64100-109">0（零）</span><span class="sxs-lookup"><span data-stu-id="64100-109">0 (zero)</span></span>|
|<span data-ttu-id="64100-110">任何[内置浮点型数值类型](floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="64100-110">Any [built-in floating-point numeric type](floating-point-numeric-types.md)</span></span>|<span data-ttu-id="64100-111">0（零）</span><span class="sxs-lookup"><span data-stu-id="64100-111">0 (zero)</span></span>|
|[<span data-ttu-id="64100-112">bool</span><span class="sxs-lookup"><span data-stu-id="64100-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="64100-113">char</span><span class="sxs-lookup"><span data-stu-id="64100-113">char</span></span>](char.md)|<span data-ttu-id="64100-114">`'\0'` (U + 0000)</span><span class="sxs-lookup"><span data-stu-id="64100-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="64100-115">enum</span><span class="sxs-lookup"><span data-stu-id="64100-115">enum</span></span>](enum.md)|<span data-ttu-id="64100-116">表达式 `(E)0` 生成的值，其中 `E` 是枚举标识符。</span><span class="sxs-lookup"><span data-stu-id="64100-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="64100-117">struct</span><span class="sxs-lookup"><span data-stu-id="64100-117">struct</span></span>](struct.md)|<span data-ttu-id="64100-118">通过如下设置生成的值：将所有值类型的字段设置为其默认值，将所有引用类型的字段设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="64100-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="64100-119">任何[可以为 null 的值类型](nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="64100-119">Any [nullable value type](nullable-value-types.md)</span></span>|<span data-ttu-id="64100-120"><xref:System.Nullable%601.HasValue%2A> 属性为 `false` 且 <xref:System.Nullable%601.Value%2A> 属性未定义的实例。</span><span class="sxs-lookup"><span data-stu-id="64100-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="64100-121">该默认值也称为可以为 null 的值类型的“null”  值。</span><span class="sxs-lookup"><span data-stu-id="64100-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="64100-122">使用 [`default` 运算符](../operators/default.md#default-operator)生成默认类型值，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="64100-122">Use the [`default` operator](../operators/default.md#default-operator) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="64100-123">从 C# 7.1 开始，可使用[`default`文本](../operators/default.md#default-literal)来初始化变量，使其具有其类型的默认值：</span><span class="sxs-lookup"><span data-stu-id="64100-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="64100-124">对于值类型，隐式无参数构造函数还可生成类型的默认值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="64100-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

<span data-ttu-id="64100-125">在运行时，如果 <xref:System.Type?displayProperty=nameWithType> 实例表示一个值类型，则可以使用 <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> 方法来调用无参数构造函数，以获取该类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="64100-125">At run time, if the <xref:System.Type?displayProperty=nameWithType> instance represents a value type, you can use the <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> method to invoke the parameterless constructor to obtain the default value of the type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="64100-126">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="64100-126">C# language specification</span></span>

<span data-ttu-id="64100-127">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="64100-127">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="64100-128">默认值</span><span class="sxs-lookup"><span data-stu-id="64100-128">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="64100-129">默认构造函数</span><span class="sxs-lookup"><span data-stu-id="64100-129">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="64100-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="64100-130">See also</span></span>

- [<span data-ttu-id="64100-131">C# 参考</span><span class="sxs-lookup"><span data-stu-id="64100-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="64100-132">构造函数</span><span class="sxs-lookup"><span data-stu-id="64100-132">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
