---
title: 保护异常处理
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 256d9c9b825081e3bcfafd6e0e09de825d046d20
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894544"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="09e15-102">保护异常处理</span><span class="sxs-lookup"><span data-stu-id="09e15-102">Securing Exception Handling</span></span>
<span data-ttu-id="09e15-103">在 Visual C++和 Visual Basic 中，堆栈中的一个筛选器表达式将在任何**finally**语句之前运行。</span><span class="sxs-lookup"><span data-stu-id="09e15-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="09e15-104">与该筛选器相关联的**catch**块在**finally**语句之后运行。</span><span class="sxs-lookup"><span data-stu-id="09e15-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="09e15-105">有关详细信息，请参阅[使用用户筛选的异常](../../standard/exceptions/using-user-filtered-exception-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="09e15-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="09e15-106">本部分将介绍此顺序的安全隐患。</span><span class="sxs-lookup"><span data-stu-id="09e15-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="09e15-107">请考虑以下伪代码示例，该示例演示 filter 语句和**finally**语句的运行顺序。</span><span class="sxs-lookup"><span data-stu-id="09e15-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
```cpp  
void Main()   
{  
    try   
    {  
        Sub();  
    }   
    except (Filter())   
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()   
{  
    try   
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }   
    finally   
    {  
        Console.WriteLine("finally");  
    }  
}                        
```  
  
 <span data-ttu-id="09e15-108">此代码将打印以下代码。</span><span class="sxs-lookup"><span data-stu-id="09e15-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="09e15-109">该筛选器在**finally**语句之前运行，因此，在执行其他代码的情况下，可能会发生状态更改的任何内容引入安全问题。</span><span class="sxs-lookup"><span data-stu-id="09e15-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="09e15-110">例如:</span><span class="sxs-lookup"><span data-stu-id="09e15-110">For example:</span></span>  
  
```cpp  
try   
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and   
    // so on) that could be exploited if malicious   
    // code ran before state is restored.  
    Do_some_work();  
}   
finally   
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 <span data-ttu-id="09e15-111">此伪代码允许堆栈上较高的筛选器运行任意代码。</span><span class="sxs-lookup"><span data-stu-id="09e15-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="09e15-112">具有类似效果的其他操作示例是对其他标识的临时模拟、设置跳过某些安全检查的内部标志或更改与线程关联的区域性。</span><span class="sxs-lookup"><span data-stu-id="09e15-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="09e15-113">建议的解决方案是引入异常处理程序，以将代码的更改从调用方的筛选器块隔离到线程状态。</span><span class="sxs-lookup"><span data-stu-id="09e15-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="09e15-114">但是，必须正确地引入异常处理程序，否则不会解决此问题。</span><span class="sxs-lookup"><span data-stu-id="09e15-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="09e15-115">下面的示例将切换 UI 区域性，但任何类型的线程状态更改都可能会以同样的方式公开。</span><span class="sxs-lookup"><span data-stu-id="09e15-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",   
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 <span data-ttu-id="09e15-116">在这种情况下，正确的修复方法是在**try**/**catch**块中包装现有**try**/**finally**块。</span><span class="sxs-lookup"><span data-stu-id="09e15-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="09e15-117">只需将**catch throw**子句引入现有**try**/**finally**块中，就不能解决问题，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="09e15-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try   
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally   
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 <span data-ttu-id="09e15-118">这并不能解决此问题，因为在`FilterFunc`获取控件之前，finally 语句尚未运行。</span><span class="sxs-lookup"><span data-stu-id="09e15-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="09e15-119">下面的示例通过确保在将异常提供给调用方的异常筛选器块之前执行了**finally**子句来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="09e15-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try    
    {  
        try   
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally   
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="09e15-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="09e15-120">See also</span></span>

- [<span data-ttu-id="09e15-121">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="09e15-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
