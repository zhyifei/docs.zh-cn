---
title: 表达式主体定义的成员 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36f71352dca584c107af4f45850ce21bb016ba01
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238112"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="3ef08-102">Expression-bodied 成员（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3ef08-102">Expression-bodied members (C# programming guide)</span></span>
<span data-ttu-id="3ef08-103">通过表达式主体定义，可采用非常简洁的可读形式提供成员的实现。</span><span class="sxs-lookup"><span data-stu-id="3ef08-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="3ef08-104">只要任何支持的成员（如方法或属性）的逻辑包含单个表达式，就可以使用表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="3ef08-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="3ef08-105">表达式主体定义具有下列常规语法：</span><span class="sxs-lookup"><span data-stu-id="3ef08-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="3ef08-106">其中“expression”是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="3ef08-106">where *expression* is a valid expression.</span></span> 

<span data-ttu-id="3ef08-107">C# 6 中引入了针对方法和属性 Get 访问器的表达式主体定义支持，并在 C# 7.0 中进行了扩展。</span><span class="sxs-lookup"><span data-stu-id="3ef08-107">Support for expression body definitions was introduced for methods and property get accessors in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="3ef08-108">表达式主体定义可用于下表列出的类型成员：</span><span class="sxs-lookup"><span data-stu-id="3ef08-108">Expression body definitions can be used with the type members listed in the following table:</span></span> 

|<span data-ttu-id="3ef08-109">成员</span><span class="sxs-lookup"><span data-stu-id="3ef08-109">Member</span></span>  |<span data-ttu-id="3ef08-110">开始提供支持的版本</span><span class="sxs-lookup"><span data-stu-id="3ef08-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="3ef08-111">方法</span><span class="sxs-lookup"><span data-stu-id="3ef08-111">Method</span></span>](#methods)  |<span data-ttu-id="3ef08-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="3ef08-112">C# 6</span></span> |
|[<span data-ttu-id="3ef08-113">构造函数</span><span class="sxs-lookup"><span data-stu-id="3ef08-113">Constructor</span></span>](#constructors)   |<span data-ttu-id="3ef08-114">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="3ef08-114">C# 7.0</span></span> |
|[<span data-ttu-id="3ef08-115">终结器</span><span class="sxs-lookup"><span data-stu-id="3ef08-115">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="3ef08-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="3ef08-116">C# 7.0</span></span> |
|[<span data-ttu-id="3ef08-117">属性 Get</span><span class="sxs-lookup"><span data-stu-id="3ef08-117">Property Get</span></span>](#property-get-statements)  |<span data-ttu-id="3ef08-118">C# 6</span><span class="sxs-lookup"><span data-stu-id="3ef08-118">C# 6</span></span> |
|[<span data-ttu-id="3ef08-119">属性 Set</span><span class="sxs-lookup"><span data-stu-id="3ef08-119">Property Set</span></span>](#property-set-statements)  |<span data-ttu-id="3ef08-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="3ef08-120">C# 7.0</span></span> |
|[<span data-ttu-id="3ef08-121">索引器</span><span class="sxs-lookup"><span data-stu-id="3ef08-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="3ef08-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="3ef08-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="3ef08-123">方法</span><span class="sxs-lookup"><span data-stu-id="3ef08-123">Methods</span></span>

<span data-ttu-id="3ef08-124">expression-bodied 方法包含单个表达式，它返回的值的类型与方法的返回类型匹配；或者，对于返回 `void` 的方法，其表达式则执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="3ef08-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="3ef08-125">例如，替代 <xref:System.Object.ToString%2A> 方法的类型通常包含单个表达式，该表达式返回当前对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="3ef08-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span> 

<span data-ttu-id="3ef08-126">下面的示例定义 `Person` 类，该类通过表达式主体定义替代 <xref:System.Object.ToString%2A>。</span><span class="sxs-lookup"><span data-stu-id="3ef08-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="3ef08-127">它还定义向控制台显示名称的 `DisplayName` 方法。</span><span class="sxs-lookup"><span data-stu-id="3ef08-127">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="3ef08-128">请注意，`ToString` 表达式主体定义中未使用 `return` 关键字。</span><span class="sxs-lookup"><span data-stu-id="3ef08-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="3ef08-129">有关详细信息，请参阅[方法（C# 编程指南）](../classes-and-structs/methods.md)。</span><span class="sxs-lookup"><span data-stu-id="3ef08-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>
 
## <a name="constructors"></a><span data-ttu-id="3ef08-130">构造函数</span><span class="sxs-lookup"><span data-stu-id="3ef08-130">Constructors</span></span>

<span data-ttu-id="3ef08-131">构造函数的表达式主体定义通常包含单个赋值表达式或一个方法调用，该方法调用可处理构造函数的参数，也可初始化实例状态。</span><span class="sxs-lookup"><span data-stu-id="3ef08-131">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span> 

<span data-ttu-id="3ef08-132">以下示例定义 `Location` 类，其构造函数具有一个名为“name”的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="3ef08-132">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="3ef08-133">表达式主体定义向 `Name` 属性分配参数。</span><span class="sxs-lookup"><span data-stu-id="3ef08-133">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="3ef08-134">有关详细信息，请参阅[构造函数（C# 编程指南）](../classes-and-structs/constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="3ef08-134">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="3ef08-135">终结器</span><span class="sxs-lookup"><span data-stu-id="3ef08-135">Finalizers</span></span>

<span data-ttu-id="3ef08-136">终结器的表达式主体定义通常包含清理语句，例如释放非托管资源的语句。</span><span class="sxs-lookup"><span data-stu-id="3ef08-136">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="3ef08-137">下面的示例定义了一个终结器，该终结器使用表达式主体定义来指示已调用该终结器。</span><span class="sxs-lookup"><span data-stu-id="3ef08-137">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="3ef08-138">有关详细信息，请参阅[终结器（C# 编程指南）](../classes-and-structs/destructors.md)。</span><span class="sxs-lookup"><span data-stu-id="3ef08-138">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="property-get-statements"></a><span data-ttu-id="3ef08-139">属性 Get 语句</span><span class="sxs-lookup"><span data-stu-id="3ef08-139">Property get statements</span></span>

<span data-ttu-id="3ef08-140">如果选择自行实现属性 Get 访问器，可以对只返回属性值的单个表达式使用表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="3ef08-140">If you choose to implement a property get accessor yourself, you can use an expression body definition for single expressions that simply return the property value.</span></span> <span data-ttu-id="3ef08-141">请注意，未使用 `return` 语句。</span><span class="sxs-lookup"><span data-stu-id="3ef08-141">Note that the `return` statement isn't used.</span></span>

<span data-ttu-id="3ef08-142">下面的示例定义 `Location.Name` 属性，其属性 Get 访问器返回支持该属性的私有 `locationName` 字段的值。</span><span class="sxs-lookup"><span data-stu-id="3ef08-142">The following example defines a `Location.Name` property whose property get accessor returns the value of the private `locationName` field that backs the property.</span></span> 

[!code-csharp[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="3ef08-143">不使用显式 `set` 语句也可实现使用表达式主体定义的只读属性。</span><span class="sxs-lookup"><span data-stu-id="3ef08-143">Read-only properties that use an expression body definition can be implemented without an explicit `set` statement.</span></span> <span data-ttu-id="3ef08-144">语法为：</span><span class="sxs-lookup"><span data-stu-id="3ef08-144">The syntax is:</span></span>

```csharp
PropertyName => returnValue;
```

<span data-ttu-id="3ef08-145">下面的示例定义 `Location` 类，其只读 `Name` 属性以表达式主体定义的形式实现，该表达式主体定义返回私有 `locationName` 字段值。</span><span class="sxs-lookup"><span data-stu-id="3ef08-145">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="3ef08-146">有关详细信息，请参阅[属性（C# 编程指南）](../classes-and-structs/properties.md)。</span><span class="sxs-lookup"><span data-stu-id="3ef08-146">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="property-set-statements"></a><span data-ttu-id="3ef08-147">属性 Set 语句</span><span class="sxs-lookup"><span data-stu-id="3ef08-147">Property set statements</span></span>

<span data-ttu-id="3ef08-148">如果选择自行实现属性 Set 访问器，可以对单行表达式使用表达式主体定义，该单行表达式用于对支持该属性的字段赋值。</span><span class="sxs-lookup"><span data-stu-id="3ef08-148">If you choose to implement a property set accessor yourself, you can use an expression body definition for a single-line expression that assigns a value to the field that backs the property.</span></span>

<span data-ttu-id="3ef08-149">下面的示例定义 `Location.Name` 属性，其属性 Set 语句将其输入参数赋给支持该属性的私有 `locationName` 字段。</span><span class="sxs-lookup"><span data-stu-id="3ef08-149">The following example defines a `Location.Name` property whose property set statement assigns its input argument to the private `locationName` field that backs the property.</span></span>

[!code-csharp[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="3ef08-150">有关详细信息，请参阅[属性（C# 编程指南）](../classes-and-structs/properties.md)。</span><span class="sxs-lookup"><span data-stu-id="3ef08-150">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="3ef08-151">索引器</span><span class="sxs-lookup"><span data-stu-id="3ef08-151">Indexers</span></span>

<span data-ttu-id="3ef08-152">与属性一样，如果索引器的 Get 访问器包含单个返回值的语句或其 Set 访问器执行简单的赋值，则 Get 和 Set 访问器包含表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="3ef08-152">Like properties, an indexer's get and set accessors consist of expression body definitions if the get accessor consists of a single statement that returns a value or the set accessor performs a simple assignment.</span></span>

<span data-ttu-id="3ef08-153">下面的示例定义名为 `Sports` 的类，其中包含一个内部 <xref:System.String> 数组，该数组包含大量体育运动的名称。</span><span class="sxs-lookup"><span data-stu-id="3ef08-153">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="3ef08-154">索引器的 Get 和 Set 访问器都以表达式主体定义的形式实现。</span><span class="sxs-lookup"><span data-stu-id="3ef08-154">Both the indexer's get and set accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

<span data-ttu-id="3ef08-155">有关详细信息，请参阅[索引器（C# 编程指南）](../indexers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3ef08-155">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>

