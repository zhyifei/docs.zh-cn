---
title: 了解何时使用 Override 和 New 关键字（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- override keyword [C#]
- new keyword [C#]
- polymorphism [C#], using override and new [C#]
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
ms.openlocfilehash: 61bfa87b7aaa7c17d4ba67c69fa1e57ee7415dc0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340263"
---
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a><span data-ttu-id="5712e-102">了解何时使用 Override 和 New 关键字（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5712e-102">Knowing When to Use Override and New Keywords (C# Programming Guide)</span></span>
<span data-ttu-id="5712e-103">在 C# 中，派生类中的方法可具有与基类中的方法相同的名称。</span><span class="sxs-lookup"><span data-stu-id="5712e-103">In C#, a method in a derived class can have the same name as a method in the base class.</span></span> <span data-ttu-id="5712e-104">可使用 [new](../../../csharp/language-reference/keywords/new.md) 和 [override](../../../csharp/language-reference/keywords/override.md) 关键字指定方法的交互方式。</span><span class="sxs-lookup"><span data-stu-id="5712e-104">You can specify how the methods interact by using the [new](../../../csharp/language-reference/keywords/new.md) and [override](../../../csharp/language-reference/keywords/override.md) keywords.</span></span> <span data-ttu-id="5712e-105">`override` 修饰符用于扩展基类方法，而 `new` 修饰符则用于隐藏该方法。</span><span class="sxs-lookup"><span data-stu-id="5712e-105">The `override` modifier *extends* the base class method, and the `new` modifier *hides* it.</span></span> <span data-ttu-id="5712e-106">本主题中的示例阐释了这种差异。</span><span class="sxs-lookup"><span data-stu-id="5712e-106">The difference is illustrated in the examples in this topic.</span></span>  
  
 <span data-ttu-id="5712e-107">在控制台应用程序中，声明以下两个类：`BaseClass` 和 `DerivedClass`。</span><span class="sxs-lookup"><span data-stu-id="5712e-107">In a console application, declare the following two classes, `BaseClass` and `DerivedClass`.</span></span> <span data-ttu-id="5712e-108">`DerivedClass` 继承自 `BaseClass`。</span><span class="sxs-lookup"><span data-stu-id="5712e-108">`DerivedClass` inherits from `BaseClass`.</span></span>  
  
```csharp  
class BaseClass  
{  
    public void Method1()  
    {  
        Console.WriteLine("Base - Method1");  
    }  
}  
  
class DerivedClass : BaseClass  
{  
    public void Method2()  
    {  
        Console.WriteLine("Derived - Method2");  
    }  
}  
```  
  
 <span data-ttu-id="5712e-109">在 `Main` 方法中，声明变量 `bc`、`dc` 和 `bcdc`。</span><span class="sxs-lookup"><span data-stu-id="5712e-109">In the `Main` method, declare variables `bc`, `dc`, and `bcdc`.</span></span>  
  
-   <span data-ttu-id="5712e-110">`bc` 为 `BaseClass` 类型，其值为 `BaseClass` 类型。</span><span class="sxs-lookup"><span data-stu-id="5712e-110">`bc` is of type `BaseClass`, and its value is of type `BaseClass`.</span></span>  
  
-   <span data-ttu-id="5712e-111">`dc` 为 `DerivedClass` 类型，其值为 `DerivedClass` 类型。</span><span class="sxs-lookup"><span data-stu-id="5712e-111">`dc` is of type `DerivedClass`, and its value is of type `DerivedClass`.</span></span>  
  
-   <span data-ttu-id="5712e-112">`bcdc` 为 `BaseClass` 类型，其值为 `DerivedClass` 类型。</span><span class="sxs-lookup"><span data-stu-id="5712e-112">`bcdc` is of type `BaseClass`, and its value is of type `DerivedClass`.</span></span> <span data-ttu-id="5712e-113">需注意此变量。</span><span class="sxs-lookup"><span data-stu-id="5712e-113">This is the variable to pay attention to.</span></span>  
  
 <span data-ttu-id="5712e-114">由于 `bc` 和 `bcdc` 具有 `BaseClass` 类型，因此它们只能直接访问 `Method1`，除非使用强制转换。</span><span class="sxs-lookup"><span data-stu-id="5712e-114">Because `bc` and `bcdc` have type `BaseClass`, they can only directly access `Method1`, unless you use casting.</span></span> <span data-ttu-id="5712e-115">变量 `dc` 可同时访问 `Method1` 和 `Method2`。</span><span class="sxs-lookup"><span data-stu-id="5712e-115">Variable `dc` can access both `Method1` and `Method2`.</span></span> <span data-ttu-id="5712e-116">下面的代码演示了这些关系。</span><span class="sxs-lookup"><span data-stu-id="5712e-116">These relationships are shown in the following code.</span></span>  
  
```csharp  
class Program  
{  
    static void Main(string[] args)  
    {  
        BaseClass bc = new BaseClass();  
        DerivedClass dc = new DerivedClass();  
        BaseClass bcdc = new DerivedClass();  
  
        bc.Method1();  
        dc.Method1();  
        dc.Method2();  
        bcdc.Method1();  
    }  
    // Output:  
    // Base - Method1  
    // Base - Method1  
    // Derived - Method2  
    // Base - Method1  
}  
```  
  
 <span data-ttu-id="5712e-117">接着，将以下 `Method2` 方法添加到 `BaseClass`。</span><span class="sxs-lookup"><span data-stu-id="5712e-117">Next, add the following `Method2` method to `BaseClass`.</span></span> <span data-ttu-id="5712e-118">此方法的签名与 `DerivedClass` 中 `Method2` 方法的签名匹配。</span><span class="sxs-lookup"><span data-stu-id="5712e-118">The signature of this method matches the signature of the `Method2` method in `DerivedClass`.</span></span>  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 <span data-ttu-id="5712e-119">由于 `BaseClass` 现在具有 `Method2` 方法，因此可以为 `BaseClass` 变量 `bc` 和 `bcdc` 添加第二个调用语句，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="5712e-119">Because `BaseClass` now has a `Method2` method, a second calling statement can be added for `BaseClass` variables `bc` and `bcdc`, as shown in the following code.</span></span>  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 <span data-ttu-id="5712e-120">当生成项目时，你将看到在 `BaseClass` 中添加 `Method2` 方法将引发警告。</span><span class="sxs-lookup"><span data-stu-id="5712e-120">When you build the project, you see that the addition of the `Method2` method in `BaseClass` causes a warning.</span></span> <span data-ttu-id="5712e-121">警告显示 `DerivedClass` 中的 `Method2` 方法隐藏了 `BaseClass` 中的 `Method2` 方法。</span><span class="sxs-lookup"><span data-stu-id="5712e-121">The warning says that the `Method2` method in `DerivedClass` hides the `Method2` method in `BaseClass`.</span></span> <span data-ttu-id="5712e-122">如果希望获得该结果，则建议使用 `Method2` 定义中的 `new` 关键字。</span><span class="sxs-lookup"><span data-stu-id="5712e-122">You are advised to use the `new` keyword in the `Method2` definition if you intend to cause that result.</span></span> <span data-ttu-id="5712e-123">或者，可重命名 `Method2` 方法之一来消除警告，但这始终不实用。</span><span class="sxs-lookup"><span data-stu-id="5712e-123">Alternatively, you could rename one of the `Method2` methods to resolve the warning, but that is not always practical.</span></span>  
  
 <span data-ttu-id="5712e-124">添加 `new` 之前，请运行程序，查看其他调用语句生成的输出。</span><span class="sxs-lookup"><span data-stu-id="5712e-124">Before adding `new`, run the program to see the output produced by the additional calling statements.</span></span> <span data-ttu-id="5712e-125">显示以下结果。</span><span class="sxs-lookup"><span data-stu-id="5712e-125">The following results are displayed.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="5712e-126">`new` 关键字可以保留生成该输出的关系，但它会禁止显示警告。</span><span class="sxs-lookup"><span data-stu-id="5712e-126">The `new` keyword preserves the relationships that produce that output, but it suppresses the warning.</span></span> <span data-ttu-id="5712e-127">具有 `BaseClass` 类型的变量继续访问 `BaseClass` 的成员，而具有 `DerivedClass` 类型的变量首先继续访问 `DerivedClass` 中的成员，然后再考虑从 `BaseClass` 继承的成员。</span><span class="sxs-lookup"><span data-stu-id="5712e-127">The variables that have type `BaseClass` continue to access the members of `BaseClass`, and the variable that has type `DerivedClass` continues to access members in `DerivedClass` first, and then to consider members inherited from `BaseClass`.</span></span>  
  
 <span data-ttu-id="5712e-128">若要禁止显示警告，请将 `new` 修饰符添加到 `DerivedClass` 中的 `Method2` 定义，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="5712e-128">To suppress the warning, add the `new` modifier to the definition of `Method2` in `DerivedClass`, as shown in the following code.</span></span> <span data-ttu-id="5712e-129">可在 `public` 前后添加修饰符。</span><span class="sxs-lookup"><span data-stu-id="5712e-129">The modifier can be added before or after `public`.</span></span>  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 <span data-ttu-id="5712e-130">再次运行该程序，确认输出未发生更改。</span><span class="sxs-lookup"><span data-stu-id="5712e-130">Run the program again to verify that the output has not changed.</span></span> <span data-ttu-id="5712e-131">此外，确认不再显示警告。</span><span class="sxs-lookup"><span data-stu-id="5712e-131">Also verify that the warning no longer appears.</span></span> <span data-ttu-id="5712e-132">通过使用 `new`，断言你知道它修饰的成员将隐藏从基类继承的成员。</span><span class="sxs-lookup"><span data-stu-id="5712e-132">By using `new`, you are asserting that you are aware that the member that it modifies hides a member that is inherited from the base class.</span></span> <span data-ttu-id="5712e-133">有关通过继承隐藏名称的详细信息，请参阅 [new 修饰符](../../../csharp/language-reference/keywords/new-modifier.md)。</span><span class="sxs-lookup"><span data-stu-id="5712e-133">For more information about name hiding through inheritance, see [new Modifier](../../../csharp/language-reference/keywords/new-modifier.md).</span></span>  
  
 <span data-ttu-id="5712e-134">若要将此行为与使用 `override` 的效果进行对比，请将以下方法添加到 `DerivedClass`。</span><span class="sxs-lookup"><span data-stu-id="5712e-134">To contrast this behavior to the effects of using `override`, add the following method to `DerivedClass`.</span></span> <span data-ttu-id="5712e-135">可在 `public` 前后添加 `override` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="5712e-135">The `override` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 <span data-ttu-id="5712e-136">将 `virtual` 修饰符添加到 `BaseClass` 中的 `Method1` 定义。</span><span class="sxs-lookup"><span data-stu-id="5712e-136">Add the `virtual` modifier to the definition of `Method1` in `BaseClass`.</span></span> <span data-ttu-id="5712e-137">可在 `public` 前后添加 `virtual` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="5712e-137">The `virtual` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 <span data-ttu-id="5712e-138">再次运行该项目。</span><span class="sxs-lookup"><span data-stu-id="5712e-138">Run the project again.</span></span> <span data-ttu-id="5712e-139">尤其注意以下输出的最后两行。</span><span class="sxs-lookup"><span data-stu-id="5712e-139">Notice especially the last two lines of the following output.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="5712e-140">使用 `override` 修饰符可使 `bcdc` 访问 `DerivedClass` 中定义的 `Method1` 方法。</span><span class="sxs-lookup"><span data-stu-id="5712e-140">The use of the `override` modifier enables `bcdc` to access the `Method1` method that is defined in `DerivedClass`.</span></span> <span data-ttu-id="5712e-141">通常，这是继承层次结构中所需的行为。</span><span class="sxs-lookup"><span data-stu-id="5712e-141">Typically, that is the desired behavior in inheritance hierarchies.</span></span> <span data-ttu-id="5712e-142">让具有从派生类创建的值的对象使用派生类中定义的方法。</span><span class="sxs-lookup"><span data-stu-id="5712e-142">You want objects that have values that are created from the derived class to use the methods that are defined in the derived class.</span></span> <span data-ttu-id="5712e-143">可使用 `override` 扩展基类方法实现该行为。</span><span class="sxs-lookup"><span data-stu-id="5712e-143">You achieve that behavior by using `override` to extend the base class method.</span></span>  
  
 <span data-ttu-id="5712e-144">下面的代码包括完整的示例。</span><span class="sxs-lookup"><span data-stu-id="5712e-144">The following code contains the full example.</span></span>  
  
```csharp  
using System;  
using System.Text;  
  
namespace OverrideAndNew  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BaseClass bc = new BaseClass();  
            DerivedClass dc = new DerivedClass();  
            BaseClass bcdc = new DerivedClass();  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in BaseClass.  
            bc.Method1();  
            bc.Method2();  
            // Output:  
            // Base - Method1  
            // Base - Method2  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in DerivedClass.  
            dc.Method1();  
            dc.Method2();  
            // Output:  
            // Derived - Method1  
            // Derived - Method2  
  
            // The following two calls produce different results, depending   
            // on whether override (Method1) or new (Method2) is used.  
            bcdc.Method1();  
            bcdc.Method2();  
            // Output:  
            // Derived - Method1  
            // Base - Method2  
        }  
    }  
  
    class BaseClass  
    {  
        public virtual void Method1()  
        {  
            Console.WriteLine("Base - Method1");  
        }  
  
        public virtual void Method2()  
        {  
            Console.WriteLine("Base - Method2");  
        }  
    }  
  
    class DerivedClass : BaseClass  
    {  
        public override void Method1()  
        {  
            Console.WriteLine("Derived - Method1");  
        }  
  
        public new void Method2()  
        {  
            Console.WriteLine("Derived - Method2");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="5712e-145">下列阐释了不同上下文中的类似行为。</span><span class="sxs-lookup"><span data-stu-id="5712e-145">The following example illustrates similar behavior in a different context.</span></span> <span data-ttu-id="5712e-146">该示例定义了三个类：一个名为 `Car` 的基类和两个由其派生的 `ConvertibleCar` 和 `Minivan`。</span><span class="sxs-lookup"><span data-stu-id="5712e-146">The example defines three classes: a base class named `Car` and two classes that are derived from it, `ConvertibleCar` and `Minivan`.</span></span> <span data-ttu-id="5712e-147">基类中包含 `DescribeCar` 方法。</span><span class="sxs-lookup"><span data-stu-id="5712e-147">The base class contains a `DescribeCar` method.</span></span> <span data-ttu-id="5712e-148">该方法给出了对一辆车的基本描述，然后调用 `ShowDetails` 提供其他信息。</span><span class="sxs-lookup"><span data-stu-id="5712e-148">The method displays a basic description of a car, and then calls `ShowDetails` to provide additional information.</span></span> <span data-ttu-id="5712e-149">这三个类中的每一个类都定义了 `ShowDetails` 方法。</span><span class="sxs-lookup"><span data-stu-id="5712e-149">Each of the three classes defines a `ShowDetails` method.</span></span> <span data-ttu-id="5712e-150">`new` 修饰符用于定义 `ConvertibleCar` 类中的 `ShowDetails`。</span><span class="sxs-lookup"><span data-stu-id="5712e-150">The `new` modifier is used to define `ShowDetails` in the `ConvertibleCar` class.</span></span> <span data-ttu-id="5712e-151">`override` 修饰符用于定义 `Minivan` 类中的 `ShowDetails`。</span><span class="sxs-lookup"><span data-stu-id="5712e-151">The `override` modifier is used to define `ShowDetails` in the `Minivan` class.</span></span>  
  
```csharp  
// Define the base class, Car. The class defines two methods,  
// DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
// class also defines a ShowDetails method. The example tests which version of  
// ShowDetails is selected, the base class method or the derived class method.  
class Car  
{  
    public void DescribeCar()  
    {  
        System.Console.WriteLine("Four wheels and an engine.");  
        ShowDetails();  
    }  
  
    public virtual void ShowDetails()  
    {  
        System.Console.WriteLine("Standard transportation.");  
    }  
}  
  
// Define the derived classes.  
  
// Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
// hides the base class method.  
class ConvertibleCar : Car  
{  
    public new void ShowDetails()  
    {  
        System.Console.WriteLine("A roof that opens up.");  
    }  
}  
  
// Class Minivan uses the override modifier to specify that ShowDetails  
// extends the base class method.  
class Minivan : Car  
{  
    public override void ShowDetails()  
    {  
        System.Console.WriteLine("Carries seven people.");  
    }  
}  
```  
  
 <span data-ttu-id="5712e-152">该示例测试被调用的 `ShowDetails` 版本。</span><span class="sxs-lookup"><span data-stu-id="5712e-152">The example tests which version of `ShowDetails` is called.</span></span> <span data-ttu-id="5712e-153">下面的方法 `TestCars1` 为每个类声明了一个实例，并在每个实例上调用 `DescribeCar`。</span><span class="sxs-lookup"><span data-stu-id="5712e-153">The following method, `TestCars1`, declares an instance of each class, and then calls `DescribeCar` on each instance.</span></span>  
  
```csharp  
public static void TestCars1()  
{  
    System.Console.WriteLine("\nTestCars1");  
    System.Console.WriteLine("----------");  
  
    Car car1 = new Car();  
    car1.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    // Notice the output from this test case. The new modifier is  
    // used in the definition of ShowDetails in the ConvertibleCar  
    // class.    
  
    ConvertibleCar car2 = new ConvertibleCar();  
    car2.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    Minivan car3 = new Minivan();  
    car3.DescribeCar();  
    System.Console.WriteLine("----------");  
}  
```  
  
 <span data-ttu-id="5712e-154">`TestCars1` 将生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="5712e-154">`TestCars1` produces the following output.</span></span> <span data-ttu-id="5712e-155">请特别注意 `car2` 的结果，该结果可能不是你需要的内容。</span><span class="sxs-lookup"><span data-stu-id="5712e-155">Notice especially the results for `car2`, which probably are not what you expected.</span></span> <span data-ttu-id="5712e-156">对象的类型是 `ConvertibleCar`，但 `DescribeCar` 不会访问 `ConvertibleCar` 类中定义的 `ShowDetails` 版本，因为方法已声明包含 `new` 修饰符声明，而不是 `override` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="5712e-156">The type of the object is `ConvertibleCar`, but `DescribeCar` does not access the version of `ShowDetails` that is defined in the `ConvertibleCar` class because that method is declared with the `new` modifier, not the `override` modifier.</span></span> <span data-ttu-id="5712e-157">因此，`ConvertibleCar` 对象与 `Car` 对象显示的说明相同。</span><span class="sxs-lookup"><span data-stu-id="5712e-157">As a result, a `ConvertibleCar` object displays the same description as a `Car` object.</span></span> <span data-ttu-id="5712e-158">比较 `car3` 的结果，这是一个 `Minivan` 对象。</span><span class="sxs-lookup"><span data-stu-id="5712e-158">Contrast the results for `car3`, which is a `Minivan` object.</span></span> <span data-ttu-id="5712e-159">在这种情况下，`Minivan` 类中声明的 `ShowDetails` 方法会替代 `Car` 类中声明的 `ShowDetails` 方法，显示的说明描述小型货车。</span><span class="sxs-lookup"><span data-stu-id="5712e-159">In this case, the `ShowDetails` method that is declared in the `Minivan` class overrides the `ShowDetails` method that is declared in the `Car` class, and the description that is displayed describes a minivan.</span></span>  
  
```csharp  
// TestCars1  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 <span data-ttu-id="5712e-160">`TestCars2` 创建具有 `Car` 类型的对象列表。</span><span class="sxs-lookup"><span data-stu-id="5712e-160">`TestCars2` creates a list of objects that have type `Car`.</span></span> <span data-ttu-id="5712e-161">对象的值由 `Car` 类、`ConvertibleCar` 类和 `Minivan` 类实例化所得。</span><span class="sxs-lookup"><span data-stu-id="5712e-161">The values of the objects are instantiated from the `Car`, `ConvertibleCar`, and `Minivan` classes.</span></span> <span data-ttu-id="5712e-162">对列表中的每个元素调用 `DescribeCar`。</span><span class="sxs-lookup"><span data-stu-id="5712e-162">`DescribeCar` is called on each element of the list.</span></span> <span data-ttu-id="5712e-163">以下代码显示 `TestCars2` 的定义。</span><span class="sxs-lookup"><span data-stu-id="5712e-163">The following code shows the definition of `TestCars2`.</span></span>  
  
```csharp  
public static void TestCars2()  
{  
    System.Console.WriteLine("\nTestCars2");  
    System.Console.WriteLine("----------");  
  
    var cars = new List<Car> { new Car(), new ConvertibleCar(),   
        new Minivan() };  
  
    foreach (var car in cars)  
    {  
        car.DescribeCar();  
        System.Console.WriteLine("----------");  
    }  
}  
```  
  
 <span data-ttu-id="5712e-164">显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="5712e-164">The following output is displayed.</span></span> <span data-ttu-id="5712e-165">请注意，它与 `TestCars1` 显示的输出相同。</span><span class="sxs-lookup"><span data-stu-id="5712e-165">Notice that it is the same as the output that is displayed by `TestCars1`.</span></span> <span data-ttu-id="5712e-166">不调用 `ConvertibleCar` 类的 `ShowDetails` 方法，不管该对象的类型是 `ConvertibleCar`（在 `TestCars1` 中）还是 `Car`（在 `TestCars2` 中）。</span><span class="sxs-lookup"><span data-stu-id="5712e-166">The `ShowDetails` method of the `ConvertibleCar` class is not called, regardless of whether the type of the object is `ConvertibleCar`, as in `TestCars1`, or `Car`, as in `TestCars2`.</span></span> <span data-ttu-id="5712e-167">相反，在这两种情况下，`car3` 从 `Minivan` 调用 `ShowDetails` 方法，不管它拥有类型 `Minivan` 还是类型 `Car`。</span><span class="sxs-lookup"><span data-stu-id="5712e-167">Conversely, `car3` calls the `ShowDetails` method from the `Minivan` class in both cases, whether it has type `Minivan` or type `Car`.</span></span>  
  
```csharp  
// TestCars2  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 <span data-ttu-id="5712e-168">方法 `TestCars3` 和方法 `TestCars4` 完成示例。</span><span class="sxs-lookup"><span data-stu-id="5712e-168">Methods `TestCars3` and `TestCars4` complete the example.</span></span> <span data-ttu-id="5712e-169">这些方法直接调用 `ShowDetails`，先从声明具有类型 `ConvertibleCar` 和 `Minivan` (`TestCars3`) 的对象开始，然后再转到声明具有类型 `Car` (`TestCars4`) 的对象。</span><span class="sxs-lookup"><span data-stu-id="5712e-169">These methods call `ShowDetails` directly, first from objects declared to have type `ConvertibleCar` and `Minivan` (`TestCars3`), then from objects declared to have type `Car` (`TestCars4`).</span></span> <span data-ttu-id="5712e-170">以下代码定义了这两种方法。</span><span class="sxs-lookup"><span data-stu-id="5712e-170">The following code defines these two methods.</span></span>  
  
```csharp  
public static void TestCars3()  
{  
    System.Console.WriteLine("\nTestCars3");  
    System.Console.WriteLine("----------");  
    ConvertibleCar car2 = new ConvertibleCar();  
    Minivan car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
  
public static void TestCars4()  
{  
    System.Console.WriteLine("\nTestCars4");  
    System.Console.WriteLine("----------");  
    Car car2 = new ConvertibleCar();  
    Car car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
```  
  
 <span data-ttu-id="5712e-171">这两种方法将产生以下输出，输出对应本主题第一个示例的结果。</span><span class="sxs-lookup"><span data-stu-id="5712e-171">The methods produce the following output, which corresponds to the results from the first example in this topic.</span></span>  
  
```csharp  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
```  
  
 <span data-ttu-id="5712e-172">以下代码显示了完整项目及其输出。</span><span class="sxs-lookup"><span data-stu-id="5712e-172">The following code shows the complete project and its output.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
namespace OverrideAndNew2  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Declare objects of the derived classes and test which version  
            // of ShowDetails is run, base or derived.  
            TestCars1();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars2();  
  
            // Declare objects of the derived classes and call ShowDetails  
            // directly.  
            TestCars3();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars4();  
        }  
  
        public static void TestCars1()  
        {  
            System.Console.WriteLine("\nTestCars1");  
            System.Console.WriteLine("----------");  
  
            Car car1 = new Car();  
            car1.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            // Notice the output from this test case. The new modifier is  
            // used in the definition of ShowDetails in the ConvertibleCar  
            // class.    
            ConvertibleCar car2 = new ConvertibleCar();  
            car2.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            Minivan car3 = new Minivan();  
            car3.DescribeCar();  
            System.Console.WriteLine("----------");  
        }  
        // Output:  
        // TestCars1  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars2()  
        {  
            System.Console.WriteLine("\nTestCars2");  
            System.Console.WriteLine("----------");  
  
            var cars = new List<Car> { new Car(), new ConvertibleCar(),   
                new Minivan() };  
  
            foreach (var car in cars)  
            {  
                car.DescribeCar();  
                System.Console.WriteLine("----------");  
            }  
        }  
        // Output:  
        // TestCars2  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars3()  
        {  
            System.Console.WriteLine("\nTestCars3");  
            System.Console.WriteLine("----------");  
            ConvertibleCar car2 = new ConvertibleCar();  
            Minivan car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars3  
        // ----------  
        // A roof that opens up.  
        // Carries seven people.  
  
        public static void TestCars4()  
        {  
            System.Console.WriteLine("\nTestCars4");  
            System.Console.WriteLine("----------");  
            Car car2 = new ConvertibleCar();  
            Car car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars4  
        // ----------  
        // Standard transportation.  
        // Carries seven people.  
    }  
  
    // Define the base class, Car. The class defines two virtual methods,  
    // DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
    // class also defines a ShowDetails method. The example tests which version of  
    // ShowDetails is used, the base class method or the derived class method.  
    class Car  
    {  
        public virtual void DescribeCar()  
        {  
            System.Console.WriteLine("Four wheels and an engine.");  
            ShowDetails();  
        }  
  
        public virtual void ShowDetails()  
        {  
            System.Console.WriteLine("Standard transportation.");  
        }  
    }  
  
    // Define the derived classes.  
  
    // Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
    // hides the base class method.  
    class ConvertibleCar : Car  
    {  
        public new void ShowDetails()  
        {  
            System.Console.WriteLine("A roof that opens up.");  
        }  
    }  
  
    // Class Minivan uses the override modifier to specify that ShowDetails  
    // extends the base class method.  
    class Minivan : Car  
    {  
        public override void ShowDetails()  
        {  
            System.Console.WriteLine("Carries seven people.");  
        }  
    }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5712e-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="5712e-173">See Also</span></span>  
 [<span data-ttu-id="5712e-174">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5712e-174">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5712e-175">类和结构</span><span class="sxs-lookup"><span data-stu-id="5712e-175">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="5712e-176">使用 Override 和 New 关键字进行版本控制</span><span class="sxs-lookup"><span data-stu-id="5712e-176">Versioning with the Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)  
 [<span data-ttu-id="5712e-177">base</span><span class="sxs-lookup"><span data-stu-id="5712e-177">base</span></span>](../../../csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="5712e-178">abstract</span><span class="sxs-lookup"><span data-stu-id="5712e-178">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)
