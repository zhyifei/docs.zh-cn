---
title: CorDebugExceptionObjectStackFrame 结构
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a4cd4d353c22921ed3dba1dc08fe2cee7e429f8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173077"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="84dc8-102">CorDebugExceptionObjectStackFrame 结构</span><span class="sxs-lookup"><span data-stu-id="84dc8-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="84dc8-103">表示异常对象中的堆栈帧信息。</span><span class="sxs-lookup"><span data-stu-id="84dc8-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84dc8-104">语法</span><span class="sxs-lookup"><span data-stu-id="84dc8-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="84dc8-105">成员</span><span class="sxs-lookup"><span data-stu-id="84dc8-105">Members</span></span>  
  
|<span data-ttu-id="84dc8-106">成员</span><span class="sxs-lookup"><span data-stu-id="84dc8-106">Member</span></span>|<span data-ttu-id="84dc8-107">描述</span><span class="sxs-lookup"><span data-stu-id="84dc8-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="84dc8-108">指向当前帧的 icor 调试模块对象的指针。</span><span class="sxs-lookup"><span data-stu-id="84dc8-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="84dc8-109">指令指针 (EIP/RIP) 当前帧的值。</span><span class="sxs-lookup"><span data-stu-id="84dc8-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="84dc8-110">用于当前帧的方法标记。</span><span class="sxs-lookup"><span data-stu-id="84dc8-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="84dc8-111">一个值，指示框架是否外异常中的最后一帧。</span><span class="sxs-lookup"><span data-stu-id="84dc8-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84dc8-112">备注</span><span class="sxs-lookup"><span data-stu-id="84dc8-112">Remarks</span></span>  
 <span data-ttu-id="84dc8-113">不能再使用后，调用方必须释放 icor 调试模块对象的指针。</span><span class="sxs-lookup"><span data-stu-id="84dc8-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84dc8-114">要求</span><span class="sxs-lookup"><span data-stu-id="84dc8-114">Requirements</span></span>  
 <span data-ttu-id="84dc8-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84dc8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84dc8-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84dc8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84dc8-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84dc8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84dc8-118">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84dc8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84dc8-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="84dc8-119">See also</span></span>

- [<span data-ttu-id="84dc8-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="84dc8-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="84dc8-121">调试</span><span class="sxs-lookup"><span data-stu-id="84dc8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
