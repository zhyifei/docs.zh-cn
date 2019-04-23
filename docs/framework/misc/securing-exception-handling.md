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
ms.openlocfilehash: bc8cd20a4183ffd002f1399b6b50c8956208a21b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173665"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="206ca-102">保护异常处理</span><span class="sxs-lookup"><span data-stu-id="206ca-102">Securing Exception Handling</span></span>
<span data-ttu-id="206ca-103">视觉对象中C++和 Visual Basic 中之前, 运行的筛选器表达式进一步在堆栈中向上**最后**语句。</span><span class="sxs-lookup"><span data-stu-id="206ca-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="206ca-104">**捕获**与关联的块之后运行该筛选器**最后**语句。</span><span class="sxs-lookup"><span data-stu-id="206ca-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="206ca-105">有关详细信息，请参阅[使用用户筛选异常](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="206ca-105">For more information, see [Using User-Filtered Exceptions](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="206ca-106">本部分中检查此顺序的安全隐患。</span><span class="sxs-lookup"><span data-stu-id="206ca-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="206ca-107">请考虑下面的伪代码示例说明了哪些筛选器语句中的顺序，并**最后**运行的语句。</span><span class="sxs-lookup"><span data-stu-id="206ca-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="206ca-108">此代码将打印以下。</span><span class="sxs-lookup"><span data-stu-id="206ca-108">This code prints the following.</span></span>  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="206ca-109">筛选器之前运行**最后**语句，因此安全问题可能会造成的任何内容会使更改在其中执行其他代码无法充分利用状态。</span><span class="sxs-lookup"><span data-stu-id="206ca-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="206ca-110">例如：</span><span class="sxs-lookup"><span data-stu-id="206ca-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="206ca-111">此伪代码允许运行任意代码的堆栈较高的筛选器。</span><span class="sxs-lookup"><span data-stu-id="206ca-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="206ca-112">将具有类似的效果的操作的其他示例包括临时模拟另一标识，绕过某些安全检查，内部标志设置或更改区域性与线程关联。</span><span class="sxs-lookup"><span data-stu-id="206ca-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="206ca-113">建议的解决方案是引入了一个异常处理程序，以隔离到线程的状态从向调用方的筛选器块的代码的更改。</span><span class="sxs-lookup"><span data-stu-id="206ca-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="206ca-114">但是，很重要的异常处理程序必须正确地引入或将不会修复此问题。</span><span class="sxs-lookup"><span data-stu-id="206ca-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="206ca-115">下面的示例切换的 UI 区域性，但无法类似的方式公开任何类型的线程状态更改。</span><span class="sxs-lookup"><span data-stu-id="206ca-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="206ca-116">正确的解决方法在这种情况下是包装现有**尝试**/**最后**块中**尝试**/**捕获**块。</span><span class="sxs-lookup"><span data-stu-id="206ca-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="206ca-117">只需引入**catch throw**到现有的子句**尝试**/**最后**块不能解决此问题，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="206ca-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="206ca-118">此操作未修复问题，因为**最后**以前未运行语句`FilterFunc`获取控件。</span><span class="sxs-lookup"><span data-stu-id="206ca-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="206ca-119">下面的示例通过确保修复此问题**最后**子句已提供异常向调用方的异常筛选器块之前执行。</span><span class="sxs-lookup"><span data-stu-id="206ca-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="206ca-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="206ca-120">See also</span></span>

- [<span data-ttu-id="206ca-121">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="206ca-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
