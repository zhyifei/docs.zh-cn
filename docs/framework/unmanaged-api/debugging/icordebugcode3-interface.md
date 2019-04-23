---
title: ICorDebugCode3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cb9aa09447acf28f1ed10ba409ce936cdb4f84a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085033"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="2220a-102">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="2220a-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="2220a-103">提供扩展了"ICorDebugCode"和"ICorDebugCode2"，以便提供有关托管返回值信息的方法。</span><span class="sxs-lookup"><span data-stu-id="2220a-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2220a-104">方法</span><span class="sxs-lookup"><span data-stu-id="2220a-104">Methods</span></span>  
  
|<span data-ttu-id="2220a-105">方法</span><span class="sxs-lookup"><span data-stu-id="2220a-105">Method</span></span>|<span data-ttu-id="2220a-106">描述</span><span class="sxs-lookup"><span data-stu-id="2220a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2220a-107">GetReturnValueLiveOffset 方法</span><span class="sxs-lookup"><span data-stu-id="2220a-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="2220a-108">对于指定的 IL 偏移量，获取本机偏移量，以便调试器可以从函数获取返回值应放置一个断点。</span><span class="sxs-lookup"><span data-stu-id="2220a-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2220a-109">备注</span><span class="sxs-lookup"><span data-stu-id="2220a-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2220a-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="2220a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2220a-111">要求</span><span class="sxs-lookup"><span data-stu-id="2220a-111">Requirements</span></span>  
 <span data-ttu-id="2220a-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2220a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2220a-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2220a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2220a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2220a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2220a-115">**.NET Framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2220a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2220a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2220a-116">See also</span></span>

- [<span data-ttu-id="2220a-117">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="2220a-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
- [<span data-ttu-id="2220a-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="2220a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
