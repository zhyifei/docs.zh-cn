---
title: 基元类型 (F#)
description: '发现的基础的基元类型，F # 语言中使用。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 7832151ee211f56547ecad98fc31f1454cb18870
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="primitive-types"></a><span data-ttu-id="7030c-103">基元类型</span><span class="sxs-lookup"><span data-stu-id="7030c-103">Primitive Types</span></span>

<span data-ttu-id="7030c-104">本主题列出了 F # 语言中使用的基础基元类型。</span><span class="sxs-lookup"><span data-stu-id="7030c-104">This topic lists the fundamental primitive types that are used in the F# language.</span></span> <span data-ttu-id="7030c-105">它还提供每种类型的相应 .NET 类型和最小和最大值。</span><span class="sxs-lookup"><span data-stu-id="7030c-105">It also provides the corresponding .NET types and the minimum and maximum values for each type.</span></span>

## <a name="summary-of-primitive-types"></a><span data-ttu-id="7030c-106">基元类型的摘要</span><span class="sxs-lookup"><span data-stu-id="7030c-106">Summary of Primitive Types</span></span>
<span data-ttu-id="7030c-107">下表总结了基元的 F # 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="7030c-107">The following table summarizes the properties of the primitive F# types.</span></span>

|<span data-ttu-id="7030c-108">类型</span><span class="sxs-lookup"><span data-stu-id="7030c-108">Type</span></span>|<span data-ttu-id="7030c-109">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="7030c-109">.NET type</span></span>|<span data-ttu-id="7030c-110">描述</span><span class="sxs-lookup"><span data-stu-id="7030c-110">Description</span></span>|
|----|---------|-----------|
|`bool`|`System.Boolean`|<span data-ttu-id="7030c-111">可能的值为 `true` 和 `false`。</span><span class="sxs-lookup"><span data-stu-id="7030c-111">Possible values are `true` and `false`.</span></span>|
|`byte`|`System.Byte`|<span data-ttu-id="7030c-112">值的范围是从 0 到 255。</span><span class="sxs-lookup"><span data-stu-id="7030c-112">Values from 0 to 255.</span></span>|
|`sbyte`|`System.SByte`|<span data-ttu-id="7030c-113">值的范围是从-128 到 127 之间。</span><span class="sxs-lookup"><span data-stu-id="7030c-113">Values from -128 to 127.</span></span>|
|`int16`|`System.Int16`|<span data-ttu-id="7030c-114">从-32768 到 32767 之间的值。</span><span class="sxs-lookup"><span data-stu-id="7030c-114">Values from -32768 to 32767.</span></span>|
|`uint16`|`System.UInt16`|<span data-ttu-id="7030c-115">值的范围是从 0 到 65535。</span><span class="sxs-lookup"><span data-stu-id="7030c-115">Values from 0 to 65535.</span></span>|
|`int`|`System.Int32`|<span data-ttu-id="7030c-116">从-2147483648 到 2147483647 的值。</span><span class="sxs-lookup"><span data-stu-id="7030c-116">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|`System.UInt32`|<span data-ttu-id="7030c-117">从 0 到 4294967295 之间的值。</span><span class="sxs-lookup"><span data-stu-id="7030c-117">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|`System.Int64`|<span data-ttu-id="7030c-118">值的范围是从-9223372036854775808 到 9223372036854775807。</span><span class="sxs-lookup"><span data-stu-id="7030c-118">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|`System.UInt64`|<span data-ttu-id="7030c-119">从 0 到 18446744073709551615 之间的值。</span><span class="sxs-lookup"><span data-stu-id="7030c-119">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|`System.IntPtr`|<span data-ttu-id="7030c-120">一个带符号整数形式的本机指针。</span><span class="sxs-lookup"><span data-stu-id="7030c-120">A native pointer as a signed integer.</span></span>|
|`unativeint`|`System.UIntPtr`|<span data-ttu-id="7030c-121">本机指针作为无符号整数。</span><span class="sxs-lookup"><span data-stu-id="7030c-121">A native pointer as an unsigned integer.</span></span>|
|`char`|`System.Char`|<span data-ttu-id="7030c-122">Unicode 字符值。</span><span class="sxs-lookup"><span data-stu-id="7030c-122">Unicode character values.</span></span>|
|`string`|`System.String`|<span data-ttu-id="7030c-123">Unicode 文本。</span><span class="sxs-lookup"><span data-stu-id="7030c-123">Unicode text.</span></span>|
|`decimal`|`System.Decimal`|<span data-ttu-id="7030c-124">一个浮点数据类型具有至少 28 个有效位。</span><span class="sxs-lookup"><span data-stu-id="7030c-124">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="7030c-125">不适用</span><span class="sxs-lookup"><span data-stu-id="7030c-125">not applicable</span></span>|<span data-ttu-id="7030c-126">表示实际值的缺失。</span><span class="sxs-lookup"><span data-stu-id="7030c-126">Indicates the absence of an actual value.</span></span> <span data-ttu-id="7030c-127">该类型具有只有一个正式的值，表示`()`。</span><span class="sxs-lookup"><span data-stu-id="7030c-127">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="7030c-128">单元值， `()`，通常用作的占位符其中需要值但没有真正的价值可用或者有意义。</span><span class="sxs-lookup"><span data-stu-id="7030c-128">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|`System.Void`|<span data-ttu-id="7030c-129">不指示任何类型或值。</span><span class="sxs-lookup"><span data-stu-id="7030c-129">Indicates no type or value.</span></span>|
|`float32, single`|`System.Single`|<span data-ttu-id="7030c-130">一个 32 位浮点类型。</span><span class="sxs-lookup"><span data-stu-id="7030c-130">A 32-bit floating point type.</span></span>|
|`float, double`|`System.Double`|<span data-ttu-id="7030c-131">一个 64 位浮点类型。</span><span class="sxs-lookup"><span data-stu-id="7030c-131">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="7030c-132">可以通过使用 64 位整数类型中执行计算传递具有整数太大[bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa)类型。</span><span class="sxs-lookup"><span data-stu-id="7030c-132">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="7030c-133">`bigint` 不被视为基元的类型;它是的缩写`System.Numerics.BigInteger`。</span><span class="sxs-lookup"><span data-stu-id="7030c-133">`bigint` is not considered a primitive type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7030c-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="7030c-134">See Also</span></span>
[<span data-ttu-id="7030c-135">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="7030c-135">F# Language Reference</span></span>](index.md)
