---
title: 如何：定义抽象属性（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: 549867cac99784ce885b8fce8a1638c40ad88cec
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46002978"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="d2715-102">如何：定义抽象属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="d2715-102">How to: Define Abstract Properties (C# Programming Guide)</span></span>
<span data-ttu-id="d2715-103">以下示例演示如何定义[抽象](../../../csharp/language-reference/keywords/abstract.md)属性。</span><span class="sxs-lookup"><span data-stu-id="d2715-103">The following example shows how to define [abstract](../../../csharp/language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="d2715-104">抽象属性声明不提供属性访问器的实现，它声明该类支持属性，而将访问器实现留给派生类。</span><span class="sxs-lookup"><span data-stu-id="d2715-104">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="d2715-105">以下示例演示如何实现从基类继承抽象属性。</span><span class="sxs-lookup"><span data-stu-id="d2715-105">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="d2715-106">此示例由三个文件组成，其中每个文件都单独编译，产生的程序集由下一次编译引用：</span><span class="sxs-lookup"><span data-stu-id="d2715-106">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
-   <span data-ttu-id="d2715-107">abstractshape.cs：包含抽象 `Area` 属性的 `Shape` 类。</span><span class="sxs-lookup"><span data-stu-id="d2715-107">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
-   <span data-ttu-id="d2715-108">shapes.cs： `Shape` 类的子类。</span><span class="sxs-lookup"><span data-stu-id="d2715-108">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
-   <span data-ttu-id="d2715-109">shapetest.cs：测试程序，用于显示某些 `Shape` 派生对象的区域。</span><span class="sxs-lookup"><span data-stu-id="d2715-109">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="d2715-110">若要编译该示例，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="d2715-110">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="d2715-111">这将创建可执行文件 shapetest.exe。</span><span class="sxs-lookup"><span data-stu-id="d2715-111">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2715-112">示例</span><span class="sxs-lookup"><span data-stu-id="d2715-112">Example</span></span>  
 <span data-ttu-id="d2715-113">此文件声明 `Shape` 类，该类包含 `double` 类型的 `Area` 属性。</span><span class="sxs-lookup"><span data-stu-id="d2715-113">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_1.cs)]  
  
-   <span data-ttu-id="d2715-114">属性的修饰符放置在属性声明中。</span><span class="sxs-lookup"><span data-stu-id="d2715-114">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="d2715-115">例如:</span><span class="sxs-lookup"><span data-stu-id="d2715-115">For example:</span></span>  
  
    ```csharp  
    public abstract double Area  
    ```  
  
-   <span data-ttu-id="d2715-116">声明抽象属性时（如本示例中的 `Area`），只需指明哪些属性访问器可用即可，不要实现它们。</span><span class="sxs-lookup"><span data-stu-id="d2715-116">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="d2715-117">在此示例中，仅 [get](../../../csharp/language-reference/keywords/get.md) 访问器可用，因此该属性是只读属性。</span><span class="sxs-lookup"><span data-stu-id="d2715-117">In this example, only a [get](../../../csharp/language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2715-118">示例</span><span class="sxs-lookup"><span data-stu-id="d2715-118">Example</span></span>  
 <span data-ttu-id="d2715-119">下面的代码演示 `Shape` 的三个子类，并演示它们如何替代 `Area` 属性来提供自己的实现。</span><span class="sxs-lookup"><span data-stu-id="d2715-119">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="d2715-120">示例</span><span class="sxs-lookup"><span data-stu-id="d2715-120">Example</span></span>  
 <span data-ttu-id="d2715-121">下面的代码演示一个创建若干 `Shape` 派生对象并输出其区域的测试程序。</span><span class="sxs-lookup"><span data-stu-id="d2715-121">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d2715-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2715-122">See Also</span></span>

- [<span data-ttu-id="d2715-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d2715-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d2715-124">类和结构</span><span class="sxs-lookup"><span data-stu-id="d2715-124">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="d2715-125">抽象类、密封类及类成员</span><span class="sxs-lookup"><span data-stu-id="d2715-125">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
- [<span data-ttu-id="d2715-126">属性</span><span class="sxs-lookup"><span data-stu-id="d2715-126">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [<span data-ttu-id="d2715-127">如何：使用命令行创建和使用程序集</span><span class="sxs-lookup"><span data-stu-id="d2715-127">How to: Create and Use Assemblies Using the Command Line</span></span>](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
