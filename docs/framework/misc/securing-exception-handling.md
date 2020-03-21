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
ms.openlocfilehash: ad27e62197f6fdaa6b5e706f4ae02c03fecae9f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181138"
---
# <a name="securing-exception-handling"></a>保护异常处理
在 Visual C++ 和 Visual Basic 中，进一步向上堆栈的筛选器表达式在任何**最终**语句之前运行。 与该筛选器关联的**catch**块在**最终**语句之后运行。 有关详细信息，请参阅[使用用户筛选的异常](../../standard/exceptions/using-user-filtered-exception-handlers.md)。 本节将检查此订单的安全影响。 请考虑以下伪代码示例，该示例说明了筛选器语句**和最后语句**的运行顺序。  
  
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
  
 此代码打印以下内容。  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 筛选器在**最终**语句之前运行，因此任何进行状态更改都可以引入安全问题，从而可以利用其他代码的执行。 例如：  
  
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
  
 此伪代码允许堆栈上较高的筛选器运行任意代码。 具有类似效果的其他操作示例包括临时模拟另一个标识、设置绕过某些安全检查的内部标志或更改与线程关联的区域性。 建议的解决方案是引入一个异常处理程序，以将代码对线程状态的更改与调用方的筛选器块隔离开来。 但是，正确引入异常处理程序或无法解决此问题非常重要。 下面的示例切换 UI 区域性，但任何类型的线程状态更改可能同样公开。  
  
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
  
 在这种情况下，正确的解决方法是在**try**/**catch**块中包装现有**try**/**finally**块。 简单地将**catch-throw**子句引入到现有**try**/**finally**块中并不能解决问题，如下例所示。  
  
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
  
 这不能解决问题，因为**finally**语句在`FilterFunc`获取控件之前未运行。  
  
 下面的示例通过在提供调用方的异常筛选器块的异常之前已执行**最终**子句来解决此问题。  
  
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
  
## <a name="see-also"></a>另请参阅

- [代码安全维护指南](../../standard/security/secure-coding-guidelines.md)
