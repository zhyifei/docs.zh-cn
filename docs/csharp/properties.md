---
title: "属性"
description: "了解 C# 属性，包括验证功能、计算值、迟缓计算及属性更改通知。"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 04/03/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 6950d25a-bba1-4744-b7c7-a3cc90438c55
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e5d2d5d7074678383243e687d4b469606007e585
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="properties"></a><span data-ttu-id="5d141-104">属性</span><span class="sxs-lookup"><span data-stu-id="5d141-104">Properties</span></span>

<span data-ttu-id="5d141-105">属性是 C# 中的一等公民。</span><span class="sxs-lookup"><span data-stu-id="5d141-105">Properties are first class citizens in C#.</span></span> <span data-ttu-id="5d141-106">借助该语言所定义的语法，开发人员能够编写出准确表达其设计意图的代码。</span><span class="sxs-lookup"><span data-stu-id="5d141-106">The language defines syntax that enables developers to write code that accurately expresses their design intent.</span></span>

<span data-ttu-id="5d141-107">访问属性时，其行为类似于字段。</span><span class="sxs-lookup"><span data-stu-id="5d141-107">Properties behave like fields when they are accessed.</span></span>
<span data-ttu-id="5d141-108">但与字段不同的是，属性通过访问器实现；访问器用于定义访问属性或为属性赋值时执行的语句。</span><span class="sxs-lookup"><span data-stu-id="5d141-108">However, unlike fields, properties are implemented with accessors that define the statements executed when a property is accessed or assigned.</span></span>

## <a name="property-syntax"></a><span data-ttu-id="5d141-109">属性语法</span><span class="sxs-lookup"><span data-stu-id="5d141-109">Property Syntax</span></span>

<span data-ttu-id="5d141-110">属性语法是字段的自然延伸。</span><span class="sxs-lookup"><span data-stu-id="5d141-110">The syntax for properties is a natural extension to fields.</span></span> <span data-ttu-id="5d141-111">字段定义存储位置：</span><span class="sxs-lookup"><span data-stu-id="5d141-111">A field defines a storage location:</span></span>

```csharp
public class Person
{
    public string FirstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="5d141-112">属性定义包含 `get` 和 `set` 访问器的声明，这两个访问器用于检索该属性的值以及对其赋值：</span><span class="sxs-lookup"><span data-stu-id="5d141-112">A property definition contains declarations for a `get` and `set` accessor that retrieves and assigns the value of that property:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="5d141-113">上述语法是*自动属性*语法。</span><span class="sxs-lookup"><span data-stu-id="5d141-113">The syntax shown above is the *auto property* syntax.</span></span> <span data-ttu-id="5d141-114">编译器生成支持该属性的字段的存储位置。</span><span class="sxs-lookup"><span data-stu-id="5d141-114">The compiler generates the storage location for the field that backs up the property.</span></span> <span data-ttu-id="5d141-115">编译器还实现 `get` 和 `set` 访问器的正文。</span><span class="sxs-lookup"><span data-stu-id="5d141-115">The compiler also implements the body of the `get` and `set` accessors.</span></span>

<span data-ttu-id="5d141-116">有时，需要将属性初始化为其类型默认值以外的值。</span><span class="sxs-lookup"><span data-stu-id="5d141-116">Sometimes, you need to initialize a property to a value other than the default for its type.</span></span>  <span data-ttu-id="5d141-117">C# 通过在属性的右括号后设置值达到此目的。</span><span class="sxs-lookup"><span data-stu-id="5d141-117">C# enables that by setting a value after the closing brace for the property.</span></span> <span data-ttu-id="5d141-118">对于 `FirstName` 属性的的初始值，你可能更希望设置为空字符串而非 `null`。</span><span class="sxs-lookup"><span data-stu-id="5d141-118">You may prefer the initial value for the `FirstName` property to be the empty string rather than `null`.</span></span> <span data-ttu-id="5d141-119">可按如下所示进行指定：</span><span class="sxs-lookup"><span data-stu-id="5d141-119">You would specify that as shown below:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; } = string.Empty;

    // remaining implementation removed from listing
}
```

<span data-ttu-id="5d141-120">这对于只读属性最有用，本主题的后面部分将进行介绍。</span><span class="sxs-lookup"><span data-stu-id="5d141-120">This is most useful for read-only properties, as you'll see later in this topic.</span></span>

