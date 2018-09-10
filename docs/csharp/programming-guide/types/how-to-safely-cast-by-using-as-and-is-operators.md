---
title: 如何：使用 as 和 is 运算符安全地进行强制转换（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
ms.openlocfilehash: 8e0b17122bd23a7de82ca1c210a559fe09ad7fee
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508113"
---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a><span data-ttu-id="bcdd4-102">如何：使用 as 和 is 运算符安全地进行强制转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="bcdd4-102">How to: Safely Cast by Using as and is Operators (C# Programming Guide)</span></span>
<span data-ttu-id="bcdd4-103">由于是多态对象，基类类型的变量可以保存派生类型。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-103">Because objects are polymorphic, it is possible for a variable of a base class type to hold a derived type.</span></span> <span data-ttu-id="bcdd4-104">若要访问派生类型的实例方法，必须将值强制转换回派生类型。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-104">To access the derived type's instance methods, it is necessary to cast the value back to the derived type.</span></span> <span data-ttu-id="bcdd4-105">但是，在这些情况下尝试简单的强制转换会产生引发 <xref:System.InvalidCastException> 的风险。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-105">However, to attempt a simple cast in these cases creates the risk of throwing an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="bcdd4-106">这就是 C# 提供 [is](../../../csharp/language-reference/keywords/is.md) 和 [as](../../../csharp/language-reference/keywords/as.md) 运算符的原因。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-106">That is why C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators.</span></span> <span data-ttu-id="bcdd4-107">这些运算符可用于测试强制转换是否会成功且不引发异常。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-107">You can use these operators to test whether a cast will succeed without causing an exception to be thrown.</span></span> <span data-ttu-id="bcdd4-108">一般情况下，`as` 运算符更高效，因为如果可以成功执行强制转换，实际上它会返回强制转换值。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-108">In general, the `as` operator is more efficient because it actually returns the cast value if the cast can be made successfully.</span></span> <span data-ttu-id="bcdd4-109">`is` 运算符只返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-109">The `is` operator returns only a Boolean value.</span></span> <span data-ttu-id="bcdd4-110">因此，可以在只需确定对象类型，无需实际强制转换时使用。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-110">It can therefore be used when you just want to determine an object's type but do not have to actually cast it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcdd4-111">示例</span><span class="sxs-lookup"><span data-stu-id="bcdd4-111">Example</span></span>  
 <span data-ttu-id="bcdd4-112">以下示例演示如何使用 `is` 和 `as` 运算符将一种引用类型强制转换为另一种引用类型，且无引发异常的风险。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-112">The following examples show how to use the `is` and `as` operators to cast from one reference type to another without the risk of throwing an exception.</span></span> <span data-ttu-id="bcdd4-113">该示例还演示如何将 `as` 运算符用于可以为 null 的值类型。</span><span class="sxs-lookup"><span data-stu-id="bcdd4-113">The example also shows how to use the `as` operator with nullable value types.</span></span>  
  
 [!code-csharp[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="bcdd4-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcdd4-114">See Also</span></span>

- [<span data-ttu-id="bcdd4-115">类型</span><span class="sxs-lookup"><span data-stu-id="bcdd4-115">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
- [<span data-ttu-id="bcdd4-116">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="bcdd4-116">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
- [<span data-ttu-id="bcdd4-117">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="bcdd4-117">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)
