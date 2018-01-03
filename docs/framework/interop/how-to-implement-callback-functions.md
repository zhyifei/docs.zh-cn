---
title: "如何：实现回调函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 819861f9bf13f9af3fab7a1ea7ffc697c1d98926
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-callback-functions"></a><span data-ttu-id="f3930-102">如何：实现回调函数</span><span class="sxs-lookup"><span data-stu-id="f3930-102">How to: Implement Callback Functions</span></span>
<span data-ttu-id="f3930-103">下面的过程和示例演示使用平台调用的托管应用程序如何在本地计算机上打印每个窗口的句柄值。</span><span class="sxs-lookup"><span data-stu-id="f3930-103">The following procedure and example demonstrate how a managed application, using platform invoke, can print the handle value for each window on the local computer.</span></span> <span data-ttu-id="f3930-104">具体而言，过程和示例使用“EnumWindows” 函数来逐句通过窗口列表，使用托管回调函数（名为 CallBack）来打印窗口句柄的值。</span><span class="sxs-lookup"><span data-stu-id="f3930-104">Specifically, the procedure and example use the **EnumWindows** function to step through the list of windows and a managed callback function (named CallBack) to print the value of the window handle.</span></span>  
  
### <a name="to-implement-a-callback-function"></a><span data-ttu-id="f3930-105">实现回调函数的步骤</span><span class="sxs-lookup"><span data-stu-id="f3930-105">To implement a callback function</span></span>  
  
1.  <span data-ttu-id="f3930-106">在进一步执行实现前，请查看“EnumWindows”函数的签名。</span><span class="sxs-lookup"><span data-stu-id="f3930-106">Look at the signature for the **EnumWindows** function before going further with the implementation.</span></span> <span data-ttu-id="f3930-107">“EnumWindows”具有以下签名：</span><span class="sxs-lookup"><span data-stu-id="f3930-107">**EnumWindows** has the following signature:</span></span>  
  
    ```  
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)  
    ```  
  
     <span data-ttu-id="f3930-108">此函数需要回调的线索之一是存在“lpEnumFunc”自变量。</span><span class="sxs-lookup"><span data-stu-id="f3930-108">One clue that this function requires a callback is the presence of the **lpEnumFunc** argument.</span></span> <span data-ttu-id="f3930-109">经常可以看到在采用指向回调函数的指针的参数名称中“lp”（长指针）前缀与“Func”后缀结合在一起。</span><span class="sxs-lookup"><span data-stu-id="f3930-109">It is common to see the **lp** (long pointer) prefix combined with the **Func** suffix in the name of arguments that take a pointer to a callback function.</span></span> <span data-ttu-id="f3930-110">有关 Win32 函数的文档，请参阅 Microsoft Platform SDK。</span><span class="sxs-lookup"><span data-stu-id="f3930-110">For documentation about Win32 functions, see the Microsoft Platform SDK.</span></span>  
  
2.  <span data-ttu-id="f3930-111">创建托管回调函数。</span><span class="sxs-lookup"><span data-stu-id="f3930-111">Create the managed callback function.</span></span> <span data-ttu-id="f3930-112">此示例声明一个名为 `CallBack` 的委托类型，该类型采用两个自变量（“hwnd”和“lparam”）。</span><span class="sxs-lookup"><span data-stu-id="f3930-112">The example declares a delegate type, called `CallBack`, which takes two arguments (**hwnd** and **lparam**).</span></span> <span data-ttu-id="f3930-113">第一个自变量是窗口的句柄；第二个自变量是应用程序定义的。</span><span class="sxs-lookup"><span data-stu-id="f3930-113">The first argument is a handle to the window; the second argument is application-defined.</span></span> <span data-ttu-id="f3930-114">在此版本中，这两个参数都必须是整数。</span><span class="sxs-lookup"><span data-stu-id="f3930-114">In this release, both arguments must be integers.</span></span>  
  
     <span data-ttu-id="f3930-115">回调函数通常返回非零值来指示成功，返回零值来指示失败。</span><span class="sxs-lookup"><span data-stu-id="f3930-115">Callback functions generally return nonzero values to indicate success and zero to indicate failure.</span></span> <span data-ttu-id="f3930-116">此示例将返回值显式设置为“true”以继续进行枚举。</span><span class="sxs-lookup"><span data-stu-id="f3930-116">This example explicitly sets the return value to **true** to continue the enumeration.</span></span>  
  
