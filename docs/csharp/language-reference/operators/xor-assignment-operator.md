---
title: ^= 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 12189d6469a9716d3b7ebcffef23423a75692d1a
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333546"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f6c5f-102">^= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f6c5f-102">^= operator (C# Reference)</span></span>

<span data-ttu-id="f6c5f-103">异或赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="f6c5f-103">The exclusive-OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6c5f-104">备注</span><span class="sxs-lookup"><span data-stu-id="f6c5f-104">Remarks</span></span>

<span data-ttu-id="f6c5f-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="f6c5f-105">An expression of the form</span></span>

```csharp
x ^= y
```

<span data-ttu-id="f6c5f-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="f6c5f-106">is evaluated as</span></span>

```csharp
x = x ^ y
```

<span data-ttu-id="f6c5f-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="f6c5f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="f6c5f-108">[^ 运算符](xor-operator.md) 对整型操作数执行按位异或运算，对 [bool](../keywords/bool.md) 操作数执行逻辑异或运算。</span><span class="sxs-lookup"><span data-stu-id="f6c5f-108">The [^ operator](xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="f6c5f-109">不能直接重载 ^= 运算符，但用户定义的类型可重载 [^ 运算符](xor-operator.md)（请参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="f6c5f-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](xor-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="f6c5f-110">示例</span><span class="sxs-lookup"><span data-stu-id="f6c5f-110">Example</span></span>

[!code-csharp[csRefOperators#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#23)]

## <a name="see-also"></a><span data-ttu-id="f6c5f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6c5f-111">See also</span></span>

- [<span data-ttu-id="f6c5f-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f6c5f-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f6c5f-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f6c5f-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f6c5f-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="f6c5f-114">C# operators</span></span>](index.md)