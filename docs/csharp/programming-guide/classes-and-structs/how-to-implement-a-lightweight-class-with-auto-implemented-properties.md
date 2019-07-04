---
title: 如何：使用自动实现的属性实现轻量类 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: f9884f353e58ff6119e3bc3b95aa55f0f60d0ad5
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398500"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="7c3c6-102">如何：使用自动实现的属性实现轻量类（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="7c3c6-102">How to: Implement a Lightweight Class with Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="7c3c6-103">本示例演示如何创建一个仅用于封装一组自动实现的属性的不可变轻型类。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-103">This example shows how to create an immutable lightweight class that serves only to encapsulate a set of auto-implemented properties.</span></span> <span data-ttu-id="7c3c6-104">当你必须使用引用类型语义时，请使用此种构造而不是结构。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-104">Use this kind of construct instead of a struct when you must use reference type semantics.</span></span>

<span data-ttu-id="7c3c6-105">可通过两种方法来实现不可变的属性：</span><span class="sxs-lookup"><span data-stu-id="7c3c6-105">You can make an immutable property in two ways:</span></span>
- <span data-ttu-id="7c3c6-106">可以将 [set](../../../csharp/language-reference/keywords/set.md) 访问器声明为[专用](../../../csharp/language-reference/keywords/private.md)。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-106">You can declare the [set](../../../csharp/language-reference/keywords/set.md) accessor to be [private](../../../csharp/language-reference/keywords/private.md).</span></span>  <span data-ttu-id="7c3c6-107">属性只能在该类型中设置，但它对于使用者是不可变的。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-107">The property is only settable within the type, but it is immutable to consumers.</span></span>

  <span data-ttu-id="7c3c6-108">当你声明一个 private `set` 取值函数时，你无法使用对象初始值设定项来初始化属性。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-108">When you declare a private `set` accessor, you cannot use an object initializer to initialize the property.</span></span> <span data-ttu-id="7c3c6-109">你必须使用构造函数或工厂方法。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-109">You must use a constructor or a factory method.</span></span>
- <span data-ttu-id="7c3c6-110">也可以仅声明 [get](../../../csharp/language-reference/keywords/get.md) 访问器，使属性除了能在该类型的构造函数中可变，在其他任何位置都不可变。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-110">You can declare only the [get](../../../csharp/language-reference/keywords/get.md) accessor, which makes the property immutable everywhere except in the type’s constructor.</span></span>

## <a name="example"></a><span data-ttu-id="7c3c6-111">示例</span><span class="sxs-lookup"><span data-stu-id="7c3c6-111">Example</span></span>

<span data-ttu-id="7c3c6-112">下面的示例演示了实现具有自动实现属性的不可变类的两种方法。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-112">The following example shows two ways to implement an immutable class that has auto-implemented properties.</span></span> <span data-ttu-id="7c3c6-113">这两种方法均使用 private `set` 声明其中一个属性，使用单独的 `get` 声明另一个属性。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-113">Each way declares one of the properties with a private `set` and one of the properties with a `get` only.</span></span>  <span data-ttu-id="7c3c6-114">第一个类仅使用构造函数来初始化属性，第二个类则使用可调用构造函数的静态工厂方法。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-114">The first class uses a constructor only to initialize the properties, and the second class uses a static factory method that calls a constructor.</span></span>

```csharp
// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// constructor to initialize its properties.
class Contact
{
    // Read-only properties.
    public string Name { get; }
    public string Address { get; private set; }

    // Public constructor.
    public Contact(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }
}

// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// static method and private constructor to initialize its properties.
public class Contact2
{
    // Read-only properties.
    public string Name { get; private set; }
    public string Address { get; }

    // Private constructor.
    private Contact2(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }

    // Public factory method.
    public static Contact2 CreateContact(string name, string address)
    {
        return new Contact2(name, address);
    }
}

public class Program
{
    static void Main()
    {
        // Some simple data sources.
        string[] names = {"Terry Adams","Fadi Fakhouri", "Hanying Feng",
                            "Cesar Garcia", "Debra Garcia"};
        string[] addresses = {"123 Main St.", "345 Cypress Ave.", "678 1st Ave",
                                "12 108th St.", "89 E. 42nd St."};

        // Simple query to demonstrate object creation in select clause.
        // Create Contact objects by using a constructor.
        var query1 = from i in Enumerable.Range(0, 5)
                    select new Contact(names[i], addresses[i]);

        // List elements cannot be modified by client code.
        var list = query1.ToList();
        foreach (var contact in list)
        {
            Console.WriteLine("{0}, {1}", contact.Name, contact.Address);
        }

        // Create Contact2 objects by using a static factory method.
        var query2 = from i in Enumerable.Range(0, 5)
                        select Contact2.CreateContact(names[i], addresses[i]);

        // Console output is identical to query1.
        var list2 = query2.ToList();

        // List elements cannot be modified by client code.
        // CS0272:
        // list2[0].Name = "Eugene Zabokritski";

        // Keep the console open in debug mode.
        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }
}

/* Output:
    Terry Adams, 123 Main St.
    Fadi Fakhouri, 345 Cypress Ave.
    Hanying Feng, 678 1st Ave
    Cesar Garcia, 12 108th St.
    Debra Garcia, 89 E. 42nd St.
*/
```

<span data-ttu-id="7c3c6-115">编译器为每个自动实现的属性创建了支持字段。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-115">The compiler creates backing fields for each auto-implemented property.</span></span> <span data-ttu-id="7c3c6-116">这些字段无法直接从源代码进行访问。</span><span class="sxs-lookup"><span data-stu-id="7c3c6-116">The fields are not accessible directly from source code.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c3c6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c3c6-117">See also</span></span>

- [<span data-ttu-id="7c3c6-118">属性</span><span class="sxs-lookup"><span data-stu-id="7c3c6-118">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="7c3c6-119">struct</span><span class="sxs-lookup"><span data-stu-id="7c3c6-119">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)
- [<span data-ttu-id="7c3c6-120">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="7c3c6-120">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
