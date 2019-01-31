---
title: 使用委托中的变体 (C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 44a6153a9a1c0aa0aebb18710ea9e770fd4e57fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667266"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="82493-102">使用委托中的变体 (C#)</span><span class="sxs-lookup"><span data-stu-id="82493-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="82493-103">向委托分配方法时，协变和逆变为匹配委托类型和方法签名提供了灵活性。</span><span class="sxs-lookup"><span data-stu-id="82493-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="82493-104">协变允许方法具有的派生返回类型多于委托中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="82493-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="82493-105">逆变允许方法具有的派生参数类型少于委托类型中的类型。</span><span class="sxs-lookup"><span data-stu-id="82493-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="82493-106">示例 1：协变</span><span class="sxs-lookup"><span data-stu-id="82493-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="82493-107">说明</span><span class="sxs-lookup"><span data-stu-id="82493-107">Description</span></span>  
 <span data-ttu-id="82493-108">本示例演示如何将委托与具有返回类型的方法一起使用，这些返回类型派生自委托签名中的返回类型。</span><span class="sxs-lookup"><span data-stu-id="82493-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="82493-109">`DogsHandler` 返回的数据类型属于 `Dogs` 类型，它派生自委托中定义的 `Mammals` 类型。</span><span class="sxs-lookup"><span data-stu-id="82493-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="82493-110">代码</span><span class="sxs-lookup"><span data-stu-id="82493-110">Code</span></span>  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="82493-111">示例 2：逆变</span><span class="sxs-lookup"><span data-stu-id="82493-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="82493-112">说明</span><span class="sxs-lookup"><span data-stu-id="82493-112">Description</span></span>  
 <span data-ttu-id="82493-113">本示例演示如何将委托与具有某个类型的参数的方法一起使用，这些返回类型是委托签名参数类型的基类型。</span><span class="sxs-lookup"><span data-stu-id="82493-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="82493-114">通过逆变可以使用一个事件处理程序而不是多个单独的处理程序。</span><span class="sxs-lookup"><span data-stu-id="82493-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="82493-115">例如，可以创建接受 `EventArgs` 输入参数的事件处理程序，并将其与将 `MouseEventArgs` 类型作为参数发送的 `Button.MouseClick` 事件一起使用，也可以将其与发送 `KeyEventArgs` 参数的 `TextBox.KeyDown` 事件一起使用。</span><span class="sxs-lookup"><span data-stu-id="82493-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="82493-116">代码</span><span class="sxs-lookup"><span data-stu-id="82493-116">Code</span></span>  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method   
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="82493-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="82493-117">See also</span></span>

- [<span data-ttu-id="82493-118">委托中的变体 (C#)</span><span class="sxs-lookup"><span data-stu-id="82493-118">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="82493-119">对 Func 和 Action 泛型委托使用变体 (C#)</span><span class="sxs-lookup"><span data-stu-id="82493-119">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
