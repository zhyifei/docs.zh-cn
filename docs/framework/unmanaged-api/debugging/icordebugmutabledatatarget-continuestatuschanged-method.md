---
title: ICorDebugMutableDataTarget::ContinueStatusChanged 方法
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb07c519743c41a7a31994e42d2fdc5220e5e2ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418205"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="8d8a7-102">ICorDebugMutableDataTarget::ContinueStatusChanged 方法</span><span class="sxs-lookup"><span data-stu-id="8d8a7-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="8d8a7-103">更改指定线程上未完成的调试事件的延续状态。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d8a7-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d8a7-104">Syntax</span></span>  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d8a7-105">参数</span><span class="sxs-lookup"><span data-stu-id="8d8a7-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="8d8a7-106">由操作系统定义的线程标识符。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="8d8a7-107">A[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值，该值表示新请求的延续状态。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-107">A[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d8a7-108">备注</span><span class="sxs-lookup"><span data-stu-id="8d8a7-108">Remarks</span></span>  
 <span data-ttu-id="8d8a7-109">当调试器调用需要以不同于通常处理方式的方式处理当前的调试事件的 ICorDebug 方法时，该调试器将调用 `ContinueStatusChanged` 方法。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="8d8a7-110">例如，如果出现未处理的异常，并且调试器请求会取消该异常的操作 (如[icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)或`FuncEval`)，此 API 用于请求异常取消。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d8a7-111">要求</span><span class="sxs-lookup"><span data-stu-id="8d8a7-111">Requirements</span></span>  
 <span data-ttu-id="8d8a7-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d8a7-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d8a7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d8a7-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d8a7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d8a7-115">**.NET framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d8a7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d8a7-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d8a7-116">See Also</span></span>  
 [<span data-ttu-id="8d8a7-117">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="8d8a7-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="8d8a7-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="8d8a7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
