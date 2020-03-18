---
title: 接口属性 - C# 编程指南
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 5798b80526f34e923e2eaab43847b98f6c64e14b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626615"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="00fa8-102">接口属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="00fa8-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="00fa8-103">可以在[接口](../../language-reference/keywords/interface.md)上声明属性。</span><span class="sxs-lookup"><span data-stu-id="00fa8-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="00fa8-104">下面的示例声明一个接口属性访问器：</span><span class="sxs-lookup"><span data-stu-id="00fa8-104">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="00fa8-105">接口属性通常没有主体。</span><span class="sxs-lookup"><span data-stu-id="00fa8-105">Interface properties typically don't have a body.</span></span> <span data-ttu-id="00fa8-106">访问器指示属性是读写、只读还是只写。</span><span class="sxs-lookup"><span data-stu-id="00fa8-106">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="00fa8-107">与在类和结构中不同，在没有主体的情况下声明访问器不会声明[自动实现的属性](auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="00fa8-107">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="00fa8-108">从 C# 8.0 开始，接口可为成员（包括属性）定义默认实现。</span><span class="sxs-lookup"><span data-stu-id="00fa8-108">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="00fa8-109">在接口中为属性定义默认实现的情况非常少，因为接口可能不会定义实例数据字段。</span><span class="sxs-lookup"><span data-stu-id="00fa8-109">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="00fa8-110">示例</span><span class="sxs-lookup"><span data-stu-id="00fa8-110">Example</span></span>

<span data-ttu-id="00fa8-111">在此示例中，接口 `IEmployee` 具有读写属性 `Name` 和只读属性 `Counter`。</span><span class="sxs-lookup"><span data-stu-id="00fa8-111">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="00fa8-112">类 `Employee` 实现 `IEmployee` 接口，并使用这两个属性。</span><span class="sxs-lookup"><span data-stu-id="00fa8-112">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="00fa8-113">程序读取新员工的姓名以及当前员工数，并显示员工名称和计算的员工数。</span><span class="sxs-lookup"><span data-stu-id="00fa8-113">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="00fa8-114">可以使用属性的完全限定名称，它引用其中声明成员的接口。</span><span class="sxs-lookup"><span data-stu-id="00fa8-114">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="00fa8-115">例如：</span><span class="sxs-lookup"><span data-stu-id="00fa8-115">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="00fa8-116">前面的示例演示了如何[显式接口实现](../interfaces/explicit-interface-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="00fa8-116">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="00fa8-117">例如，如果 `Employee` 类正在实现接口 `ICitizen` 和接口 `IEmployee`，而这两个接口都具有 `Name` 属性，则需要用到显式接口成员实现。</span><span class="sxs-lookup"><span data-stu-id="00fa8-117">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="00fa8-118">即是说下列属性声明：</span><span class="sxs-lookup"><span data-stu-id="00fa8-118">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="00fa8-119">在 `IEmployee` 接口中实现 `Name` 属性，而以下声明：</span><span class="sxs-lookup"><span data-stu-id="00fa8-119">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="00fa8-120">在 `ICitizen` 接口中实现 `Name` 属性。</span><span class="sxs-lookup"><span data-stu-id="00fa8-120">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="00fa8-121">示例输出</span><span class="sxs-lookup"><span data-stu-id="00fa8-121">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="00fa8-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="00fa8-122">See also</span></span>

- [<span data-ttu-id="00fa8-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="00fa8-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="00fa8-124">属性</span><span class="sxs-lookup"><span data-stu-id="00fa8-124">Properties</span></span>](./properties.md)
- [<span data-ttu-id="00fa8-125">使用属性</span><span class="sxs-lookup"><span data-stu-id="00fa8-125">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="00fa8-126">属性与索引器之间的比较</span><span class="sxs-lookup"><span data-stu-id="00fa8-126">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="00fa8-127">索引器</span><span class="sxs-lookup"><span data-stu-id="00fa8-127">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="00fa8-128">接口</span><span class="sxs-lookup"><span data-stu-id="00fa8-128">Interfaces</span></span>](../interfaces/index.md)
