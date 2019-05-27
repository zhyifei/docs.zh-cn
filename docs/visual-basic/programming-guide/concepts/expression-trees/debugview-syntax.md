---
title: 使用 DebugView 属性 (Visual Basic) 语法
description: 介绍 DebugView 属性用于生成表达式树的字符串表示形式的特殊语法
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 1b2a1164f02208cc7578820d8f8ed3bc145fb5b8
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196527"
---
# <a name="debugview-syntax"></a><span data-ttu-id="ad74e-103">`DebugView` 语法</span><span class="sxs-lookup"><span data-stu-id="ad74e-103">`DebugView` syntax</span></span> 

<span data-ttu-id="ad74e-104">`DebugView`属性 （仅在调试时可用） 提供的表达式树的字符串呈现。</span><span class="sxs-lookup"><span data-stu-id="ad74e-104">The `DebugView` property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="ad74e-105">大部分语法是非常简单，若要了解;以下各节所述的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="ad74e-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="ad74e-106">每个示例后跟一个注释块，其中包含`DebugView`。</span><span class="sxs-lookup"><span data-stu-id="ad74e-106">Each example is followed by a comment block containing the `DebugView`.</span></span> 

## <a name="parameterexpression"></a><span data-ttu-id="ad74e-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="ad74e-107">ParameterExpression</span></span>

<span data-ttu-id="ad74e-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> 变量名称的开头显示有“$”符号。</span><span class="sxs-lookup"><span data-stu-id="ad74e-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="ad74e-109">如果参数没有名称，则会为其分配一个自动生成的名称，例如 `$var1` 或 `$var2`。</span><span class="sxs-lookup"><span data-stu-id="ad74e-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="ad74e-110">示例</span><span class="sxs-lookup"><span data-stu-id="ad74e-110">Examples</span></span>

```vb
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")
'
'    $num
'

Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer))
'
'    $var1
'
```

## <a name="constantexpressions"></a><span data-ttu-id="ad74e-111">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="ad74e-111">ConstantExpressions</span></span>

<span data-ttu-id="ad74e-112">对于表示整数值、字符串和 `null` 的 <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> 对象，将显示常数的值。</span><span class="sxs-lookup"><span data-stu-id="ad74e-112">For <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="ad74e-113">对于某些数值类型，将后缀添加到值：</span><span class="sxs-lookup"><span data-stu-id="ad74e-113">For some numeric types, a suffix is added to the value:</span></span>

| <span data-ttu-id="ad74e-114">类型</span><span class="sxs-lookup"><span data-stu-id="ad74e-114">Type</span></span> | <span data-ttu-id="ad74e-115">关键字</span><span class="sxs-lookup"><span data-stu-id="ad74e-115">Keyword</span></span> | <span data-ttu-id="ad74e-116">Suffix</span><span class="sxs-lookup"><span data-stu-id="ad74e-116">Suffix</span></span> |  
|--|--|--|
| <xref:System.UInt32> | [<span data-ttu-id="ad74e-117">UInteger</span><span class="sxs-lookup"><span data-stu-id="ad74e-117">UInteger</span></span>](../../../language-reference/data-types/uinteger-data-type.md) | <span data-ttu-id="ad74e-118">U</span><span class="sxs-lookup"><span data-stu-id="ad74e-118">U</span></span> |
| <xref:System.Int64> | [<span data-ttu-id="ad74e-119">Long</span><span class="sxs-lookup"><span data-stu-id="ad74e-119">Long</span></span>](../../../language-reference/data-types/long-data-type.md) | <span data-ttu-id="ad74e-120">L</span><span class="sxs-lookup"><span data-stu-id="ad74e-120">L</span></span> |
| <xref:System.UInt64> | [<span data-ttu-id="ad74e-121">ULong</span><span class="sxs-lookup"><span data-stu-id="ad74e-121">ULong</span></span>](../../../language-reference/data-types/ulong-data-type.md) | <span data-ttu-id="ad74e-122">UL</span><span class="sxs-lookup"><span data-stu-id="ad74e-122">UL</span></span> |
| <xref:System.Double> | [<span data-ttu-id="ad74e-123">Double</span><span class="sxs-lookup"><span data-stu-id="ad74e-123">Double</span></span>](../../../language-reference/data-types/double-data-type.md) | <span data-ttu-id="ad74e-124">D</span><span class="sxs-lookup"><span data-stu-id="ad74e-124">D</span></span> |
| <xref:System.Single> | [<span data-ttu-id="ad74e-125">Single</span><span class="sxs-lookup"><span data-stu-id="ad74e-125">Single</span></span>](../../../language-reference/data-types/single-data-type.md) | <span data-ttu-id="ad74e-126">F</span><span class="sxs-lookup"><span data-stu-id="ad74e-126">F</span></span> | 
| <xref:System.Decimal> | [<span data-ttu-id="ad74e-127">小数</span><span class="sxs-lookup"><span data-stu-id="ad74e-127">Decimal</span></span>](../../../language-reference/data-types/decimal-data-type.md) | <span data-ttu-id="ad74e-128">M</span><span class="sxs-lookup"><span data-stu-id="ad74e-128">M</span></span> |

