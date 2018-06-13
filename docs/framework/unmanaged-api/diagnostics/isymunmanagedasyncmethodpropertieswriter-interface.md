---
title: ISymUnmanagedAsyncMethodPropertiesWriter 接口
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ec66e0064a8d6e8d4664dd8c727aa87621cfd8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427302"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="7e7d3-102">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="7e7d3-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="7e7d3-103">允许你定义每个方法符号的可选的异步方法信息。</span><span class="sxs-lookup"><span data-stu-id="7e7d3-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="7e7d3-104">始终使用与打开的方法;也就是说，对的调用之间[OpenMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)和[CloseMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7e7d3-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e7d3-105">语法</span><span class="sxs-lookup"><span data-stu-id="7e7d3-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="7e7d3-106">方法</span><span class="sxs-lookup"><span data-stu-id="7e7d3-106">Methods</span></span>  
 <span data-ttu-id="7e7d3-107">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="7e7d3-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="7e7d3-108">方法</span><span class="sxs-lookup"><span data-stu-id="7e7d3-108">Method</span></span>|<span data-ttu-id="7e7d3-109">描述</span><span class="sxs-lookup"><span data-stu-id="7e7d3-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e7d3-110">DefineAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="7e7d3-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="7e7d3-111">定义一组异步等待在当前方法中的操作。</span><span class="sxs-lookup"><span data-stu-id="7e7d3-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="7e7d3-112">每个 yield 偏移量与 await 表达式的返回指令，用于标识潜在 yield 相匹配。</span><span class="sxs-lookup"><span data-stu-id="7e7d3-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="7e7d3-113">每个`breakpointMethod` / `breakpointOffset`对标识异步操作将恢复其中; 它可能在不同的方法。</span><span class="sxs-lookup"><span data-stu-id="7e7d3-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="7e7d3-114">DefineCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="7e7d3-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="7e7d3-115">设置 IL 偏移量的编译器生成 catch 处理程序包装异步方法。</span><span class="sxs-lookup"><span data-stu-id="7e7d3-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="7e7d3-116">生成 catch 的 IL 偏移量由调试器用于处理该 catch，就像它是非用户代码，即使它可能会出现在用户代码方法。</span><span class="sxs-lookup"><span data-stu-id="7e7d3-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="7e7d3-117">具体而言，它用于响应**CatchHandlerFound**异常事件。</span><span class="sxs-lookup"><span data-stu-id="7e7d3-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="7e7d3-118">DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="7e7d3-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="7e7d3-119">设置启动异步操作的开始方法。</span><span class="sxs-lookup"><span data-stu-id="7e7d3-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e7d3-120">要求</span><span class="sxs-lookup"><span data-stu-id="7e7d3-120">Requirements</span></span>  
 <span data-ttu-id="7e7d3-121">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7e7d3-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e7d3-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e7d3-122">See Also</span></span>  
 [<span data-ttu-id="7e7d3-123">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="7e7d3-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