<span data-ttu-id="5d141-121">你也可以自行定义存储，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5d141-121">You can also define the storage yourself, as shown below:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get { return firstName; }
        set { firstName = value; }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="5d141-122">属性实现是单个表达式时，可为 getter 或 setter 使用表达式主体成员：</span><span class="sxs-lookup"><span data-stu-id="5d141-122">When a property implementation is a single expression, you can use *expression bodied members* for the getter or setter:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get => firstName;
        set => firstName = value;
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="5d141-123">在本主题中，将在所有适用之处使用此简化的语法。</span><span class="sxs-lookup"><span data-stu-id="5d141-123">This simplified syntax will be used where applicable throughout this topic.</span></span>

<span data-ttu-id="5d141-124">上述属性定义是读-写属性。</span><span class="sxs-lookup"><span data-stu-id="5d141-124">The property definition shown above is a read-write property.</span></span> <span data-ttu-id="5d141-125">注意 set 访问器中的关键字 `value`。</span><span class="sxs-lookup"><span data-stu-id="5d141-125">Notice the keyword `value` in the set accessor.</span></span> <span data-ttu-id="5d141-126">`set` 访问器始终具有一个名为 `value` 的参数。</span><span class="sxs-lookup"><span data-stu-id="5d141-126">The `set` accessor always has a single parameter named `value`.</span></span> <span data-ttu-id="5d141-127">`get` 访问器必须返回一个值，该值可转换为该属性的类型（本例中为 `string`）。</span><span class="sxs-lookup"><span data-stu-id="5d141-127">The `get` accessor must return a value that is convertible to the type of the property (`string` in this example).</span></span>
 
<span data-ttu-id="5d141-128">这就是该语法的基础知识。</span><span class="sxs-lookup"><span data-stu-id="5d141-128">That's the basics of the syntax.</span></span> <span data-ttu-id="5d141-129">有许多不同的语法变体，支持着各种不同的设计习惯。</span><span class="sxs-lookup"><span data-stu-id="5d141-129">There are many different variations that support a variety of different design idioms.</span></span> <span data-ttu-id="5d141-130">接下来我们将了解这些变体，以及每个变体的语法选项。</span><span class="sxs-lookup"><span data-stu-id="5d141-130">Let's explore those, and learn the syntax options for each.</span></span>

## <a name="scenarios"></a><span data-ttu-id="5d141-131">方案</span><span class="sxs-lookup"><span data-stu-id="5d141-131">Scenarios</span></span>

<span data-ttu-id="5d141-132">上述示例介绍了属性定义中最简单的一种情况：不进行验证的读-写属性。</span><span class="sxs-lookup"><span data-stu-id="5d141-132">The examples above showed one of the simplest cases of property definition: a read-write property with no validation.</span></span> <span data-ttu-id="5d141-133">通过在 `get` 和 `set` 访问器中编写所需的代码，可以创建多种不同的方案。</span><span class="sxs-lookup"><span data-stu-id="5d141-133">By writing the code you want in the `get` and `set` accessors, you can create many different scenarios.</span></span>

### <a name="validation"></a><span data-ttu-id="5d141-134">验证</span><span class="sxs-lookup"><span data-stu-id="5d141-134">Validation</span></span>

<span data-ttu-id="5d141-135">可以在 `set` 访问器中编写代码，确保由某个属性表示的值始终有效。</span><span class="sxs-lookup"><span data-stu-id="5d141-135">You can write code in the `set` accessor to ensure that the values represented by a property are always valid.</span></span> <span data-ttu-id="5d141-136">例如，假设 `Person` 类的一个规则是名称不能为空白或空格。</span><span class="sxs-lookup"><span data-stu-id="5d141-136">For example, suppose one rule for the `Person` class is that the name cannot be blank, or whitespace.</span></span> <span data-ttu-id="5d141-137">可按如下方式编写：</span><span class="sxs-lookup"><span data-stu-id="5d141-137">You would write that as follows:</span></span>

