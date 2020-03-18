---
title: 对 Func 和 Action 泛型委托使用变体 (C#)
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: 17f55d594ad4364fd29c8f6e41bd6ad2445b0986
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169787"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a><span data-ttu-id="deb69-102">对 Func 和 Action 泛型委托使用变体 (C#)</span><span class="sxs-lookup"><span data-stu-id="deb69-102">Using Variance for Func and Action Generic Delegates (C#)</span></span>
<span data-ttu-id="deb69-103">这些示例演示如何使用 `Func` 和 `Action` 泛型委托中的协变和逆变来启用重用方法并为代码中提供更多的灵活性。</span><span class="sxs-lookup"><span data-stu-id="deb69-103">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="deb69-104">有关协变和逆变的详细信息，请参阅[委托中的变体 (C#)](./variance-in-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="deb69-104">For more information about covariance and contravariance, see [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="deb69-105">使用具有协变类型参数的委托</span><span class="sxs-lookup"><span data-stu-id="deb69-105">Using Delegates with Covariant Type Parameters</span></span>  
 <span data-ttu-id="deb69-106">下例阐释了泛型 `Func` 委托中的协变支持的益处。</span><span class="sxs-lookup"><span data-stu-id="deb69-106">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="deb69-107">`FindByTitle` 方法采用 `String` 类型的一个参数，并返回 `Employee` 类型的一个对象。</span><span class="sxs-lookup"><span data-stu-id="deb69-107">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="deb69-108">但是，可将此方法分配给 `Func<String, Person>` 委托，因为 `Employee` 继承 `Person`。</span><span class="sxs-lookup"><span data-stu-id="deb69-108">However, you can assign this method to the `Func<String, Person>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static Employee FindByTitle(String title)  
    {  
        // This is a stub for a method that returns  
        // an employee that has the specified title.  
        return new Employee();  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Func<String, Employee> findEmployee = FindByTitle;  
  
        // The delegate expects a method to return Person,  
        // but you can assign it a method that returns Employee.  
        Func<String, Person> findPerson = FindByTitle;  
  
        // You can also assign a delegate
        // that returns a more derived type
        // to a delegate that returns a less derived type.  
        findPerson = findEmployee;  
  
    }  
}  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="deb69-109">使用具有逆变类型参数的委托</span><span class="sxs-lookup"><span data-stu-id="deb69-109">Using Delegates with Contravariant Type Parameters</span></span>  
 <span data-ttu-id="deb69-110">下例阐释了泛型 `Action` 委托中的逆变支持的益处。</span><span class="sxs-lookup"><span data-stu-id="deb69-110">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="deb69-111">`AddToContacts` 方法采用 `Person` 类型的一个参数。</span><span class="sxs-lookup"><span data-stu-id="deb69-111">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="deb69-112">但是，可将此方法分配给 `Action<Employee>` 委托，因为 `Employee` 继承 `Person`。</span><span class="sxs-lookup"><span data-stu-id="deb69-112">However, you can assign this method to the `Action<Employee>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static void AddToContacts(Person person)  
    {  
        // This method adds a Person object  
        // to a contact list.  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Action<Person> addPersonToContacts = AddToContacts;  
  
        // The Action delegate expects
        // a method that has an Employee parameter,  
        // but you can assign it a method that has a Person parameter  
        // because Employee derives from Person.  
        Action<Employee> addEmployeeToContacts = AddToContacts;  
  
        // You can also assign a delegate
        // that accepts a less derived parameter to a delegate
        // that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="deb69-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="deb69-113">See also</span></span>

- [<span data-ttu-id="deb69-114">协变和逆变 (C#)</span><span class="sxs-lookup"><span data-stu-id="deb69-114">Covariance and Contravariance (C#)</span></span>](./index.md)
- [<span data-ttu-id="deb69-115">泛型</span><span class="sxs-lookup"><span data-stu-id="deb69-115">Generics</span></span>](../../../../standard/generics/index.md)