### <a name="examples"></a><span data-ttu-id="ad74e-129">示例</span><span class="sxs-lookup"><span data-stu-id="ad74e-129">Examples</span></span>

```vb
Dim num as Integer = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10
'

Dim num As Double = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10D
'
```

## <a name="blockexpression"></a><span data-ttu-id="ad74e-130">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="ad74e-130">BlockExpression</span></span>

<span data-ttu-id="ad74e-131">如果类型<xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType>对象与块中的最后一个表达式的类型不同，在尖括号内显示的类型 (`<`和`>`)。</span><span class="sxs-lookup"><span data-stu-id="ad74e-131">If the type of a <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="ad74e-132">否则，将不显示 <xref:System.Linq.Expressions.BlockExpression> 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="ad74e-132">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="ad74e-133">示例</span><span class="sxs-lookup"><span data-stu-id="ad74e-133">Examples</span></span>

```vb
Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
'
'    .Block() {
'        "test"
'    }
'

Dim block As BlockExpression = Expression.Block(
    GetType(Object), 
    Expression.Constant("test")
)
'
'    .Block<System.Object>() {
'        "test"
'    }
'
```

## <a name="lambdaexpression"></a><span data-ttu-id="ad74e-134">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="ad74e-134">LambdaExpression</span></span>

<span data-ttu-id="ad74e-135">显示 <xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> 对象及其委托类型。</span><span class="sxs-lookup"><span data-stu-id="ad74e-135"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="ad74e-136">如果 lambda 表达式没有名称，则会为其分配一个自动生成的名称，例如 `#Lambda1` 或 `#Lambda2`。</span><span class="sxs-lookup"><span data-stu-id="ad74e-136">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="ad74e-137">示例</span><span class="sxs-lookup"><span data-stu-id="ad74e-137">Examples</span></span>

```vb
Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1)
)
'
'    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
'        1
'    }
'

Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1),
    "SampleLambda",
    Nothing
)
'
'    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
'        1
'    }
'
```

## <a name="labelexpression"></a><span data-ttu-id="ad74e-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="ad74e-138">LabelExpression</span></span>

<span data-ttu-id="ad74e-139">如果指定 <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> 对象的默认值，则在 <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> 对象之前显示此值。</span><span class="sxs-lookup"><span data-stu-id="ad74e-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="ad74e-140">`.Label` 令牌指示标签的开头。</span><span class="sxs-lookup"><span data-stu-id="ad74e-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="ad74e-141">`.LabelTarget` 令牌指示要跳转到的目标的目的地。</span><span class="sxs-lookup"><span data-stu-id="ad74e-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="ad74e-142">如果标签没有名称，则会为其分配一个自动生成的名称，例如 `#Label1` 或 `#Label2`。</span><span class="sxs-lookup"><span data-stu-id="ad74e-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="ad74e-143">示例</span><span class="sxs-lookup"><span data-stu-id="ad74e-143">Examples</span></span>

```vb
Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
)
'
'    .Block() {
'        .Goto SampleLabel { 0 };
'        .Label
'            -1
'        .LabelTarget SampleLabel:
'    }
'

Dim target As LabelTarget = Expression.Label()
Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), 
    Expression.Label(target)
)
'
'    .Block() {
'        .Goto #Label1 { };
'        .Label
'        .LabelTarget #Label1:
'    }
'
```

## <a name="checked-operators"></a><span data-ttu-id="ad74e-144">Checked 运算符</span><span class="sxs-lookup"><span data-stu-id="ad74e-144">Checked Operators</span></span>

<span data-ttu-id="ad74e-145">Checked 的运算符将显示与`#`在运算符前面的符号。</span><span class="sxs-lookup"><span data-stu-id="ad74e-145">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="ad74e-146">例如，checked 加号显示为 `#+`。</span><span class="sxs-lookup"><span data-stu-id="ad74e-146">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="ad74e-147">示例</span><span class="sxs-lookup"><span data-stu-id="ad74e-147">Examples</span></span>

```vb
Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1),
    Expression.Constant(2)
)
'
'     1 #+ 2
'

Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0),
    GetType(Integer)
)
'
'    #(System.Int32)10D
'
```