---
title: '基本类型 （F #）'
description: '了解 F # 语言中使用的基础的基本类型。'
ms.date: 07/09/2018
ms.openlocfilehash: 8f948d066323527b09b1d3f9f4167b95b1c875cf
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "48026928"
---
# <a name="basic-types"></a><span data-ttu-id="16826-103">基本类型</span><span class="sxs-lookup"><span data-stu-id="16826-103">Basic types</span></span>

<span data-ttu-id="16826-104">本主题列出了在 F # 语言中定义的基本类型。</span><span class="sxs-lookup"><span data-stu-id="16826-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="16826-105">这些类型是最基本的 F # 中，几乎每个 F # 程序的基础。</span><span class="sxs-lookup"><span data-stu-id="16826-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="16826-106">它们是.NET 基元类型的一个超集。</span><span class="sxs-lookup"><span data-stu-id="16826-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="16826-107">类型</span><span class="sxs-lookup"><span data-stu-id="16826-107">Type</span></span>|<span data-ttu-id="16826-108">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="16826-108">.NET type</span></span>|<span data-ttu-id="16826-109">描述</span><span class="sxs-lookup"><span data-stu-id="16826-109">Description</span></span>|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="16826-110">可能的值为 `true` 和 `false`。</span><span class="sxs-lookup"><span data-stu-id="16826-110">Possible values are `true` and `false`.</span></span>|
|`byte`|<xref:System.Byte>|<span data-ttu-id="16826-111">从 0 到 255 之间的值。</span><span class="sxs-lookup"><span data-stu-id="16826-111">Values from 0 to 255.</span></span>|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="16826-112">从-128 到 127 之间的值。</span><span class="sxs-lookup"><span data-stu-id="16826-112">Values from -128 to 127.</span></span>|
|`int16`|<xref:System.Int16>|<span data-ttu-id="16826-113">从-32768 到 32767 之间的值。</span><span class="sxs-lookup"><span data-stu-id="16826-113">Values from -32768 to 32767.</span></span>|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="16826-114">值的范围是从 0 到 65535。</span><span class="sxs-lookup"><span data-stu-id="16826-114">Values from 0 to 65535.</span></span>|
|`int`|<xref:System.Int32>|<span data-ttu-id="16826-115">从-2147483648 到 2147483647 的值。</span><span class="sxs-lookup"><span data-stu-id="16826-115">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|<xref:System.UInt32>|<span data-ttu-id="16826-116">从 0 到 4294967295 之间的值。</span><span class="sxs-lookup"><span data-stu-id="16826-116">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|<xref:System.Int64>|<span data-ttu-id="16826-117">从-9223372036854775808 到 9,223,372,036,854,775,807 的值。</span><span class="sxs-lookup"><span data-stu-id="16826-117">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="16826-118">从 0 到 18446744073709551615 之间的值。</span><span class="sxs-lookup"><span data-stu-id="16826-118">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="16826-119">一个有符号整数形式的本机指针。</span><span class="sxs-lookup"><span data-stu-id="16826-119">A native pointer as a signed integer.</span></span>|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="16826-120">无符号整数形式的本机指针。</span><span class="sxs-lookup"><span data-stu-id="16826-120">A native pointer as an unsigned integer.</span></span>|
|`char`|<xref:System.Char>|<span data-ttu-id="16826-121">Unicode 字符值。</span><span class="sxs-lookup"><span data-stu-id="16826-121">Unicode character values.</span></span>|
|`string`|<xref:System.String>|<span data-ttu-id="16826-122">Unicode 文本。</span><span class="sxs-lookup"><span data-stu-id="16826-122">Unicode text.</span></span>|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="16826-123">一个浮点数据类型的至少 28 个有效位。</span><span class="sxs-lookup"><span data-stu-id="16826-123">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="16826-124">不适用</span><span class="sxs-lookup"><span data-stu-id="16826-124">not applicable</span></span>|<span data-ttu-id="16826-125">表示实际值不的存在。</span><span class="sxs-lookup"><span data-stu-id="16826-125">Indicates the absence of an actual value.</span></span> <span data-ttu-id="16826-126">该类型具有只有一个正式的值，该值表示`()`。</span><span class="sxs-lookup"><span data-stu-id="16826-126">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="16826-127">单元值， `()`，通常用作其中需要的值，但没有实际值是可用或者有意义的占位符。</span><span class="sxs-lookup"><span data-stu-id="16826-127">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|<xref:System.Void>|<span data-ttu-id="16826-128">指示没有类型或值。</span><span class="sxs-lookup"><span data-stu-id="16826-128">Indicates no type or value.</span></span>|
|<span data-ttu-id="16826-129">`float32`， `single`</span><span class="sxs-lookup"><span data-stu-id="16826-129">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="16826-130">32 位浮点类型。</span><span class="sxs-lookup"><span data-stu-id="16826-130">A 32-bit floating point type.</span></span>|
|<span data-ttu-id="16826-131">`float`， `double`</span><span class="sxs-lookup"><span data-stu-id="16826-131">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="16826-132">64 位浮点类型。</span><span class="sxs-lookup"><span data-stu-id="16826-132">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="16826-133">通过执行 64 位整数类型具有整数太大的计算[bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa)类型。</span><span class="sxs-lookup"><span data-stu-id="16826-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="16826-134">`bigint` 不被视为一种基本类型;是的缩写`System.Numerics.BigInteger`。</span><span class="sxs-lookup"><span data-stu-id="16826-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="16826-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="16826-135">See also</span></span>

- [<span data-ttu-id="16826-136">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="16826-136">F# Language Reference</span></span>](index.md)
