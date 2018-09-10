---
title: 接口属性（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: eea2bb524496a3db22146586df323437d9f84242
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43396726"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="3f173-102">接口属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3f173-102">Interface Properties (C# Programming Guide)</span></span>
<span data-ttu-id="3f173-103">可以在[接口](../../../csharp/language-reference/keywords/interface.md)上声明属性。</span><span class="sxs-lookup"><span data-stu-id="3f173-103">Properties can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="3f173-104">下面是接口属性访问器的示例：</span><span class="sxs-lookup"><span data-stu-id="3f173-104">The following is an example of an interface property accessor:</span></span>  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 <span data-ttu-id="3f173-105">接口属性的访问器没有正文。</span><span class="sxs-lookup"><span data-stu-id="3f173-105">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="3f173-106">因此，访问器的用途是指示属性为读写、只读还是只写。</span><span class="sxs-lookup"><span data-stu-id="3f173-106">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f173-107">示例</span><span class="sxs-lookup"><span data-stu-id="3f173-107">Example</span></span>  
 <span data-ttu-id="3f173-108">在此示例中，接口 `IEmployee` 具有读写属性 `Name` 和只读属性 `Counter`。</span><span class="sxs-lookup"><span data-stu-id="3f173-108">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="3f173-109">类 `Employee` 实现 `IEmployee` 接口，并使用这两个属性。</span><span class="sxs-lookup"><span data-stu-id="3f173-109">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="3f173-110">程序读取新员工的姓名以及当前员工数，并显示员工名称和计算的员工数。</span><span class="sxs-lookup"><span data-stu-id="3f173-110">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>  
  
 <span data-ttu-id="3f173-111">可以使用属性的完全限定名称，它引用其中声明成员的接口。</span><span class="sxs-lookup"><span data-stu-id="3f173-111">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="3f173-112">例如:</span><span class="sxs-lookup"><span data-stu-id="3f173-112">For example:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 <span data-ttu-id="3f173-113">这称为[显式接口实现](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="3f173-113">This is called [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="3f173-114">例如，如果 `Employee` 类正在实现接口 `ICitizen` 和接口 `IEmployee`，而这两个接口都具有 `Name` 属性，则需要用到显式接口成员实现。</span><span class="sxs-lookup"><span data-stu-id="3f173-114">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="3f173-115">即是说下列属性声明：</span><span class="sxs-lookup"><span data-stu-id="3f173-115">That is, the following property declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 <span data-ttu-id="3f173-116">在 `IEmployee` 接口中实现 `Name` 属性，而以下声明：</span><span class="sxs-lookup"><span data-stu-id="3f173-116">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 <span data-ttu-id="3f173-117">在 `ICitizen` 接口中实现 `Name` 属性。</span><span class="sxs-lookup"><span data-stu-id="3f173-117">implements the `Name` property on the `ICitizen` interface.</span></span>  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a><span data-ttu-id="3f173-118">示例输出</span><span class="sxs-lookup"><span data-stu-id="3f173-118">Sample Output</span></span>  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a><span data-ttu-id="3f173-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f173-119">See Also</span></span>  
 [<span data-ttu-id="3f173-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3f173-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3f173-121">属性</span><span class="sxs-lookup"><span data-stu-id="3f173-121">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="3f173-122">使用属性</span><span class="sxs-lookup"><span data-stu-id="3f173-122">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [<span data-ttu-id="3f173-123">属性与索引器之间的比较</span><span class="sxs-lookup"><span data-stu-id="3f173-123">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
 [<span data-ttu-id="3f173-124">索引器</span><span class="sxs-lookup"><span data-stu-id="3f173-124">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="3f173-125">接口</span><span class="sxs-lookup"><span data-stu-id="3f173-125">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
