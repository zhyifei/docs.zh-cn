---
title: 运算符关键字 - C# 参考
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- keywords [C#], operators
- operators [C#], keywords
ms.assetid: f745c81f-f8d8-4673-86a1-0f3a85cc63c3
ms.openlocfilehash: e03e1c930b452cf5e4f2c4bb1d06d5363f20c991
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243591"
---
# <a name="operator-keywords-c-reference"></a><span data-ttu-id="7bb4f-102">运算符关键字（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7bb4f-102">Operator Keywords (C# Reference)</span></span>

<span data-ttu-id="7bb4f-103">用于执行其他操作，例如创建对象、检查对象的运行时类型、获取类型的大小等等。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-103">Used to perform miscellaneous actions such as creating objects, checking the run-time type of an object, obtaining the size of a type, and other actions.</span></span> <span data-ttu-id="7bb4f-104">本部分介绍以下关键字：</span><span class="sxs-lookup"><span data-stu-id="7bb4f-104">This section introduces the following keywords:</span></span>

- <span data-ttu-id="7bb4f-105">[as](as.md) 将对象转换为兼容类型。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-105">[as](as.md) Converts an object to a compatible type.</span></span>

- <span data-ttu-id="7bb4f-106">[await](await.md) 暂停 [async](async.md) 方法，直到等待的任务已完成。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-106">[await](await.md) Suspends an [async](async.md) method until an awaited task is completed.</span></span>

- <span data-ttu-id="7bb4f-107">[is](is.md) 检查对象的运行时类型，或（自 C# 7.0 起）根据模式测试表达式。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-107">[is](is.md) Checks the run-time type of an object, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

- [<span data-ttu-id="7bb4f-108">new</span><span class="sxs-lookup"><span data-stu-id="7bb4f-108">new</span></span>](new.md)

  - <span data-ttu-id="7bb4f-109">[new 运算符](new-operator.md) 创建对象。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-109">[new Operator](new-operator.md) Creates objects.</span></span>

  - <span data-ttu-id="7bb4f-110">[new 修饰符](new-modifier.md) 隐藏继承的成员。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-110">[new Modifier](new-modifier.md) Hides an inherited member.</span></span>

  - <span data-ttu-id="7bb4f-111">[new 约束](new-constraint.md) 限定类型参数。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-111">[new Constraint](new-constraint.md) Qualifies a type parameter.</span></span>

- <span data-ttu-id="7bb4f-112">[nameof](nameof.md) 获取变量、类型或成员的简单（非限定）字符串名称。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-112">[nameof](nameof.md) Obtains the simple (unqualified) string name of a variable, type, or member.</span></span>

- <span data-ttu-id="7bb4f-113">[sizeof](sizeof.md) 获取非托管类型的大小。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-113">[sizeof](sizeof.md) Obtains the size of an unmanaged type.</span></span>  

- <span data-ttu-id="7bb4f-114">[typeof](typeof.md) 获取类型的 <xref:System.Type?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-114">[typeof](typeof.md) Obtains the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span>  

- [<span data-ttu-id="7bb4f-115">true</span><span class="sxs-lookup"><span data-stu-id="7bb4f-115">true</span></span>](true.md)  

  - <span data-ttu-id="7bb4f-116">[true 运算符](true-false-operators.md)返回 [bool](bool.md) 值 `true` 以指示操作数一定为 true。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-116">[true Operator](true-false-operators.md) Returns the [bool](bool.md) value `true` to indicate that the operand is definitely true.</span></span>

  - <span data-ttu-id="7bb4f-117">[true 字面常数](true-literal.md)表示 [bool](bool.md) 值 `true`。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-117">[true Literal](true-literal.md) Represents the [bool](bool.md) value `true`.</span></span>

- [<span data-ttu-id="7bb4f-118">false</span><span class="sxs-lookup"><span data-stu-id="7bb4f-118">false</span></span>](false.md)  

  - <span data-ttu-id="7bb4f-119">[false 运算符](true-false-operators.md)返回 [bool](bool.md) 值 `true`，以指明操作数一定为 false。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-119">[false Operator](true-false-operators.md) Returns the [bool](bool.md) value `true` to indicate that the operand is definitely false.</span></span>

  - <span data-ttu-id="7bb4f-120">[false 文本](false-literal.md)表示 [bool](bool.md) 值 `false`。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-120">[false Literal](false-literal.md) Represents the [bool](bool.md) value `false`.</span></span>

- <span data-ttu-id="7bb4f-121">[stackalloc](stackalloc.md) 在堆栈上分配内存块。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-121">[stackalloc](stackalloc.md) Allocates a block of memory on the stack.</span></span>  

<span data-ttu-id="7bb4f-122">以下关键字可以用作运算符和语句，详见[语句](statement-keywords.md)部分：</span><span class="sxs-lookup"><span data-stu-id="7bb4f-122">The following keywords, which can be used as operators and as statements, are covered in the [Statements](statement-keywords.md) section:</span></span>

- <span data-ttu-id="7bb4f-123">[checked](checked.md) 指定已检查的上下文。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-123">[checked](checked.md) Specifies checked context.</span></span>  

- <span data-ttu-id="7bb4f-124">[unchecked](unchecked.md) 指定未检查的上下文。</span><span class="sxs-lookup"><span data-stu-id="7bb4f-124">[unchecked](unchecked.md) Specifies unchecked context.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7bb4f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7bb4f-125">See also</span></span>

- [<span data-ttu-id="7bb4f-126">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7bb4f-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7bb4f-127">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7bb4f-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7bb4f-128">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="7bb4f-128">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7bb4f-129">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="7bb4f-129">C# Operators</span></span>](../operators/index.md)
