---
title: C++ 模板和 C# 泛型之间的区别（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], vs. C++ templates
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
ms.openlocfilehash: eef2fc5919f405b75be7ae2a2069b1e7cf8a45a7
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44088071"
---
# <a name="differences-between-c-templates-and-c-generics-c-programming-guide"></a><span data-ttu-id="57741-102">C++ 模板和 C# 泛型之间的区别（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="57741-102">Differences Between C++ Templates and C# Generics (C# Programming Guide)</span></span>
<span data-ttu-id="57741-103">C# 泛型和 C++ 模板均是支持参数化类型的语言功能。</span><span class="sxs-lookup"><span data-stu-id="57741-103">C# Generics and C++ templates are both language features that provide support for parameterized types.</span></span> <span data-ttu-id="57741-104">但是，两者之间存在很多不同。</span><span class="sxs-lookup"><span data-stu-id="57741-104">However, there are many differences between the two.</span></span> <span data-ttu-id="57741-105">在语法层次，C# 泛型是参数化类型的一个更简单的方法，而不具有 C++ 模板的复杂性。</span><span class="sxs-lookup"><span data-stu-id="57741-105">At the syntax level, C# generics are a simpler approach to parameterized types without the complexity of C++ templates.</span></span> <span data-ttu-id="57741-106">此外，C# 不试图提供  C++ 模板所具有的所有功能。</span><span class="sxs-lookup"><span data-stu-id="57741-106">In addition, C# does not attempt to provide all of the functionality that C++ templates provide.</span></span> <span data-ttu-id="57741-107">在实现层次，主要区别在于 C# 泛型类型的替换在运行时执行，从而为实例化对象保留了泛型类型信息。</span><span class="sxs-lookup"><span data-stu-id="57741-107">At the implementation level, the primary difference is that C# generic type substitutions are performed at runtime and generic type information is thereby preserved for instantiated objects.</span></span> <span data-ttu-id="57741-108">有关详细信息，请参阅[运行时中的泛型](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)。</span><span class="sxs-lookup"><span data-stu-id="57741-108">For more information, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
 <span data-ttu-id="57741-109">以下是 C# 泛型和 C++ 模板之间的主要差异：</span><span class="sxs-lookup"><span data-stu-id="57741-109">The following are the key differences between C# Generics and C++ templates:</span></span>  
  
-   <span data-ttu-id="57741-110">C# 泛型的灵活性与 C++ 模板不同。</span><span class="sxs-lookup"><span data-stu-id="57741-110">C# generics do not provide the same amount of flexibility as C++ templates.</span></span> <span data-ttu-id="57741-111">例如，虽然可以调用 C# 泛型类中的用户定义的运算符，但是无法调用算术运算符。</span><span class="sxs-lookup"><span data-stu-id="57741-111">For example, it is not possible to call arithmetic operators in a C# generic class, although it is possible to call user defined operators.</span></span>  
  
-   <span data-ttu-id="57741-112">C# 不允许使用非类型模板参数，如 `template C<int i> {}`。</span><span class="sxs-lookup"><span data-stu-id="57741-112">C# does not allow non-type template parameters, such as `template C<int i> {}`.</span></span>  
  
-   <span data-ttu-id="57741-113">C# 不支持显式定制化；即特定类型模板的自定义实现。</span><span class="sxs-lookup"><span data-stu-id="57741-113">C# does not support explicit specialization; that is, a custom implementation of a template for a specific type.</span></span>  
  
-   <span data-ttu-id="57741-114">C# 不支持部分定制化：部分类型参数的自定义实现。</span><span class="sxs-lookup"><span data-stu-id="57741-114">C# does not support partial specialization: a custom implementation for a subset of the type arguments.</span></span>  
  
-   <span data-ttu-id="57741-115">C# 不允许将类型参数用作泛型类型的基类。</span><span class="sxs-lookup"><span data-stu-id="57741-115">C# does not allow the type parameter to be used as the base class for the generic type.</span></span>  
  
-   <span data-ttu-id="57741-116">C# 不允许类型参数具有默认类型。</span><span class="sxs-lookup"><span data-stu-id="57741-116">C# does not allow type parameters to have default types.</span></span>  
  
-   <span data-ttu-id="57741-117">在 C# 中，泛型类型参数本身不能是泛型，但是构造类型可以用作泛型。</span><span class="sxs-lookup"><span data-stu-id="57741-117">In C#, a generic type parameter cannot itself be a generic, although constructed types can be used as generics.</span></span> <span data-ttu-id="57741-118">C++ 允许使用模板参数。</span><span class="sxs-lookup"><span data-stu-id="57741-118">C++ does allow template parameters.</span></span>  
  
-   <span data-ttu-id="57741-119">C++ 允许在模板中使用可能并非对所有类型参数有效的代码，随后针对用作类型参数的特定类型检查此代码。</span><span class="sxs-lookup"><span data-stu-id="57741-119">C++ allows code that might not be valid for all type parameters in the template, which is then checked for the specific type used as the type parameter.</span></span> <span data-ttu-id="57741-120">C# 要求类中编写的代码可处理满足约束的任何类型。</span><span class="sxs-lookup"><span data-stu-id="57741-120">C# requires code in a class to be written in such a way that it will work with any type that satisfies the constraints.</span></span> <span data-ttu-id="57741-121">例如，在 C++ 中可以编写一个函数，此函数对类型参数的对象使用算术运算符 `+` 和 `-`，在实例化具有不支持这些运算符的类型的模板时，此函数将产生错误。</span><span class="sxs-lookup"><span data-stu-id="57741-121">For example, in C++ it is possible to write a function that uses the arithmetic operators `+` and `-` on objects of the type parameter, which will produce an error at the time of instantiation of the template with a type that does not support these operators.</span></span> <span data-ttu-id="57741-122">C# 不允许此操作；唯一允许的语言构造是可以从约束中推断出来的构造。</span><span class="sxs-lookup"><span data-stu-id="57741-122">C# disallows this; the only language constructs allowed are those that can be deduced from the constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57741-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="57741-123">See Also</span></span>

- [<span data-ttu-id="57741-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="57741-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="57741-125">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="57741-125">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
- [<span data-ttu-id="57741-126">模板</span><span class="sxs-lookup"><span data-stu-id="57741-126">Templates</span></span>](/cpp/cpp/templates-cpp)
