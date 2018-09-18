---
title: 位运算符 (F#)
description: '了解有关 F # 编程语言中可用的按位运算符。'
ms.date: 07/20/2018
ms.openlocfilehash: ed76fcf5f9c569a2f288cf260e99dc29fd65ef3b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "45989730"
---
# <a name="bitwise-operators"></a><span data-ttu-id="ee293-103">位运算符</span><span class="sxs-lookup"><span data-stu-id="ee293-103">Bitwise Operators</span></span>

<span data-ttu-id="ee293-104">本主题介绍 F # 语言中提供的按位运算符。</span><span class="sxs-lookup"><span data-stu-id="ee293-104">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="ee293-105">按位运算符摘要</span><span class="sxs-lookup"><span data-stu-id="ee293-105">Summary of Bitwise Operators</span></span>

<span data-ttu-id="ee293-106">下表描述 F # 语言中的未装箱整型类型支持的按位运算符。</span><span class="sxs-lookup"><span data-stu-id="ee293-106">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="ee293-107">运算符</span><span class="sxs-lookup"><span data-stu-id="ee293-107">Operator</span></span>|<span data-ttu-id="ee293-108">说明</span><span class="sxs-lookup"><span data-stu-id="ee293-108">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="ee293-109">按位 AND 运算符。</span><span class="sxs-lookup"><span data-stu-id="ee293-109">Bitwise AND operator.</span></span> <span data-ttu-id="ee293-110">当且仅当在两个源操作数的相应位均为 1，结果中的位将具有值 1。</span><span class="sxs-lookup"><span data-stu-id="ee293-110">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="ee293-111">按位 OR 运算符。</span><span class="sxs-lookup"><span data-stu-id="ee293-111">Bitwise OR operator.</span></span> <span data-ttu-id="ee293-112">结果中的位具有值 1，如果任一操作数的源中的对应位是 1。</span><span class="sxs-lookup"><span data-stu-id="ee293-112">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="ee293-113">按位异或运算符。</span><span class="sxs-lookup"><span data-stu-id="ee293-113">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="ee293-114">当且仅当源操作数中的位具有不相等的值，结果中的位将具有值 1。</span><span class="sxs-lookup"><span data-stu-id="ee293-114">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="ee293-115">按位求反运算符。</span><span class="sxs-lookup"><span data-stu-id="ee293-115">Bitwise negation operator.</span></span> <span data-ttu-id="ee293-116">这是一个一元运算符，并生成的结果，在其中源操作数中的所有 0 位转换为 1 的位，且所有 1 的位转换为 0 位。</span><span class="sxs-lookup"><span data-stu-id="ee293-116">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="ee293-117">按位左移运算符。</span><span class="sxs-lookup"><span data-stu-id="ee293-117">Bitwise left-shift operator.</span></span> <span data-ttu-id="ee293-118">结果是第一个操作数中的位位数向左移动的第二个操作数中的位数。</span><span class="sxs-lookup"><span data-stu-id="ee293-118">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="ee293-119">移去最高有效位不会转入最低有效位。</span><span class="sxs-lookup"><span data-stu-id="ee293-119">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="ee293-120">最低有效位用零填充。</span><span class="sxs-lookup"><span data-stu-id="ee293-120">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="ee293-121">第二个参数的类型是`int32`。</span><span class="sxs-lookup"><span data-stu-id="ee293-121">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="ee293-122">按位右移运算符。</span><span class="sxs-lookup"><span data-stu-id="ee293-122">Bitwise right-shift operator.</span></span> <span data-ttu-id="ee293-123">结果是通过第二个操作数中的位数向右位移位的第一个操作数。</span><span class="sxs-lookup"><span data-stu-id="ee293-123">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="ee293-124">移去的最低有效位不会转入最高有效位。</span><span class="sxs-lookup"><span data-stu-id="ee293-124">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="ee293-125">对于无符号类型，最明显的位用零填充。</span><span class="sxs-lookup"><span data-stu-id="ee293-125">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="ee293-126">对于具有负值的有符号类型，与填充最高有效位。</span><span class="sxs-lookup"><span data-stu-id="ee293-126">For signed types with negative values, the most significant bits are padded with ones.</span></span> <span data-ttu-id="ee293-127">第二个参数的类型是`int32`。</span><span class="sxs-lookup"><span data-stu-id="ee293-127">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="ee293-128">与按位运算符可以使用以下类型： `byte`， `sbyte`， `int16`， `uint16`， `int32 (int)`， `uint32`， `int64`， `uint64`， `nativeint`，和`unativeint`。</span><span class="sxs-lookup"><span data-stu-id="ee293-128">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee293-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee293-129">See also</span></span>

- [<span data-ttu-id="ee293-130">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="ee293-130">Symbol and Operator Reference</span></span>](index.md)
- [<span data-ttu-id="ee293-131">算术运算符</span><span class="sxs-lookup"><span data-stu-id="ee293-131">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="ee293-132">布尔运算符</span><span class="sxs-lookup"><span data-stu-id="ee293-132">Boolean Operators</span></span>](boolean-operators.md)
