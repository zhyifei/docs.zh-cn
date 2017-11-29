---
title: "CorDebugExceptionObjectStackFrame 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugExceptionObjectStackFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugExceptionObjectStackFrame
helpviewer_keywords: CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf166f606aa2c0e0900356395c36bd6875897e3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="9bf67-102">CorDebugExceptionObjectStackFrame 结构</span><span class="sxs-lookup"><span data-stu-id="9bf67-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="9bf67-103">表示异常对象中的堆栈帧信息。</span><span class="sxs-lookup"><span data-stu-id="9bf67-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf67-104">语法</span><span class="sxs-lookup"><span data-stu-id="9bf67-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="9bf67-105">成员</span><span class="sxs-lookup"><span data-stu-id="9bf67-105">Members</span></span>  
  
|<span data-ttu-id="9bf67-106">成员</span><span class="sxs-lookup"><span data-stu-id="9bf67-106">Member</span></span>|<span data-ttu-id="9bf67-107">描述</span><span class="sxs-lookup"><span data-stu-id="9bf67-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="9bf67-108">指向当前帧的 icor 调试模块对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9bf67-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="9bf67-109">当前帧的指令指针 (EIP/RIP) 的值。</span><span class="sxs-lookup"><span data-stu-id="9bf67-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="9bf67-110">当前帧方法标记。</span><span class="sxs-lookup"><span data-stu-id="9bf67-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="9bf67-111">一个值，指示的框架是在外异常中的最后一帧。</span><span class="sxs-lookup"><span data-stu-id="9bf67-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bf67-112">备注</span><span class="sxs-lookup"><span data-stu-id="9bf67-112">Remarks</span></span>  
 <span data-ttu-id="9bf67-113">不再使用后，调用方必须释放 icor 调试模块对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9bf67-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bf67-114">要求</span><span class="sxs-lookup"><span data-stu-id="9bf67-114">Requirements</span></span>  
 <span data-ttu-id="9bf67-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9bf67-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bf67-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bf67-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bf67-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bf67-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bf67-118">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bf67-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf67-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bf67-119">See Also</span></span>  
 [<span data-ttu-id="9bf67-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="9bf67-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="9bf67-121">调试</span><span class="sxs-lookup"><span data-stu-id="9bf67-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
