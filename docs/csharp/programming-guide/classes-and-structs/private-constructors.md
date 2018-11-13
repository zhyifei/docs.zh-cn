---
title: 私有构造函数（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 5b387447046e4755287fc9f6a8813a19752799c2
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "50980711"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="5fa32-102">私有构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5fa32-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="5fa32-103">私有构造函数是一种特殊的实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="5fa32-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="5fa32-104">它通常用于只包含静态成员的类中。</span><span class="sxs-lookup"><span data-stu-id="5fa32-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="5fa32-105">如果类具有一个或多个私有构造函数而没有公共构造函数，则其他类（除嵌套类外）无法创建该类的实例。</span><span class="sxs-lookup"><span data-stu-id="5fa32-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="5fa32-106">例如:</span><span class="sxs-lookup"><span data-stu-id="5fa32-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 <span data-ttu-id="5fa32-107">声明空构造函数可阻止自动生成默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="5fa32-107">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="5fa32-108">请注意，如果不对构造函数使用访问修饰符，则在默认情况下它仍为私有构造函数。</span><span class="sxs-lookup"><span data-stu-id="5fa32-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="5fa32-109">但是，通常会显式地使用 [private](../../../csharp/language-reference/keywords/private.md) 修饰符来清楚地表明该类不能被实例化。</span><span class="sxs-lookup"><span data-stu-id="5fa32-109">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="5fa32-110">当没有实例字段或实例方法（例如 <xref:System.Math> 类）时或者当调用方法以获得类的实例时，私有构造函数可用于阻止创建类的实例。</span><span class="sxs-lookup"><span data-stu-id="5fa32-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="5fa32-111">如果类中的所有方法都是静态的，可考虑使整个类成为静态的。</span><span class="sxs-lookup"><span data-stu-id="5fa32-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="5fa32-112">有关详细信息，请参阅[静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="5fa32-112">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fa32-113">示例</span><span class="sxs-lookup"><span data-stu-id="5fa32-113">Example</span></span>  
 <span data-ttu-id="5fa32-114">下面是使用私有构造函数的类的示例。</span><span class="sxs-lookup"><span data-stu-id="5fa32-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 <span data-ttu-id="5fa32-115">请注意，如果取消注释该示例中的以下语句，它将生成一个错误，因为该构造函数受其保护级别的限制而不可访问：</span><span class="sxs-lookup"><span data-stu-id="5fa32-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5fa32-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5fa32-116">C# Language Specification</span></span>  

<span data-ttu-id="5fa32-117">有关详细信息，请参阅 [C# 语言规范](../../language-reference/language-specification/index.md)中的[私有构造函数](~/_csharplang/spec/classes.md#private-constructors)。</span><span class="sxs-lookup"><span data-stu-id="5fa32-117">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="5fa32-118">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="5fa32-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5fa32-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa32-119">See Also</span></span>

- [<span data-ttu-id="5fa32-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5fa32-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5fa32-121">类和结构</span><span class="sxs-lookup"><span data-stu-id="5fa32-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="5fa32-122">构造函数</span><span class="sxs-lookup"><span data-stu-id="5fa32-122">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="5fa32-123">终结器</span><span class="sxs-lookup"><span data-stu-id="5fa32-123">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [<span data-ttu-id="5fa32-124">private</span><span class="sxs-lookup"><span data-stu-id="5fa32-124">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="5fa32-125">public</span><span class="sxs-lookup"><span data-stu-id="5fa32-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)
