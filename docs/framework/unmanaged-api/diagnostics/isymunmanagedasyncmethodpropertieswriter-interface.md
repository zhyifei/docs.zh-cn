---
title: ISymUnmanagedAsyncMethodPropertiesWriter 接口
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82fcddd7a3f89a92cc79285930b30342333fbec2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940096"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="63848-102">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="63848-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="63848-103">可以定义每个方法符号的可选的异步方法信息。</span><span class="sxs-lookup"><span data-stu-id="63848-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="63848-104">始终使用具有打开的方法;也就是说，调用之间[OpenMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)并[CloseMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="63848-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63848-105">语法</span><span class="sxs-lookup"><span data-stu-id="63848-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="63848-106">方法</span><span class="sxs-lookup"><span data-stu-id="63848-106">Methods</span></span>  
 <span data-ttu-id="63848-107">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="63848-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="63848-108">方法</span><span class="sxs-lookup"><span data-stu-id="63848-108">Method</span></span>|<span data-ttu-id="63848-109">描述</span><span class="sxs-lookup"><span data-stu-id="63848-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63848-110">DefineAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="63848-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="63848-111">定义一组异步等待当前方法中的操作。</span><span class="sxs-lookup"><span data-stu-id="63848-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="63848-112">每个 yield 偏移量与 await 表达式的返回指令，用于标识潜在 yield 相匹配。</span><span class="sxs-lookup"><span data-stu-id="63848-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="63848-113">每个`breakpointMethod` / `breakpointOffset`对标识将继续进行异步操作; 它可能在不同的方法。</span><span class="sxs-lookup"><span data-stu-id="63848-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="63848-114">DefineCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="63848-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="63848-115">设置的 IL 偏移量的编译器生成 catch 处理程序包装异步方法。</span><span class="sxs-lookup"><span data-stu-id="63848-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="63848-116">调试器使用生成 catch 的 IL 偏移量以处理 catch，就好像非用户代码，即使它可能会出现在用户代码方法。</span><span class="sxs-lookup"><span data-stu-id="63848-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="63848-117">具体而言，它用于响应**CatchHandlerFound**异常事件。</span><span class="sxs-lookup"><span data-stu-id="63848-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="63848-118">DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="63848-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="63848-119">设置启动异步操作的开始方法。</span><span class="sxs-lookup"><span data-stu-id="63848-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63848-120">要求</span><span class="sxs-lookup"><span data-stu-id="63848-120">Requirements</span></span>  
 <span data-ttu-id="63848-121">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="63848-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63848-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="63848-122">See also</span></span>

- [<span data-ttu-id="63848-123">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="63848-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