3.  <span data-ttu-id="f3930-117">创建一个委托，并将其作为自变量传递到“EnumWindows”函数。</span><span class="sxs-lookup"><span data-stu-id="f3930-117">Create a delegate and pass it as an argument to the **EnumWindows** function.</span></span> <span data-ttu-id="f3930-118">平台调用自动将该委托转换为常见的回调格式。</span><span class="sxs-lookup"><span data-stu-id="f3930-118">Platform invoke converts the delegate to a familiar callback format automatically.</span></span>  
  
4.  <span data-ttu-id="f3930-119">确保在回调函数完成其工作之前，垃圾回收器不会回收委托。</span><span class="sxs-lookup"><span data-stu-id="f3930-119">Ensure that the garbage collector does not reclaim the delegate before the callback function completes its work.</span></span> <span data-ttu-id="f3930-120">当将委托作为参数传递，或传递作为字段包括到结构中的委托时，在调用期间不会对其进行回收。</span><span class="sxs-lookup"><span data-stu-id="f3930-120">When you pass a delegate as a parameter, or pass a delegate contained as a field in a structure, it remains uncollected for the duration of the call.</span></span> <span data-ttu-id="f3930-121">因此，正如下面的枚举示例一样，调用返回并不再需要托管调用方执行任何其他操作之前，回调函数完成其工作。</span><span class="sxs-lookup"><span data-stu-id="f3930-121">So, as is the case in the following enumeration example, the callback function completes its work before the call returns and requires no additional action by the managed caller.</span></span>  
  
     <span data-ttu-id="f3930-122">但是，如果调用返回后可以调用回调函数，托管调用方必须采取措施来确保委托在回调函数完成之前不会被回收。</span><span class="sxs-lookup"><span data-stu-id="f3930-122">If, however, the callback function can be invoked after the call returns, the managed caller must take steps to ensure that the delegate remains uncollected until the callback function finishes.</span></span> <span data-ttu-id="f3930-123">有关防止垃圾回收的详细信息，请参阅使用平台调用的[互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)。</span><span class="sxs-lookup"><span data-stu-id="f3930-123">For detailed information about preventing garbage collection, see [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md) with Platform Invoke.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3930-124">示例</span><span class="sxs-lookup"><span data-stu-id="f3930-124">Example</span></span>  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
  
Public Delegate Function CallBack( _  
hwnd As Integer, lParam As Integer) As Boolean  
  
Public Class EnumReportApp  
  
    Declare Function EnumWindows Lib "user32" ( _  
       x As CallBack, y As Integer) As Integer  
  
    Public Shared Sub Main()  
        EnumWindows(AddressOf EnumReportApp.Report, 0)  
    End Sub 'Main  
  
    Public Shared Function Report(hwnd As Integer, lParam As Integer) _  
    As Boolean  
        Console.Write("Window handle is ")  
        Console.WriteLine(hwnd)  
        Return True  
    End Function 'Report  
End Class 'EnumReportApp  
```  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public delegate bool CallBack(int hwnd, int lParam);  
  
public class EnumReportApp  
{  
    [DllImport("user32")]  
    public static extern int EnumWindows(CallBack x, int y);   
  
    public static void Main()   
    {  
        CallBack myCallBack = new CallBack(EnumReportApp.Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    public static bool Report(int hwnd, int lParam)  
    {   
        Console.Write("Window handle is ");  
        Console.WriteLine(hwnd);  
        return true;  
    }  
}  
```  
  
```cpp  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// A delegate type.  
delegate bool CallBack(int hwnd, int lParam);  
  
// Managed type with the method to call.  
ref class EnumReport  
{  
// Report the window handle.  
public:  
    [DllImport("user32")]  
    static int EnumWindows(CallBack^ x, int y);  
  
    static void Main()  
    {  
        EnumReport^ er = gcnew EnumReport;  
        CallBack^ myCallBack = gcnew CallBack(&EnumReport::Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    static bool Report(int hwnd, int lParam)  
    {  
       Console::Write(L"Window handle is ");  
       Console::WriteLine(hwnd);  
       return true;  
    }  
};  
  
int main()  
{  
    EnumReport::Main();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3930-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3930-125">See Also</span></span>  
 [<span data-ttu-id="f3930-126">回调函数</span><span class="sxs-lookup"><span data-stu-id="f3930-126">Callback Functions</span></span>](../../../docs/framework/interop/callback-functions.md)  
 [<span data-ttu-id="f3930-127">调用 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="f3930-127">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
