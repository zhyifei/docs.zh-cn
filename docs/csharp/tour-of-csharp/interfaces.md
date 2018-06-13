---
title: C# 接口 - C# 语言介绍
description: 接口定义 C# 类型实现的协定
ms.date: 08/10/2016
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.openlocfilehash: 0ad02d5b2792656783d93b2cc767aeb81efbc30e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343890"
---
# <a name="interfaces"></a><span data-ttu-id="7d9b6-103">接口</span><span class="sxs-lookup"><span data-stu-id="7d9b6-103">Interfaces</span></span>

<span data-ttu-id="7d9b6-104">***接口***定义了可由类和结构实现的协定。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-104">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="7d9b6-105">接口可以包含方法、属性、事件和索引器。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-105">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="7d9b6-106">接口不提供所定义的成员的实现代码，仅指定必须由实现接口的类或结构提供的成员。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-106">An interface does not provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="7d9b6-107">接口可以采用***多重继承***。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-107">Interfaces may employ ***multiple inheritance***.</span></span> <span data-ttu-id="7d9b6-108">在以下示例中，接口 `IComboBox` 同时继承自 `ITextBox` 和 `IListBox`。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-108">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]

<span data-ttu-id="7d9b6-109">类和结构可以实现多个接口。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-109">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="7d9b6-110">在以下示例中，类 `EditBox` 同时实现 `IControl` 和 `IDataBound`。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-110">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]

<span data-ttu-id="7d9b6-111">当类或结构实现特定接口时，此类或结构的实例可以隐式转换成相应的接口类型。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-111">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="7d9b6-112">例如</span><span class="sxs-lookup"><span data-stu-id="7d9b6-112">For example</span></span>

[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]

<span data-ttu-id="7d9b6-113">如果已知实例不是静态地实现特定接口，可以使用动态类型显式转换功能。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-113">In cases where an instance is not statically known to implement a particular interface, dynamic type casts can be used.</span></span> <span data-ttu-id="7d9b6-114">例如，以下语句使用动态类型显式转换功能来获取对象的 `IControl` 和 `IDataBound` 接口实现代码。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-114">For example, the following statements use dynamic type casts to obtain an object’s `IControl` and `IDataBound` interface implementations.</span></span> <span data-ttu-id="7d9b6-115">因为对象的运行时实际类型是 `EditBox`，所以显式转换会成功。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-115">Because the run-time actual type of the object is `EditBox`, the casts succeed.</span></span>

[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]

<span data-ttu-id="7d9b6-116">在前面的 `EditBox` 类中，`IControl` 接口中的 `Paint` 方法和 `IDataBound` 接口中的 `Bind` 方法均使用公共成员进行实现。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-116">In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using public members.</span></span> <span data-ttu-id="7d9b6-117">C# 还支持显式***接口成员实现代码***，这样类或结构就不会将成员设为公共成员。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-117">C# also supports explicit ***interface member implementations***, enabling the class or struct to avoid making the members public.</span></span> <span data-ttu-id="7d9b6-118">显式接口成员实现代码是使用完全限定的接口成员名称进行编写。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-118">An explicit interface member implementation is written using the fully qualified interface member name.</span></span> <span data-ttu-id="7d9b6-119">例如，`EditBox` 类可以使用显式接口成员实现代码来实现 `IControl.Paint` 和 `IDataBound.Bind` 方法，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-119">For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]

<span data-ttu-id="7d9b6-120">显式接口成员只能通过接口类型进行访问。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-120">Explicit interface members can only be accessed via the interface type.</span></span> <span data-ttu-id="7d9b6-121">例如，只有先将 `EditBox` 引用转换成 `IControl` 接口类型，才能调用上面 EditBox 类提供的 `IControl.Paint` 实现代码。</span><span class="sxs-lookup"><span data-stu-id="7d9b6-121">For example, the implementation of `IControl.Paint` provided by the previous EditBox class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]

>[!div class="step-by-step"]
<span data-ttu-id="7d9b6-122">[上一页](arrays.md)
[下一页](enums.md)</span><span class="sxs-lookup"><span data-stu-id="7d9b6-122">[Previous](arrays.md)
[Next](enums.md)</span></span>
