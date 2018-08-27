---
title: 如何：捕捉非 CLS 异常
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: c3153da78e0c25d59da7b5d83bd33f8080c7fae8
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "42754938"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="430af-102">如何：捕捉非 CLS 异常</span><span class="sxs-lookup"><span data-stu-id="430af-102">How to: Catch a non-CLS Exception</span></span>
<span data-ttu-id="430af-103">包括 C++/CLI 在内的某些 .NET 语言允许对象引发并非派生自 <xref:System.Exception> 的异常。</span><span class="sxs-lookup"><span data-stu-id="430af-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="430af-104">这类异常被称为非 CLS 异常或非异常。</span><span class="sxs-lookup"><span data-stu-id="430af-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="430af-105">无法在 C# 中引发非 CLS 异常，但有两种方式可以捕获它们：</span><span class="sxs-lookup"><span data-stu-id="430af-105">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
-   <span data-ttu-id="430af-106">在 `catch (RuntimeWrappedException e)` 块内捕获。</span><span class="sxs-lookup"><span data-stu-id="430af-106">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="430af-107">默认情况下，Visual C# 程序集将非 CLS 异常作为包装的异常捕获。</span><span class="sxs-lookup"><span data-stu-id="430af-107">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="430af-108">如需访问原始异常（可通过 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> 属性访问），请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="430af-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="430af-109">本主题的后续过程将解释如何通过此方式捕获异常。</span><span class="sxs-lookup"><span data-stu-id="430af-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
-   <span data-ttu-id="430af-110">在位于所有其他 `catch` 块之后的常规 catch 块（未指定异常类型的 catch 块）之中。</span><span class="sxs-lookup"><span data-stu-id="430af-110">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="430af-111">如果为了响应非 CLS 异常需要执行某些操作（如写入日志文件），且无需访问异常信息时，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="430af-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="430af-112">默认情况下，公共语言运行时包装所有异常。</span><span class="sxs-lookup"><span data-stu-id="430af-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="430af-113">要禁用此行为，请将此程序集级别属性添加到代码中，通常位于 AssemblyInfo.cs 文件：`[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`。</span><span class="sxs-lookup"><span data-stu-id="430af-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="430af-114">要捕捉非 CLS 异常</span><span class="sxs-lookup"><span data-stu-id="430af-114">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="430af-115">在 `catch(RuntimeWrappedException e)` 块中通过 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> 属性访问原始异常。</span><span class="sxs-lookup"><span data-stu-id="430af-115">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="430af-116">示例</span><span class="sxs-lookup"><span data-stu-id="430af-116">Example</span></span>  
 <span data-ttu-id="430af-117">下面示例显示如何捕捉以 C++/CLI 编写的类库所引发的非 CLS 异常。</span><span class="sxs-lookup"><span data-stu-id="430af-117">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="430af-118">请注意，在此示例中，C# 客户端代码预先已知被引发的异常类型是 <xref:System.String?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="430af-118">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="430af-119">可将 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> 属性转换回其原始类型，前提是可从代码访问该类型。</span><span class="sxs-lookup"><span data-stu-id="430af-119">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="430af-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="430af-120">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>  
 [<span data-ttu-id="430af-121">异常和异常处理</span><span class="sxs-lookup"><span data-stu-id="430af-121">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)
