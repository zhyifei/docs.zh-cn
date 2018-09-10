---
title: 在泛型集合的接口中使用变体 (C#)
ms.date: 07/20/2015
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
ms.openlocfilehash: 66a1eac33d5f715f52bd83c43bac4452df41aabd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44196941"
---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a><span data-ttu-id="87fc6-102">在泛型集合的接口中使用变体 (C#)</span><span class="sxs-lookup"><span data-stu-id="87fc6-102">Using Variance in Interfaces for Generic Collections (C#)</span></span>
<span data-ttu-id="87fc6-103">协变接口允许其方法返回的派生类型多于接口中指定的派生类型。</span><span class="sxs-lookup"><span data-stu-id="87fc6-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="87fc6-104">逆变接口允许其方法接受派生类型少于接口中指定的类型的参数。</span><span class="sxs-lookup"><span data-stu-id="87fc6-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="87fc6-105">在.NET Framework 4 中，多个现有接口已变为协变和逆变接口。</span><span class="sxs-lookup"><span data-stu-id="87fc6-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="87fc6-106">包括 <xref:System.Collections.Generic.IEnumerable%601> 和 <xref:System.IComparable%601>。</span><span class="sxs-lookup"><span data-stu-id="87fc6-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="87fc6-107">这使你可将对基类型的泛型集合进行操作的那些方法重用于派生类型的集合。</span><span class="sxs-lookup"><span data-stu-id="87fc6-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="87fc6-108">有关 .NET Framework 中变体接口的列表，请参阅[泛型接口中的变体 (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="87fc6-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="87fc6-109">转换泛型集合</span><span class="sxs-lookup"><span data-stu-id="87fc6-109">Converting Generic Collections</span></span>  
 <span data-ttu-id="87fc6-110">下例阐释了 <xref:System.Collections.Generic.IEnumerable%601> 接口中的协变支持的益处。</span><span class="sxs-lookup"><span data-stu-id="87fc6-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="87fc6-111">`PrintFullName` 方法接受 `IEnumerable<Person>` 类型的集合作为参数。</span><span class="sxs-lookup"><span data-stu-id="87fc6-111">The `PrintFullName` method accepts a collection of the `IEnumerable<Person>` type as a parameter.</span></span> <span data-ttu-id="87fc6-112">但可将该方法重用于 `IEnumerable<Employee>` 类型的集合，因为 `Employee` 继承 `Person`。</span><span class="sxs-lookup"><span data-stu-id="87fc6-112">However, you can reuse it for a collection of the `IEnumerable<Employee>` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,   
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a><span data-ttu-id="87fc6-113">比较泛型集合</span><span class="sxs-lookup"><span data-stu-id="87fc6-113">Comparing Generic Collections</span></span>  
 <span data-ttu-id="87fc6-114">下例阐释了 <xref:System.Collections.Generic.IComparer%601> 接口中的逆变支持的益处。</span><span class="sxs-lookup"><span data-stu-id="87fc6-114">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="87fc6-115">`PersonComparer` 类实现 `IComparer<Person>` 接口。</span><span class="sxs-lookup"><span data-stu-id="87fc6-115">The `PersonComparer` class implements the `IComparer<Person>` interface.</span></span> <span data-ttu-id="87fc6-116">但可以重用此类来比较 `Employee` 类型的对象序列，因为 `Employee` 继承 `Person`。</span><span class="sxs-lookup"><span data-stu-id="87fc6-116">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {              
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;              
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,   
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="87fc6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="87fc6-117">See Also</span></span>

- [<span data-ttu-id="87fc6-118">泛型接口中的变体 (C#)</span><span class="sxs-lookup"><span data-stu-id="87fc6-118">Variance in Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
