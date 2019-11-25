---
title: 表达式主体定义的成员 - C# 编程指南
ms.custom: seodec18
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: 45dcc58b252963e80798ba86ca5c4f461d493fac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120144"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="9b14c-102">Expression-bodied 成员（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9b14c-102">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="9b14c-103">通过表达式主体定义，可采用非常简洁的可读形式提供成员的实现。</span><span class="sxs-lookup"><span data-stu-id="9b14c-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="9b14c-104">只要任何支持的成员（如方法或属性）的逻辑包含单个表达式，就可以使用表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="9b14c-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="9b14c-105">表达式主体定义具有下列常规语法：</span><span class="sxs-lookup"><span data-stu-id="9b14c-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="9b14c-106">其中“expression”  是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="9b14c-106">where *expression* is a valid expression.</span></span>

<span data-ttu-id="9b14c-107">C# 6 中引入了针对方法和只读属性的表达式主体定义支持，并在 C# 7.0 中进行了扩展。</span><span class="sxs-lookup"><span data-stu-id="9b14c-107">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="9b14c-108">表达式主体定义可用于下表列出的类型成员：</span><span class="sxs-lookup"><span data-stu-id="9b14c-108">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="9b14c-109">成员</span><span class="sxs-lookup"><span data-stu-id="9b14c-109">Member</span></span>  |<span data-ttu-id="9b14c-110">开始提供支持的版本</span><span class="sxs-lookup"><span data-stu-id="9b14c-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="9b14c-111">方法</span><span class="sxs-lookup"><span data-stu-id="9b14c-111">Method</span></span>](#methods)  |<span data-ttu-id="9b14c-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="9b14c-112">C# 6</span></span> |
|[<span data-ttu-id="9b14c-113">只读属性</span><span class="sxs-lookup"><span data-stu-id="9b14c-113">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="9b14c-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="9b14c-114">C# 6</span></span>  |
|[<span data-ttu-id="9b14c-115">Property</span><span class="sxs-lookup"><span data-stu-id="9b14c-115">Property</span></span>](#properties)  |<span data-ttu-id="9b14c-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="9b14c-116">C# 7.0</span></span> |
|[<span data-ttu-id="9b14c-117">构造函数</span><span class="sxs-lookup"><span data-stu-id="9b14c-117">Constructor</span></span>](#constructors)   |<span data-ttu-id="9b14c-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="9b14c-118">C# 7.0</span></span> |
|[<span data-ttu-id="9b14c-119">终结器</span><span class="sxs-lookup"><span data-stu-id="9b14c-119">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="9b14c-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="9b14c-120">C# 7.0</span></span> |
|[<span data-ttu-id="9b14c-121">索引器</span><span class="sxs-lookup"><span data-stu-id="9b14c-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="9b14c-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="9b14c-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="9b14c-123">方法</span><span class="sxs-lookup"><span data-stu-id="9b14c-123">Methods</span></span>

<span data-ttu-id="9b14c-124">expression-bodied 方法包含单个表达式，它返回的值的类型与方法的返回类型匹配；或者，对于返回 `void` 的方法，其表达式则执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="9b14c-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="9b14c-125">例如，替代 <xref:System.Object.ToString%2A> 方法的类型通常包含单个表达式，该表达式返回当前对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="9b14c-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="9b14c-126">下面的示例定义 `Person` 类，该类通过表达式主体定义替代 <xref:System.Object.ToString%2A>。</span><span class="sxs-lookup"><span data-stu-id="9b14c-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="9b14c-127">它还定义向控制台显示名称的 `DisplayName` 方法。</span><span class="sxs-lookup"><span data-stu-id="9b14c-127">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="9b14c-128">请注意，`ToString` 表达式主体定义中未使用 `return` 关键字。</span><span class="sxs-lookup"><span data-stu-id="9b14c-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="9b14c-129">有关详细信息，请参阅[方法（C# 编程指南）](../classes-and-structs/methods.md)。</span><span class="sxs-lookup"><span data-stu-id="9b14c-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="9b14c-130">只读属性</span><span class="sxs-lookup"><span data-stu-id="9b14c-130">Read-only properties</span></span>

<span data-ttu-id="9b14c-131">从 C# 6 开始，可以使用表达式主体定义来实现只读属性。</span><span class="sxs-lookup"><span data-stu-id="9b14c-131">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="9b14c-132">为此，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9b14c-132">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="9b14c-133">下面的示例定义 `Location` 类，其只读 `Name` 属性以表达式主体定义的形式实现，该表达式主体定义返回私有 `locationName` 字段值：</span><span class="sxs-lookup"><span data-stu-id="9b14c-133">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="9b14c-134">有关属性的详细信息，请参阅[属性（C# 编程指南）](../classes-and-structs/properties.md)。</span><span class="sxs-lookup"><span data-stu-id="9b14c-134">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="9b14c-135">属性</span><span class="sxs-lookup"><span data-stu-id="9b14c-135">Properties</span></span>

<span data-ttu-id="9b14c-136">从 C# 7.0 开始，可以使用表达式主体定义来实现属性 `get` 和 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="9b14c-136">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="9b14c-137">下面的示例演示其实现方法：</span><span class="sxs-lookup"><span data-stu-id="9b14c-137">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="9b14c-138">有关属性的详细信息，请参阅[属性（C# 编程指南）](../classes-and-structs/properties.md)。</span><span class="sxs-lookup"><span data-stu-id="9b14c-138">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="9b14c-139">构造函数</span><span class="sxs-lookup"><span data-stu-id="9b14c-139">Constructors</span></span>

<span data-ttu-id="9b14c-140">构造函数的表达式主体定义通常包含单个赋值表达式或一个方法调用，该方法调用可处理构造函数的参数，也可初始化实例状态。</span><span class="sxs-lookup"><span data-stu-id="9b14c-140">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="9b14c-141">以下示例定义 `Location` 类，其构造函数具有一个名为“name”  的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="9b14c-141">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="9b14c-142">表达式主体定义向 `Name` 属性分配参数。</span><span class="sxs-lookup"><span data-stu-id="9b14c-142">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="9b14c-143">有关详细信息，请参阅[构造函数（C# 编程指南）](../classes-and-structs/constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="9b14c-143">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="9b14c-144">终结器</span><span class="sxs-lookup"><span data-stu-id="9b14c-144">Finalizers</span></span>

<span data-ttu-id="9b14c-145">终结器的表达式主体定义通常包含清理语句，例如释放非托管资源的语句。</span><span class="sxs-lookup"><span data-stu-id="9b14c-145">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="9b14c-146">下面的示例定义了一个终结器，该终结器使用表达式主体定义来指示已调用该终结器。</span><span class="sxs-lookup"><span data-stu-id="9b14c-146">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="9b14c-147">有关详细信息，请参阅[终结器（C# 编程指南）](../classes-and-structs/destructors.md)。</span><span class="sxs-lookup"><span data-stu-id="9b14c-147">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="9b14c-148">索引器</span><span class="sxs-lookup"><span data-stu-id="9b14c-148">Indexers</span></span>

<span data-ttu-id="9b14c-149">与使用属性一样，如果 `get` 访问器包含返回值的单个表达式或 `set` 访问器执行简单的赋值，则索引器 `get` 和 `set` 访问器包含表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="9b14c-149">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="9b14c-150">下面的示例定义名为 `Sports` 的类，其中包含一个内部 <xref:System.String> 数组，该数组包含大量体育运动的名称。</span><span class="sxs-lookup"><span data-stu-id="9b14c-150">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="9b14c-151">索引器的 `get` 和 `set` 访问器都以表达式主体定义的形式实现。</span><span class="sxs-lookup"><span data-stu-id="9b14c-151">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="9b14c-152">有关详细信息，请参阅[索引器（C# 编程指南）](../indexers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="9b14c-152">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