```csharp
public class Person
{
    public string FirstName
    {
        get => firstName;
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            firstName = value;
        }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="5d141-138">上面的示例强制执行名字不能为空白或空格的规则。</span><span class="sxs-lookup"><span data-stu-id="5d141-138">The example above enforces the rule that the first name must not be blank, or whitespace.</span></span> <span data-ttu-id="5d141-139">如果开发人员编写</span><span class="sxs-lookup"><span data-stu-id="5d141-139">If a developer writes</span></span>

```csharp
hero.FirstName = "";
```

<span data-ttu-id="5d141-140">该赋值会引发 `ArgumentException`。</span><span class="sxs-lookup"><span data-stu-id="5d141-140">That assignment throws an `ArgumentException`.</span></span> <span data-ttu-id="5d141-141">由于属性 set 访问器必须具有 void 返回类型，因此将通过引发异常来报告 set 访问器中的错误。</span><span class="sxs-lookup"><span data-stu-id="5d141-141">Because a property set accessor must have a void return type, you report errors in the set accessor by throwing an exception.</span></span>

<span data-ttu-id="5d141-142">这是一个简单的验证示例。</span><span class="sxs-lookup"><span data-stu-id="5d141-142">That is a simple case of validation.</span></span> <span data-ttu-id="5d141-143">你可以根据自己的情况随意扩展此语法。</span><span class="sxs-lookup"><span data-stu-id="5d141-143">You can extend this same syntax to anything needed in your scenario.</span></span> <span data-ttu-id="5d141-144">可以检查不同属性之间的关系，或根据任何外部条件进行验证。</span><span class="sxs-lookup"><span data-stu-id="5d141-144">You can check the relationships between different properties, or validate against any external conditions.</span></span> <span data-ttu-id="5d141-145">任何有效的 C# 语句在属性访问器中都是有效的。</span><span class="sxs-lookup"><span data-stu-id="5d141-145">Any valid C# statements are valid in a property accessor.</span></span>

### <a name="read-only"></a><span data-ttu-id="5d141-146">只读</span><span class="sxs-lookup"><span data-stu-id="5d141-146">Read-only</span></span>

<span data-ttu-id="5d141-147">到目前为止，你了解的所有属性定义都是具有公共访问器的读/写属性。</span><span class="sxs-lookup"><span data-stu-id="5d141-147">Up to this point, all the property definitions you have seen are read/write properties with public accessors.</span></span> <span data-ttu-id="5d141-148">但这不是属性唯一有效的可访问性。</span><span class="sxs-lookup"><span data-stu-id="5d141-148">That's not the only valid accessibility for properties.</span></span>
<span data-ttu-id="5d141-149">你可以创建只读属性，或者对 set 和 get 访问器提供不同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="5d141-149">You can create read-only properties, or give different accessibility to the set and get accessors.</span></span> <span data-ttu-id="5d141-150">假设 `Person` 类只能从该类的其他方法中启用 `FirstName` 属性值更改。</span><span class="sxs-lookup"><span data-stu-id="5d141-150">Suppose that your `Person` class should only enable changing the value of the `FirstName` property from other methods in that class.</span></span> <span data-ttu-id="5d141-151">可以为 set 访问器提供 `private` 可访问性，而不是 `public` 可访问性：</span><span class="sxs-lookup"><span data-stu-id="5d141-151">You could give the set accessor `private` accessibility instead of `public`:</span></span>

```csharp
public class Person
{
    public string FirstName { get; private set; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="5d141-152">现在，可以从任意代码访问 `FirstName` 属性，但只能从 `Person` 类中的其他代码对其赋值。</span><span class="sxs-lookup"><span data-stu-id="5d141-152">Now, the `FirstName` property can be accessed from any code, but it can only be assigned from other code in the `Person` class.</span></span>

<span data-ttu-id="5d141-153">可以向 set 和 get 访问器添加任何严格访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="5d141-153">You can add any restrictive access modifier to either the set or get accessors.</span></span> <span data-ttu-id="5d141-154">在单个访问器上放置的任何访问修饰符都必须比属性定义上的访问修饰符提供更严格的限制。</span><span class="sxs-lookup"><span data-stu-id="5d141-154">Any access modifier you place on the individual accessor must be more limited than the access modifier on the property definition.</span></span> <span data-ttu-id="5d141-155">上述做法是合法的，因为 `FirstName` 属性为 `public`，但 set 访问器为 `private`。</span><span class="sxs-lookup"><span data-stu-id="5d141-155">The above is legal because the `FirstName` property is `public`, but the set accessor is `private`.</span></span> <span data-ttu-id="5d141-156">不能声明具有 `public` 访问器的 `private` 属性。</span><span class="sxs-lookup"><span data-stu-id="5d141-156">You could not declare a `private` property with a `public` accessor.</span></span> <span data-ttu-id="5d141-157">属性声明还可以声明为 `protected`、`internal`、`protected internal` 甚至 `private`。</span><span class="sxs-lookup"><span data-stu-id="5d141-157">Property declarations can also be declared `protected`, `internal`, `protected internal` or even `private`.</span></span>   

<span data-ttu-id="5d141-158">在 `get` 访问器上放置限制性更强的修饰符也是合法的。</span><span class="sxs-lookup"><span data-stu-id="5d141-158">It is also legal to place the more restrictive modifier on the `get` accessor.</span></span> <span data-ttu-id="5d141-159">例如，可以有一个 `public` 属性，但将 `get` 访问器限制为 `private`。</span><span class="sxs-lookup"><span data-stu-id="5d141-159">For example, you could have a `public` property, but restrict the `get` accessor to `private`.</span></span> <span data-ttu-id="5d141-160">不过实际情况下很少这么做。</span><span class="sxs-lookup"><span data-stu-id="5d141-160">That scenario is rarely done in practice.</span></span>

<span data-ttu-id="5d141-161">还可以限制对属性的修改，以便只能在构造函数或属性初始化表达式中设置属性。</span><span class="sxs-lookup"><span data-stu-id="5d141-161">You can also restrict modifications to a property so that it can only be set in a constructor or a property initializer.</span></span> <span data-ttu-id="5d141-162">可按照这种方式修改 `Person` 类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5d141-162">You can modify the `Person` class so as follows:</span></span>

```csharp
public class Person
{
    public Person(string firstName)
    {
        this.FirstName = firstName;
    }

    public string FirstName { get; }

    // remaining implementation removed from listing
}
```

<span data-ttu-id="5d141-163">此功能通常用于初始化作为只读属性公开的集合：</span><span class="sxs-lookup"><span data-stu-id="5d141-163">This feature is most commonly used for initializing collections that are exposed as read-only properties:</span></span>

```csharp
public class Measurements
{
    public ICollection<DataPoint> points { get; } = new List<DataPoint>();
}
```

### <a name="computed-properties"></a><span data-ttu-id="5d141-164">计算属性</span><span class="sxs-lookup"><span data-stu-id="5d141-164">Computed Properties</span></span>

<span data-ttu-id="5d141-165">属性无需只返回某个成员字段的值。</span><span class="sxs-lookup"><span data-stu-id="5d141-165">A property does not need to simply return the value of a member field.</span></span> <span data-ttu-id="5d141-166">可以创建返回计算值的属性。</span><span class="sxs-lookup"><span data-stu-id="5d141-166">You can create properties that return a computed value.</span></span> <span data-ttu-id="5d141-167">让我们展开 `Person` 对象，返回通过串联名字和姓氏计算得出的全名：</span><span class="sxs-lookup"><span data-stu-id="5d141-167">Let's expand the `Person` object to return the full name, computed by concatenating the first and last names:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName { get { return $"{FirstName} {LastName}"; } }
}
```

<span data-ttu-id="5d141-168">上面的示例使用*字符串内插*语法来创建全名的格式化字符串。</span><span class="sxs-lookup"><span data-stu-id="5d141-168">The example above uses the *String Interpolation* syntax to create the formatted string for the full name.</span></span>

<span data-ttu-id="5d141-169">也可以使用*表达式主体成员*，以更简洁的方式来创建 `FullName` 计算属性：</span><span class="sxs-lookup"><span data-stu-id="5d141-169">You can also use *Expression-bodied Members*, which provides a more succinct way to create the computed `FullName` property:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public string FullName =>  $"{FirstName} {LastName}";
}
```
 
<span data-ttu-id="5d141-170">*表达式主体成员*使用 *lambda 表达式*语法来定义包含单个表达式的方法。</span><span class="sxs-lookup"><span data-stu-id="5d141-170">*Expression-bodied Members* use the *lambda expression* syntax to define a method that contain a single expression.</span></span> <span data-ttu-id="5d141-171">在这里，该表达式返回 person 对象的全名。</span><span class="sxs-lookup"><span data-stu-id="5d141-171">Here, that expression returns the full name for the person object.</span></span>

### <a name="lazy-evaluated-properties"></a><span data-ttu-id="5d141-172">迟缓计算的属性</span><span class="sxs-lookup"><span data-stu-id="5d141-172">Lazy Evaluated Properties</span></span>

<span data-ttu-id="5d141-173">可以将计算属性和存储的概念混合起来，创建*迟缓计算的属性*。</span><span class="sxs-lookup"><span data-stu-id="5d141-173">You can mix the concept of a computed property with storage and create a *lazy evaluated property*.</span></span>  <span data-ttu-id="5d141-174">例如，可以更新 `FullName` 属性，以便仅在第一次访问该属性时进行字符串格式设置：</span><span class="sxs-lookup"><span data-stu-id="5d141-174">For example, you could update the `FullName` property so that the string formatting only happened the first time it was accessed:</span></span>

```csharp
public class Person
{
    public string FirstName { get; set; }

    public string LastName { get; set; }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

<span data-ttu-id="5d141-175">不过，上面的代码含有 bug。</span><span class="sxs-lookup"><span data-stu-id="5d141-175">The above code contains a bug though.</span></span> <span data-ttu-id="5d141-176">如果代码更新 `FirstName` 或 `LastName` 属性的值，那么，以前计算的 `fullName` 字段将无效。</span><span class="sxs-lookup"><span data-stu-id="5d141-176">If code updates the value of either the `FirstName` or `LastName` property, the previously evaluated `fullName` field is invalid.</span></span> <span data-ttu-id="5d141-177">需要更新 `FirstName` 和 `LastName` 属性的 `set` 访问器，以便重新计算 `fullName` 字段：</span><span class="sxs-lookup"><span data-stu-id="5d141-177">You need to update the `set` accessors of the `FirstName` and `LastName` property so that the `fullName` field is calculated again:</span></span>

```csharp
public class Person
{
    private string firstName;
    public string FirstName
    {
        get => firstName;
        set
        {
            firstName = value;
            fullName = null;
        }
    }

