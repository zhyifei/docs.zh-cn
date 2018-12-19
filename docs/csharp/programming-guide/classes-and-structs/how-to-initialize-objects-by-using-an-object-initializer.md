---
title: 如何：使用对象初始值设定项初始化对象 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 82efa751ad70fd2741ec2e306f56f2be06abad11
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244983"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="23e42-102">如何：使用对象初始值设定项初始化对象（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="23e42-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="23e42-103">可以使用对象初始值设定项以声明方式初始化类型对象，而无需显式调用类型的构造函数。</span><span class="sxs-lookup"><span data-stu-id="23e42-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
 <span data-ttu-id="23e42-104">以下示例演示如何将对象初始值设定项用于命名对象。</span><span class="sxs-lookup"><span data-stu-id="23e42-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="23e42-105">编译器通过首先访问默认实例构造函数，然后处理成员初始化来处理对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="23e42-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="23e42-106">因此，如果默认构造函数在类中声明为 `private`，则需要公共访问的对象初始值设定项将失败。</span><span class="sxs-lookup"><span data-stu-id="23e42-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>  
  
 <span data-ttu-id="23e42-107">如果要定义匿名类型，则必须使用对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="23e42-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="23e42-108">有关更多信息，请参见[如何：在查询中返回元素属性的子集](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md)。</span><span class="sxs-lookup"><span data-stu-id="23e42-108">For more information, see [How to: Return Subsets of Element Properties in a Query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23e42-109">示例</span><span class="sxs-lookup"><span data-stu-id="23e42-109">Example</span></span>  
 <span data-ttu-id="23e42-110">下面的示例演示如何使用对象初始值设定项初始化新的 `StudentName` 类型。</span><span class="sxs-lookup"><span data-stu-id="23e42-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="23e42-111">示例</span><span class="sxs-lookup"><span data-stu-id="23e42-111">Example</span></span>  
 <span data-ttu-id="23e42-112">下面的示例演示如何使用集合初始值设定项来初始化 `StudentName` 类型的集合。</span><span class="sxs-lookup"><span data-stu-id="23e42-112">The following example shows how to initialize a collection of `StudentName` types by using a collection initializer.</span></span> <span data-ttu-id="23e42-113">请注意，集合初始值设定项是一系列由逗号分隔的对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="23e42-113">Note that a collection initializer is a series of comma-separated object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="23e42-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="23e42-114">Compiling the Code</span></span>  
 <span data-ttu-id="23e42-115">若要运行此代码，请将该类复制并粘贴到已在 Visual Studio 中创建的 Visual C# 控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="23e42-115">To run this code, copy and paste the class into a Visual C# console application project that has been created in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e42-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="23e42-116">See Also</span></span>

- [<span data-ttu-id="23e42-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="23e42-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="23e42-118">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="23e42-118">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
