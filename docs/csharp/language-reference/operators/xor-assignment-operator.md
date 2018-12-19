---
title: ^= 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: cf39c8e8586e9d4f537fe38d8b28f55542db6ab8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237150"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c4648-102">^= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c4648-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="c4648-103">异或赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="c4648-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4648-104">备注</span><span class="sxs-lookup"><span data-stu-id="c4648-104">Remarks</span></span>  
 <span data-ttu-id="c4648-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="c4648-105">An expression of the form</span></span>  
  
```csharp  
x ^= y  
```  
  
 <span data-ttu-id="c4648-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="c4648-106">is evaluated as</span></span>  
  
```csharp  
x = x ^ y  
```  
  
 <span data-ttu-id="c4648-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="c4648-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="c4648-108">[^ 运算符](../../../csharp/language-reference/operators/xor-operator.md) 对整型操作数执行按位异或运算，对 [bool](../../../csharp/language-reference/keywords/bool.md) 操作数执行逻辑异或运算。</span><span class="sxs-lookup"><span data-stu-id="c4648-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="c4648-109">不能直接重载 ^= 运算符，但用户定义的类型可重载 [^ 运算符](../../../csharp/language-reference/operators/xor-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="c4648-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4648-110">示例</span><span class="sxs-lookup"><span data-stu-id="c4648-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c4648-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4648-111">See Also</span></span>

- [<span data-ttu-id="c4648-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c4648-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="c4648-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c4648-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c4648-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c4648-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