    private string lastName;
    public string LastName
    {
        get => lastName;
        set
        {
            lastName = value;
            fullName = null;
        }
    }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

<span data-ttu-id="5d141-178">此最终版本仅在必要时计算 `FullName` 属性。</span><span class="sxs-lookup"><span data-stu-id="5d141-178">This final version evaluates the `FullName` property only when needed.</span></span>
<span data-ttu-id="5d141-179">如果以前计算的版本有效，则使用它。</span><span class="sxs-lookup"><span data-stu-id="5d141-179">If the previously calculated version is valid, it's used.</span></span> <span data-ttu-id="5d141-180">如果另一个状态更改使以前计算的版本失效，则重新计算。</span><span class="sxs-lookup"><span data-stu-id="5d141-180">If another state change invalidates the previously calculated version, it will be recalculated.</span></span> <span data-ttu-id="5d141-181">使用此类的开发人员无需了解实现的细枝末节。</span><span class="sxs-lookup"><span data-stu-id="5d141-181">Developers that use this class do not need to know the details of the implementation.</span></span> <span data-ttu-id="5d141-182">这些内部更改不会影响 Person 对象的使用。</span><span class="sxs-lookup"><span data-stu-id="5d141-182">None of these internal changes affect the use of the Person object.</span></span> <span data-ttu-id="5d141-183">这是使用属性公开对象的数据成员的关键原因。</span><span class="sxs-lookup"><span data-stu-id="5d141-183">That's the key reason for using Properties to expose data members of an object.</span></span>
 
### <a name="inotifypropertychanged"></a><span data-ttu-id="5d141-184">INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="5d141-184">INotifyPropertyChanged</span></span>

<span data-ttu-id="5d141-185">需要在属性访问器中编写代码的最后一种情形是为了支持 `INotifyPropertyChanged` 接口，该接口用于通知数据绑定客户端值已更改。</span><span class="sxs-lookup"><span data-stu-id="5d141-185">A final scenario where you need to write code in a property accessor is to support the `INotifyPropertyChanged` interface used to notify data binding clients that a value has changed.</span></span> <span data-ttu-id="5d141-186">当属性值发生更改时，该对象引发 `PropertyChanged` 事件来指示更改。</span><span class="sxs-lookup"><span data-stu-id="5d141-186">When the value of a property changes, the object raises the `PropertyChanged` event to indicate the change.</span></span> <span data-ttu-id="5d141-187">数据绑定库则基于该更改来更新显示元素。</span><span class="sxs-lookup"><span data-stu-id="5d141-187">The data binding libraries, in turn, update display elements based on that change.</span></span> <span data-ttu-id="5d141-188">下面的代码演示如何为此 person 类的 `FirstName` 属性实现 `INotifyPropertyChanged`。</span><span class="sxs-lookup"><span data-stu-id="5d141-188">The code below shows how you would implement `INotifyPropertyChanged` for the `FirstName` property of this person class.</span></span>

```csharp
public class Person : INotifyPropertyChanged
{
    public string FirstName
    {
        get => firstName;
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            if (value != firstName)
            {
                PropertyChanged?.Invoke(this, 
                    new PropertyChangedEventArgs(nameof(FirstName)));
            }
            firstName = value;
        }
    }
    private string firstName;

    public event PropertyChangedEventHandler PropertyChanged;
    // remaining implementation removed from listing
}
```

<span data-ttu-id="5d141-189">`?.` 运算符称作 *null 条件运算符*。</span><span class="sxs-lookup"><span data-stu-id="5d141-189">The `?.` operator is called the *null conditional operator*.</span></span> <span data-ttu-id="5d141-190">它在计算运算符右侧之前会检查是否存在空引用。</span><span class="sxs-lookup"><span data-stu-id="5d141-190">It checks for a null reference before evaluating the right side of the operator.</span></span> <span data-ttu-id="5d141-191">最终结果为：如果 `PropertyChanged` 事件没有订阅者，则不执行用于引发该事件的代码。</span><span class="sxs-lookup"><span data-stu-id="5d141-191">The end result is that if there are no subscribers to the `PropertyChanged` event, the code to raise the event doesn't execute.</span></span> <span data-ttu-id="5d141-192">在这种情况下，如果不执行此检查，则会引发 `NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="5d141-192">It would throw a `NullReferenceException` without this check in that case.</span></span> <span data-ttu-id="5d141-193">有关更多详细信息，请参阅有关 [`events`](delegates-events.md) 的页面。</span><span class="sxs-lookup"><span data-stu-id="5d141-193">See the page on [`events`](delegates-events.md) for more details.</span></span> <span data-ttu-id="5d141-194">此示例还使用新的 `nameof` 运算符将属性名称符号转换为其文本表示形式。</span><span class="sxs-lookup"><span data-stu-id="5d141-194">This example also uses the new `nameof` operator to convert from the property name symbol to its text representation.</span></span>
<span data-ttu-id="5d141-195">使用 `nameof` 可以减少输错属性名称这样的错误。</span><span class="sxs-lookup"><span data-stu-id="5d141-195">Using `nameof` can reduce errors where you have mistyped the name of the property.</span></span>

<span data-ttu-id="5d141-196">再次说明，此示例演示的是可以在访问器中编写代码以支持所需方案的情况。</span><span class="sxs-lookup"><span data-stu-id="5d141-196">Again, this is an example of a case where you can write code in your accessors to support the scenarios you need.</span></span>

## <a name="summing-up"></a><span data-ttu-id="5d141-197">总结</span><span class="sxs-lookup"><span data-stu-id="5d141-197">Summing up</span></span>

<span data-ttu-id="5d141-198">属性是类或对象中的一种智能字段形式。</span><span class="sxs-lookup"><span data-stu-id="5d141-198">Properties are a form of smart fields in a class or object.</span></span> <span data-ttu-id="5d141-199">从对象外部，它们看起来像对象中的字段。</span><span class="sxs-lookup"><span data-stu-id="5d141-199">From outside the object, they appear like fields in the object.</span></span> <span data-ttu-id="5d141-200">但是，属性可以通过丰富的 C# 功能来实现。</span><span class="sxs-lookup"><span data-stu-id="5d141-200">However, properties can be implemented using the full palette of C# functionality.</span></span>
<span data-ttu-id="5d141-201">你可以提供验证、不同的可访问性、迟缓计算或方案所需的任何要求。</span><span class="sxs-lookup"><span data-stu-id="5d141-201">You can provide validation, different accessibility, lazy evaluation, or any requirements your scenarios need.</span></span>

