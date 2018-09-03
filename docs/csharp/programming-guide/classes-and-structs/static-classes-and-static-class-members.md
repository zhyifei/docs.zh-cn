---
title: 静态类和静态类成员（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
ms.openlocfilehash: f3e64d975d2845d8317b37f43c3811af6be03b55
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468692"
---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a><span data-ttu-id="8960e-102">静态类和静态类成员（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8960e-102">Static Classes and Static Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="8960e-103">[静态](../../../csharp/language-reference/keywords/static.md)类基本上与非静态类相同，但存在一个差异：静态类无法实例化。</span><span class="sxs-lookup"><span data-stu-id="8960e-103">A [static](../../../csharp/language-reference/keywords/static.md) class is basically the same as a non-static class, but there is one difference: a static class cannot be instantiated.</span></span> <span data-ttu-id="8960e-104">换句话说，无法使用 [new](../../../csharp/language-reference/keywords/new.md) 关键字创建类类型的变量。</span><span class="sxs-lookup"><span data-stu-id="8960e-104">In other words, you cannot use the [new](../../../csharp/language-reference/keywords/new.md) keyword to create a variable of the class type.</span></span> <span data-ttu-id="8960e-105">由于不存在任何实例变量，因此可以使用类名本身访问静态类的成员。</span><span class="sxs-lookup"><span data-stu-id="8960e-105">Because there is no instance variable, you access the members of a static class by using the class name itself.</span></span> <span data-ttu-id="8960e-106">例如，如果你具有一个静态类，该类名为 `UtilityClass`，并且具有一个名为 `MethodA` 的公共方法，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="8960e-106">For example, if you have a static class that is named `UtilityClass` that has a public method named `MethodA`, you call the method as shown in the following example:</span></span>  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 <span data-ttu-id="8960e-107">静态类可以用作只对输入参数进行操作并且不必获取或设置任何内部实例字段的方法集的方便容器。</span><span class="sxs-lookup"><span data-stu-id="8960e-107">A static class can be used as a convenient container for sets of methods that just operate on input parameters and do not have to get or set any internal instance fields.</span></span> <span data-ttu-id="8960e-108">例如，在 .NET Framework 类库中，静态 <xref:System.Math?displayProperty=nameWithType> 类包含执行数学运算，而无需存储或检索对 <xref:System.Math> 类特定实例唯一的数据的方法。</span><span class="sxs-lookup"><span data-stu-id="8960e-108">For example, in the .NET Framework Class Library, the static <xref:System.Math?displayProperty=nameWithType> class contains methods that perform mathematical operations, without any requirement to store or retrieve data that is unique to a particular instance of the <xref:System.Math> class.</span></span> <span data-ttu-id="8960e-109">即，通过指定类名和方法名称来应用类的成员，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="8960e-109">That is, you apply the members of the class by specifying the class name and the method name, as shown in the following example.</span></span>  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 <span data-ttu-id="8960e-110">与所有类类型的情况一样，静态类的类型信息在引用该类的程序加载时，由 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 公共语言运行时 (CLR) 加载。</span><span class="sxs-lookup"><span data-stu-id="8960e-110">As is the case with all class types, the type information for a static class is loaded by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] common language runtime (CLR) when the program that references the class is loaded.</span></span> <span data-ttu-id="8960e-111">程序无法确切指定类加载的时间。</span><span class="sxs-lookup"><span data-stu-id="8960e-111">The program cannot specify exactly when the class is loaded.</span></span> <span data-ttu-id="8960e-112">但是，可保证进行加载，以及在程序中首次引用类之前初始化其字段并调用其静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="8960e-112">However, it is guaranteed to be loaded and to have its fields initialized and its static constructor called before the class is referenced for the first time in your program.</span></span> <span data-ttu-id="8960e-113">静态构造函数只调用一次，在程序所驻留的应用程序域的生存期内，静态类会保留在内存中。</span><span class="sxs-lookup"><span data-stu-id="8960e-113">A static constructor is only called one time, and a static class remains in memory for the lifetime of the application domain in which your program resides.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8960e-114">若要创建仅允许创建本身的一个实例的非静态类，请参阅[在 C# 中实现单一实例](https://msdn.microsoft.com/library/ms998558.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8960e-114">To create a non-static class that allows only one instance of itself to be created, see [Implementing Singleton in C#](https://msdn.microsoft.com/library/ms998558.aspx).</span></span>  
  
 <span data-ttu-id="8960e-115">以下列表提供静态类的主要功能：</span><span class="sxs-lookup"><span data-stu-id="8960e-115">The following list provides the main features of a static class:</span></span>  
  
-   <span data-ttu-id="8960e-116">只包含静态成员。</span><span class="sxs-lookup"><span data-stu-id="8960e-116">Contains only static members.</span></span>  
  
-   <span data-ttu-id="8960e-117">无法进行实例化。</span><span class="sxs-lookup"><span data-stu-id="8960e-117">Cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="8960e-118">会进行密封。</span><span class="sxs-lookup"><span data-stu-id="8960e-118">Is sealed.</span></span>  
  
-   <span data-ttu-id="8960e-119">不能包含[实例构造函数](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="8960e-119">Cannot contain [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="8960e-120">因此，创建静态类基本上与创建只包含静态成员和私有构造函数的类相同。</span><span class="sxs-lookup"><span data-stu-id="8960e-120">Creating a static class is therefore basically the same as creating a class that contains only static members and a private constructor.</span></span> <span data-ttu-id="8960e-121">私有构造函数可防止类进行实例化。</span><span class="sxs-lookup"><span data-stu-id="8960e-121">A private constructor prevents the class from being instantiated.</span></span> <span data-ttu-id="8960e-122">使用静态类的优点是编译器可以进行检查，以确保不会意外地添加任何实例成员。</span><span class="sxs-lookup"><span data-stu-id="8960e-122">The advantage of using a static class is that the compiler can check to make sure that no instance members are accidentally added.</span></span> <span data-ttu-id="8960e-123">编译器可保证无法创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="8960e-123">The compiler will guarantee that instances of this class cannot be created.</span></span>  
  
 <span data-ttu-id="8960e-124">静态类会进行密封，因此不能继承。</span><span class="sxs-lookup"><span data-stu-id="8960e-124">Static classes are sealed and therefore cannot be inherited.</span></span> <span data-ttu-id="8960e-125">它们不能继承自任何类（除了 <xref:System.Object>）。</span><span class="sxs-lookup"><span data-stu-id="8960e-125">They cannot inherit from any class except <xref:System.Object>.</span></span> <span data-ttu-id="8960e-126">静态类不能包含实例构造函数；但是，它们可以包含静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="8960e-126">Static classes cannot contain an instance constructor; however, they can contain a static constructor.</span></span> <span data-ttu-id="8960e-127">如果类包含需要进行重要初始化的静态成员，则非静态类还应定义静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="8960e-127">Non-static classes should also define a static constructor if the class contains static members that require non-trivial initialization.</span></span> <span data-ttu-id="8960e-128">有关详细信息，请参阅[静态构造函数](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="8960e-128">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8960e-129">示例</span><span class="sxs-lookup"><span data-stu-id="8960e-129">Example</span></span>  
 <span data-ttu-id="8960e-130">下面是静态类的示例，该类包含将温度从摄氏度从华氏度以及从华氏度转换为摄氏度的两个方法：</span><span class="sxs-lookup"><span data-stu-id="8960e-130">Here is an example of a static class that contains two methods that convert temperature from Celsius to Fahrenheit and from Fahrenheit to Celsius:</span></span>  
  
 [!code-csharp[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]  
  
## <a name="static-members"></a><span data-ttu-id="8960e-131">静态成员</span><span class="sxs-lookup"><span data-stu-id="8960e-131">Static Members</span></span>  
 <span data-ttu-id="8960e-132">非静态类可以包含静态方法、字段、属性或事件。</span><span class="sxs-lookup"><span data-stu-id="8960e-132">A non-static class can contain static methods, fields, properties, or events.</span></span> <span data-ttu-id="8960e-133">即使未创建类的任何实例，也可对类调用静态成员。</span><span class="sxs-lookup"><span data-stu-id="8960e-133">The static member is callable on a class even when no instance of the class has been created.</span></span> <span data-ttu-id="8960e-134">静态成员始终按类名（而不是实例名称）进行访问。</span><span class="sxs-lookup"><span data-stu-id="8960e-134">The static member is always accessed by the class name, not the instance name.</span></span> <span data-ttu-id="8960e-135">静态成员只有一个副本存在（与创建的类的实例数有关）。</span><span class="sxs-lookup"><span data-stu-id="8960e-135">Only one copy of a static member exists, regardless of how many instances of the class are created.</span></span> <span data-ttu-id="8960e-136">静态方法和属性无法在其包含类型中访问非静态字段和事件，它们无法访问任何对象的实例变量，除非在方法参数中显式传递它。</span><span class="sxs-lookup"><span data-stu-id="8960e-136">Static methods and properties cannot access non-static fields and events in their containing type, and they cannot access an instance variable of any object unless it is explicitly passed in a method parameter.</span></span>  
  
 <span data-ttu-id="8960e-137">更典型的做法是声明具有一些静态成员的非静态类（而不是将整个类都声明为静态）。</span><span class="sxs-lookup"><span data-stu-id="8960e-137">It is more typical to declare a non-static class with some static members, than to declare an entire class as static.</span></span> <span data-ttu-id="8960e-138">静态字段的两个常见用途是保留已实例化的对象数的计数，或是存储必须在所有实例间共享的值。</span><span class="sxs-lookup"><span data-stu-id="8960e-138">Two common uses of static fields are to keep a count of the number of objects that have been instantiated, or to store a value that must be shared among all instances.</span></span>  
  
 <span data-ttu-id="8960e-139">静态方法可以进行重载，但不能进行替代，因为它们属于类，而不属于类的任何实例。</span><span class="sxs-lookup"><span data-stu-id="8960e-139">Static methods can be overloaded but not overridden, because they belong to the class, and not to any instance of the class.</span></span>  
  
 <span data-ttu-id="8960e-140">虽然字段不能声明为 `static const`，不过 [const](../../../csharp/language-reference/keywords/const.md) 字段在其行为方面本质上是静态的。</span><span class="sxs-lookup"><span data-stu-id="8960e-140">Although a field cannot be declared as `static const`, a [const](../../../csharp/language-reference/keywords/const.md) field is essentially static in its behavior.</span></span> <span data-ttu-id="8960e-141">它属于类型，而不属于类型的实例。</span><span class="sxs-lookup"><span data-stu-id="8960e-141">It belongs to the type, not to instances of the type.</span></span> <span data-ttu-id="8960e-142">因此，可以使用用于静态字段的相同 `ClassName.MemberName` 表示法来访问常量字段。</span><span class="sxs-lookup"><span data-stu-id="8960e-142">Therefore, const fields can be accessed by using the same `ClassName.MemberName` notation that is used for static fields.</span></span> <span data-ttu-id="8960e-143">无需进行对象实例化。</span><span class="sxs-lookup"><span data-stu-id="8960e-143">No object instance is required.</span></span>  
  
 <span data-ttu-id="8960e-144">C# 不支持静态局部变量（在方法范围中声明的变量）。</span><span class="sxs-lookup"><span data-stu-id="8960e-144">C# does not support static local variables (variables that are declared in method scope).</span></span>  
  
 <span data-ttu-id="8960e-145">可在成员的返回类型之前使用 `static` 关键字声明静态类成员，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="8960e-145">You declare static class members by using the `static` keyword before the return type of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]  
  
 <span data-ttu-id="8960e-146">在首次访问静态成员之前以及在调用构造函数（如果有）之前，会初始化静态成员。</span><span class="sxs-lookup"><span data-stu-id="8960e-146">Static members are initialized before the static member is accessed for the first time and before the static constructor, if there is one, is called.</span></span> <span data-ttu-id="8960e-147">若要访问静态类成员，请使用类的名称（而不是变量名称）指定成员的位置，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="8960e-147">To access a static class member, use the name of the class instead of a variable name to specify the location of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]  
  
 <span data-ttu-id="8960e-148">如果类包含静态字段，则提供在类加载时初始化它们的静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="8960e-148">If your class contains static fields, provide a static constructor that initializes them when the class is loaded.</span></span>  
  
 <span data-ttu-id="8960e-149">对静态方法的调用会采用 Microsoft 中间语言 (MSIL) 生成调用指令，而对实例方法的调用会生成 `callvirt` 指令，该指令还会检查是否存在 null 对象引用。</span><span class="sxs-lookup"><span data-stu-id="8960e-149">A call to a static method generates a call instruction in Microsoft intermediate language (MSIL), whereas a call to an instance method generates a `callvirt` instruction, which also checks for a null object references.</span></span> <span data-ttu-id="8960e-150">但是在大多数时候，两者之间的性能差异并不显著。</span><span class="sxs-lookup"><span data-stu-id="8960e-150">However, most of the time the performance difference between the two is not significant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="8960e-151">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="8960e-151">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8960e-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="8960e-152">See Also</span></span>  
 [<span data-ttu-id="8960e-153">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8960e-153">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8960e-154">static</span><span class="sxs-lookup"><span data-stu-id="8960e-154">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
 [<span data-ttu-id="8960e-155">类</span><span class="sxs-lookup"><span data-stu-id="8960e-155">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
 [<span data-ttu-id="8960e-156">class</span><span class="sxs-lookup"><span data-stu-id="8960e-156">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="8960e-157">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="8960e-157">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
 [<span data-ttu-id="8960e-158">实例构造函数</span><span class="sxs-lookup"><span data-stu-id="8960e-158">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)
