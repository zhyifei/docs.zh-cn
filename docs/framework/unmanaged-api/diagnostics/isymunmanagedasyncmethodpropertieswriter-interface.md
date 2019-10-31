---
title: ISymUnmanagedAsyncMethodPropertiesWriter 接口
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: db065357e22ac576600a3ca61dda0882b9206a86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129153"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="bd908-102">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="bd908-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="bd908-103">允许您为每个方法符号定义可选的异步方法信息。</span><span class="sxs-lookup"><span data-stu-id="bd908-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="bd908-104">始终使用打开的方法;也就是说，在对[OpenMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)和[CloseMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)的调用之间。</span><span class="sxs-lookup"><span data-stu-id="bd908-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd908-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd908-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="bd908-106">方法</span><span class="sxs-lookup"><span data-stu-id="bd908-106">Methods</span></span>  
 <span data-ttu-id="bd908-107">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="bd908-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="bd908-108">方法</span><span class="sxs-lookup"><span data-stu-id="bd908-108">Method</span></span>|<span data-ttu-id="bd908-109">描述</span><span class="sxs-lookup"><span data-stu-id="bd908-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd908-110">DefineAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="bd908-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="bd908-111">在当前方法中定义一组异步等待操作。</span><span class="sxs-lookup"><span data-stu-id="bd908-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="bd908-112">每个 yield 偏移均与 await 的返回指令匹配，确定潜在的收益率。</span><span class="sxs-lookup"><span data-stu-id="bd908-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="bd908-113">每个 `breakpointMethod`/`breakpointOffset` 对标识异步操作将恢复到的位置;它可能采用不同的方法。</span><span class="sxs-lookup"><span data-stu-id="bd908-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="bd908-114">DefineCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="bd908-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="bd908-115">设置编译器生成的用于包装异步方法的 catch 处理程序的 IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="bd908-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="bd908-116">调试器使用生成的 catch 的 IL 偏移量来处理 catch，就像它是非用户代码一样，即使它可能出现在用户代码方法中也是如此。</span><span class="sxs-lookup"><span data-stu-id="bd908-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="bd908-117">具体而言，它用于响应**CatchHandlerFound**异常事件。</span><span class="sxs-lookup"><span data-stu-id="bd908-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="bd908-118">DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="bd908-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="bd908-119">设置启动异步操作的启动方法。</span><span class="sxs-lookup"><span data-stu-id="bd908-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd908-120">要求</span><span class="sxs-lookup"><span data-stu-id="bd908-120">Requirements</span></span>  
 <span data-ttu-id="bd908-121">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="bd908-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd908-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd908-122">See also</span></span>

- [<span data-ttu-id="bd908-123">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="bd908-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
