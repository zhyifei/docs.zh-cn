---
title: "如何：使用 as 和 is 运算符安全地进行强制转换（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c5daa8525f45c123dabb0f59dfd29385b9e50354
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a><span data-ttu-id="a4201-102">如何：使用 as 和 is 运算符安全地进行强制转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a4201-102">How to: Safely Cast by Using as and is Operators (C# Programming Guide)</span></span>
<span data-ttu-id="a4201-103">由于是多态对象，基类类型的变量可以保存派生类型。</span><span class="sxs-lookup"><span data-stu-id="a4201-103">Because objects are polymorphic, it is possible for a variable of a base class type to hold a derived type.</span></span> <span data-ttu-id="a4201-104">若要访问派生类型的方法，必须将值强制转换回派生类型。</span><span class="sxs-lookup"><span data-stu-id="a4201-104">To access the derived type's method, it is necessary to cast the value back to the derived type.</span></span> <span data-ttu-id="a4201-105">但是，在这些情况下尝试简单的强制转换会产生引发 <xref:System.InvalidCastException> 的风险。</span><span class="sxs-lookup"><span data-stu-id="a4201-105">However, to attempt a simple cast in these cases creates the risk of throwing an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="a4201-106">这就是 C# 提供 [is](../../../csharp/language-reference/keywords/is.md) 和 [as](../../../csharp/language-reference/keywords/as.md) 运算符的原因。</span><span class="sxs-lookup"><span data-stu-id="a4201-106">That is why C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators.</span></span> <span data-ttu-id="a4201-107">这些运算符可用于测试强制转换是否会成功且不引发异常。</span><span class="sxs-lookup"><span data-stu-id="a4201-107">You can use these operators to test whether a cast will succeed without causing an exception to be thrown.</span></span> <span data-ttu-id="a4201-108">一般情况下，`as` 运算符更高效，因为如果可以成功执行强制转换，实际上它会返回强制转换值。</span><span class="sxs-lookup"><span data-stu-id="a4201-108">In general, the `as` operator is more efficient because it actually returns the cast value if the cast can be made successfully.</span></span> <span data-ttu-id="a4201-109">`is` 运算符只返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="a4201-109">The `is` operator returns only a Boolean value.</span></span> <span data-ttu-id="a4201-110">因此，可以在只需确定对象类型，无需实际强制转换时使用。</span><span class="sxs-lookup"><span data-stu-id="a4201-110">It can therefore be used when you just want to determine an object's type but do not have to actually cast it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4201-111">示例</span><span class="sxs-lookup"><span data-stu-id="a4201-111">Example</span></span>  
 <span data-ttu-id="a4201-112">以下示例演示如何使用 `is` 和 `as` 运算符将一种引用类型强制转换为另一种引用类型，且无引发异常的风险。</span><span class="sxs-lookup"><span data-stu-id="a4201-112">The following examples show how to use the `is` and `as` operators to cast from one reference type to another without the risk of throwing an exception.</span></span> <span data-ttu-id="a4201-113">该示例还演示如何将 `as` 运算符用于可以为 null 的值类型。</span><span class="sxs-lookup"><span data-stu-id="a4201-113">The example also shows how to use the `as` operator with nullable value types.</span></span>  
  
 <span data-ttu-id="a4201-114">[!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4201-114">[!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4201-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4201-115">See Also</span></span>  
 <span data-ttu-id="a4201-116">[类型](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4201-116">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="a4201-117">[强制转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="a4201-117">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 [<span data-ttu-id="a4201-118">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="a4201-118">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)

