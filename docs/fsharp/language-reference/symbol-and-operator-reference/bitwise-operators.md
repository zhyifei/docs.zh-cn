---
title: 位运算符 (F#)
description: '了解有关 F # 编程语言中可用的按位运算符的信息。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4d5abff564a5d1dcbe52b99edf431ca10e442061
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="bitwise-operators"></a><span data-ttu-id="29479-103">位运算符</span><span class="sxs-lookup"><span data-stu-id="29479-103">Bitwise Operators</span></span>

<span data-ttu-id="29479-104">本主题介绍对 F # 语言中提供的按位运算符。</span><span class="sxs-lookup"><span data-stu-id="29479-104">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="29479-105">按位运算符的摘要</span><span class="sxs-lookup"><span data-stu-id="29479-105">Summary of Bitwise Operators</span></span>
<span data-ttu-id="29479-106">下表介绍对 F # 语言中的未装箱整型类型的支持的按位运算符。</span><span class="sxs-lookup"><span data-stu-id="29479-106">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="29479-107">运算符</span><span class="sxs-lookup"><span data-stu-id="29479-107">Operator</span></span>|<span data-ttu-id="29479-108">说明</span><span class="sxs-lookup"><span data-stu-id="29479-108">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="29479-109">按位 AND 运算符。</span><span class="sxs-lookup"><span data-stu-id="29479-109">Bitwise AND operator.</span></span> <span data-ttu-id="29479-110">当且仅当在源中的两个操作数的相应位均为 1，结果中的位将具有值 1。</span><span class="sxs-lookup"><span data-stu-id="29479-110">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="29479-111">按位 OR 运算符。</span><span class="sxs-lookup"><span data-stu-id="29479-111">Bitwise OR operator.</span></span> <span data-ttu-id="29479-112">结果中的位具有值 1，如果任一操作数的源中的对应位都是 1。</span><span class="sxs-lookup"><span data-stu-id="29479-112">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="29479-113">按位异或运算符。</span><span class="sxs-lookup"><span data-stu-id="29479-113">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="29479-114">当且仅当源操作数中的位具有不相等的值，结果中的位将具有值 1。</span><span class="sxs-lookup"><span data-stu-id="29479-114">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="29479-115">按位求反运算符。</span><span class="sxs-lookup"><span data-stu-id="29479-115">Bitwise negation operator.</span></span> <span data-ttu-id="29479-116">这是一个一元运算符，并生成的结果，在其中源操作数中的所有 0 位转换为 1 位，而所有 1 位转换为 0 的位。</span><span class="sxs-lookup"><span data-stu-id="29479-116">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="29479-117">按位左移运算符。</span><span class="sxs-lookup"><span data-stu-id="29479-117">Bitwise left-shift operator.</span></span> <span data-ttu-id="29479-118">结果是第一个操作数中的位左移的第二个操作数中的位数。</span><span class="sxs-lookup"><span data-stu-id="29479-118">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="29479-119">移出最高有效位的数位不会转入最低有效位。</span><span class="sxs-lookup"><span data-stu-id="29479-119">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="29479-120">最低有效位用零填充。</span><span class="sxs-lookup"><span data-stu-id="29479-120">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="29479-121">第二个参数的类型是`int32`。</span><span class="sxs-lookup"><span data-stu-id="29479-121">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="29479-122">按位右移运算符。</span><span class="sxs-lookup"><span data-stu-id="29479-122">Bitwise right-shift operator.</span></span> <span data-ttu-id="29479-123">结果是通过第二个操作数中的位数向右位移位进行运算的第一个操作数。</span><span class="sxs-lookup"><span data-stu-id="29479-123">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="29479-124">移去最低有效位不会转入最高有效位。</span><span class="sxs-lookup"><span data-stu-id="29479-124">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="29479-125">对于无符号类型，最高有效位将补零。</span><span class="sxs-lookup"><span data-stu-id="29479-125">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="29479-126">对于有符号类型，最高有效位将补替换为。</span><span class="sxs-lookup"><span data-stu-id="29479-126">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="29479-127">第二个参数的类型是`int32`。</span><span class="sxs-lookup"><span data-stu-id="29479-127">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="29479-128">可与按位运算符使用以下类型： `byte`， `sbyte`， `int16`， `uint16`， `int32 (int)`， `uint32`， `int64`， `uint64`， `nativeint`，和`unativeint`。</span><span class="sxs-lookup"><span data-stu-id="29479-128">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="29479-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="29479-129">See Also</span></span>
[<span data-ttu-id="29479-130">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="29479-130">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="29479-131">算术运算符</span><span class="sxs-lookup"><span data-stu-id="29479-131">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="29479-132">布尔运算符</span><span class="sxs-lookup"><span data-stu-id="29479-132">Boolean Operators</span></span>](boolean-operators.md)

