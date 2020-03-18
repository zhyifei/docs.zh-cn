---
title: 专用构造函数 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 2f8b93fbeb7c2996f3e2683fe86f159fbfa61a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705439"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="7316c-102">私有构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="7316c-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="7316c-103">私有构造函数是一种特殊的实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="7316c-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="7316c-104">它通常用于只包含静态成员的类中。</span><span class="sxs-lookup"><span data-stu-id="7316c-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="7316c-105">如果类具有一个或多个私有构造函数而没有公共构造函数，则其他类（除嵌套类外）无法创建该类的实例。</span><span class="sxs-lookup"><span data-stu-id="7316c-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="7316c-106">例如:</span><span class="sxs-lookup"><span data-stu-id="7316c-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="7316c-107">声明空构造函数可阻止自动生成无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="7316c-107">The declaration of the empty constructor prevents the automatic generation of a parameterless constructor.</span></span> <span data-ttu-id="7316c-108">请注意，如果不对构造函数使用访问修饰符，则在默认情况下它仍为私有构造函数。</span><span class="sxs-lookup"><span data-stu-id="7316c-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="7316c-109">但是，通常会显式地使用 [private](../../language-reference/keywords/private.md) 修饰符来清楚地表明该类不能被实例化。</span><span class="sxs-lookup"><span data-stu-id="7316c-109">However, the [private](../../language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="7316c-110">当没有实例字段或实例方法（例如 <xref:System.Math> 类）时或者当调用方法以获得类的实例时，私有构造函数可用于阻止创建类的实例。</span><span class="sxs-lookup"><span data-stu-id="7316c-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="7316c-111">如果类中的所有方法都是静态的，可考虑使整个类成为静态的。</span><span class="sxs-lookup"><span data-stu-id="7316c-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="7316c-112">有关详细信息，请参阅[静态类和静态类成员](./static-classes-and-static-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="7316c-112">For more information see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7316c-113">示例</span><span class="sxs-lookup"><span data-stu-id="7316c-113">Example</span></span>  
 <span data-ttu-id="7316c-114">下面是使用私有构造函数的类的示例。</span><span class="sxs-lookup"><span data-stu-id="7316c-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 <span data-ttu-id="7316c-115">请注意，如果取消注释该示例中的以下语句，它将生成一个错误，因为该构造函数受其保护级别的限制而不可访问：</span><span class="sxs-lookup"><span data-stu-id="7316c-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="7316c-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="7316c-116">C# Language Specification</span></span>  

<span data-ttu-id="7316c-117">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/classes.md#private-constructors)中的[私有构造函数](/dotnet/csharp/language-reference/language-specification/introduction)。</span><span class="sxs-lookup"><span data-stu-id="7316c-117">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="7316c-118">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="7316c-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7316c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7316c-119">See also</span></span>

- [<span data-ttu-id="7316c-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7316c-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7316c-121">类和结构</span><span class="sxs-lookup"><span data-stu-id="7316c-121">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="7316c-122">构造函数</span><span class="sxs-lookup"><span data-stu-id="7316c-122">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="7316c-123">终结器</span><span class="sxs-lookup"><span data-stu-id="7316c-123">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="7316c-124">private</span><span class="sxs-lookup"><span data-stu-id="7316c-124">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="7316c-125">public</span><span class="sxs-lookup"><span data-stu-id="7316c-125">public</span></span>](../../language-reference/keywords/public.md)
