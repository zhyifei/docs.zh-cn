---
title: ICorDebugMutableDataTarget::ContinueStatusChanged 方法
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: c918bb60fba5bc1ec3f0f7c58b103d05a3c7ddfd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792865"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="f476b-102">ICorDebugMutableDataTarget::ContinueStatusChanged 方法</span><span class="sxs-lookup"><span data-stu-id="f476b-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="f476b-103">更改指定线程上未完成的调试事件的延续状态。</span><span class="sxs-lookup"><span data-stu-id="f476b-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f476b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f476b-104">Syntax</span></span>  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f476b-105">参数</span><span class="sxs-lookup"><span data-stu-id="f476b-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="f476b-106">由操作系统定义的线程标识符。</span><span class="sxs-lookup"><span data-stu-id="f476b-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="f476b-107">表示新请求的延续状态的 [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 值。</span><span class="sxs-lookup"><span data-stu-id="f476b-107">A [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f476b-108">备注</span><span class="sxs-lookup"><span data-stu-id="f476b-108">Remarks</span></span>  
 <span data-ttu-id="f476b-109">当调试器调用需要以不同于通常处理方式的方式处理当前的调试事件的 ICorDebug 方法时，该调试器将调用 `ContinueStatusChanged` 方法。</span><span class="sxs-lookup"><span data-stu-id="f476b-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="f476b-110">例如，如果存在未处理异常，并且调试器请求会取消此异常的操作（例如 [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) 或 `FuncEval`），则此 API 将用于请求取消此异常。</span><span class="sxs-lookup"><span data-stu-id="f476b-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f476b-111">需求</span><span class="sxs-lookup"><span data-stu-id="f476b-111">Requirements</span></span>  
 <span data-ttu-id="f476b-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f476b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f476b-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f476b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f476b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f476b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f476b-115">**.NET Framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f476b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f476b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f476b-116">See also</span></span>

- [<span data-ttu-id="f476b-117">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="f476b-117">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="f476b-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="f476b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
