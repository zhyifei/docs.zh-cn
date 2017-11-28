---
title: "如何：捕捉非 CLS 异常"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 473cace033983915c66647d14cae16dc7f5d5b9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="70632-102">如何：捕捉非 CLS 异常</span><span class="sxs-lookup"><span data-stu-id="70632-102">How to: Catch a non-CLS Exception</span></span>
<span data-ttu-id="70632-103">包括 C++/CLI 在内的某些 .NET 语言允许对象引发并非派生自 <xref:System.Exception> 的异常。</span><span class="sxs-lookup"><span data-stu-id="70632-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="70632-104">这类异常被称为非 CLS 异常或非异常。</span><span class="sxs-lookup"><span data-stu-id="70632-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="70632-105">无法在 [!INCLUDE[csprcs](~/includes/csprcs-md.md)] 中引发非 CLS 异常，但有两种方式可以捕获它们：</span><span class="sxs-lookup"><span data-stu-id="70632-105">In [!INCLUDE[csprcs](~/includes/csprcs-md.md)] you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
-   <span data-ttu-id="70632-106">在 `catch (Exception e)` 块内作为 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>。</span><span class="sxs-lookup"><span data-stu-id="70632-106">Within a `catch (Exception e)` block as a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
     <span data-ttu-id="70632-107">默认情况下，[!INCLUDE[csprcs](~/includes/csprcs-md.md)] 程序集将非 CLS 异常作为包装的异常捕获。</span><span class="sxs-lookup"><span data-stu-id="70632-107">By default, a [!INCLUDE[csprcs](~/includes/csprcs-md.md)] assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="70632-108">如需访问原始异常（可通过 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> 属性访问），请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="70632-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span> <span data-ttu-id="70632-109">本主题的后续过程将解释如何通过此方式捕获异常。</span><span class="sxs-lookup"><span data-stu-id="70632-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
-   <span data-ttu-id="70632-110">在位于 `catch (Exception)` 或 `catch (Exception e)` 块之后的常规 catch 块（未指定异常类型的 catch 块）之中。</span><span class="sxs-lookup"><span data-stu-id="70632-110">Within a general catch block (a catch block without an exception type specified) that is put after a `catch (Exception)` or `catch (Exception e)` block.</span></span>  
  
     <span data-ttu-id="70632-111">如果为了响应非 CLS 异常需要执行某些操作（如写入日志文件），且无需访问异常信息时，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="70632-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="70632-112">默认情况下，公共语言运行时包装所有异常。</span><span class="sxs-lookup"><span data-stu-id="70632-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="70632-113">要禁用此行为，请将此程序集级别属性添加到代码中，通常位于 AssemblyInfo.cs 文件：`[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`。</span><span class="sxs-lookup"><span data-stu-id="70632-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="70632-114">要捕捉非 CLS 异常</span><span class="sxs-lookup"><span data-stu-id="70632-114">To catch a non-CLS exception</span></span>  
  
1.  <span data-ttu-id="70632-115">在 `catch(Exception e) block` 内，使用 `as` 关键字测试 `e` 是否可转换为 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>。</span><span class="sxs-lookup"><span data-stu-id="70632-115">Within a `catch(Exception e) block`, use the `as` keyword to test whether `e` can be cast to a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
2.  <span data-ttu-id="70632-116">通过 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> 属性访问原始异常。</span><span class="sxs-lookup"><span data-stu-id="70632-116">Access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70632-117">示例</span><span class="sxs-lookup"><span data-stu-id="70632-117">Example</span></span>  
 <span data-ttu-id="70632-118">下面示例显示如何捕捉以 C++/CLR 编写的类库所引发的非 CLS 异常。</span><span class="sxs-lookup"><span data-stu-id="70632-118">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLR.</span></span> <span data-ttu-id="70632-119">请注意，在此示例中，[!INCLUDE[csprcs](~/includes/csprcs-md.md)] 客户端代码预先已知道被引发的异常类型是 <xref:System.String?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="70632-119">Note that in this example, the [!INCLUDE[csprcs](~/includes/csprcs-md.md)] client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="70632-120">可将 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> 属性转换回其原始类型，前提是可从代码访问该类型。</span><span class="sxs-lookup"><span data-stu-id="70632-120">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property back its original type as long as that type is accessible from your code.</span></span>  
  
```  
// Class library written in C++/CLR.  
   ThrowNonCLS.Class1 myClass = new ThrowNonCLS.Class1();  
  
   try  
   {  
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();   
   }  
  
   catch (Exception e)  
   {  
    RuntimeWrappedException rwe = e as RuntimeWrappedException;  
    if (rwe != null)      
    {  
      String s = rwe.WrappedException as String;  
      if (s != null)  
      {  
        Console.WriteLine(s);  
      }  
    }  
    else  
    {  
       // Handle other System.Exception types.  
    }  
   }             
```  
  
## <a name="see-also"></a><span data-ttu-id="70632-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70632-121">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>  
 [<span data-ttu-id="70632-122">异常和异常处理</span><span class="sxs-lookup"><span data-stu-id="70632-122">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)
