---
title: 将委托作为回调方法进行封送
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2aa999199ddf11a1a2db57b6f7b1dd198b4ea61d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529839"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="fee25-102">将委托作为回调方法进行封送</span><span class="sxs-lookup"><span data-stu-id="fee25-102">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="fee25-103">此示例演示如何将委托传递给需要函数指针的非托管函数。</span><span class="sxs-lookup"><span data-stu-id="fee25-103">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="fee25-104">委托是可以容纳方法引用的类，等效于类型安全函数指针或回调函数。</span><span class="sxs-lookup"><span data-stu-id="fee25-104">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fee25-105">在调用内使用委托时，公共语言运行时防止在该调用的持续时间内对委托执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="fee25-105">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="fee25-106">但是，如果非托管函数存储了该委托，以便在调用完成后使用，则必须手动防止垃圾回收，直到非托管函数结束对该委托的使用为止。</span><span class="sxs-lookup"><span data-stu-id="fee25-106">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="fee25-107">有关详细信息，请参阅 [HandleRef 示例](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100))和 [GCHandle 示例](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="fee25-107">For more information, see the [HandleRef Sample](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) and [GCHandle Sample](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).</span></span>  
  
 <span data-ttu-id="fee25-108">回调示例使用以下非托管函数（与其原始函数声明一同显示）：</span><span class="sxs-lookup"><span data-stu-id="fee25-108">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="fee25-109">从 PinvokeLib.dll 导出的 TestCallBack。</span><span class="sxs-lookup"><span data-stu-id="fee25-109">**TestCallBack** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   <span data-ttu-id="fee25-110">从 PinvokeLib.dll 导出的 TestCallBack2。</span><span class="sxs-lookup"><span data-stu-id="fee25-110">**TestCallBack2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 <span data-ttu-id="fee25-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) 是一种自定义的非托管库，包含上述函数的实现。</span><span class="sxs-lookup"><span data-stu-id="fee25-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>  
  
 <span data-ttu-id="fee25-112">在此示例中，`LibWrap` 类包含 `TestCallBack` 和 `TestCallBack2` 方法的托管原型。</span><span class="sxs-lookup"><span data-stu-id="fee25-112">In this sample, the `LibWrap` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="fee25-113">这两种方法都作为参数将委托传递给回调函数。</span><span class="sxs-lookup"><span data-stu-id="fee25-113">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="fee25-114">委托的签名必须匹配它引用的方法的签名。</span><span class="sxs-lookup"><span data-stu-id="fee25-114">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="fee25-115">例如，`FPtr` 和 `FPtr2`委托的签名与 `DoSomething` 和 `DoSomething2` 方法相同。</span><span class="sxs-lookup"><span data-stu-id="fee25-115">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="fee25-116">声明原型</span><span class="sxs-lookup"><span data-stu-id="fee25-116">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a><span data-ttu-id="fee25-117">调用函数</span><span class="sxs-lookup"><span data-stu-id="fee25-117">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="fee25-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="fee25-118">See also</span></span>
- <span data-ttu-id="fee25-119">[其他封送处理示例](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fee25-119">[Miscellaneous Marshaling Samples](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span></span>
- <span data-ttu-id="fee25-120">[平台调用数据类型](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fee25-120">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>
- [<span data-ttu-id="fee25-121">在托管代码中创建原型</span><span class="sxs-lookup"><span data-stu-id="fee25-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
