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
ms.openlocfilehash: 7b3b29be2bab2d1b4cea5dcec89e31d4720be769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576871"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="bde17-102">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="bde17-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="bde17-103">提供扩展了"ICorDebugCode"和"ICorDebugCode2"，以便提供有关托管返回值信息的方法。</span><span class="sxs-lookup"><span data-stu-id="bde17-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bde17-104">方法</span><span class="sxs-lookup"><span data-stu-id="bde17-104">Methods</span></span>  
  
|<span data-ttu-id="bde17-105">方法</span><span class="sxs-lookup"><span data-stu-id="bde17-105">Method</span></span>|<span data-ttu-id="bde17-106">描述</span><span class="sxs-lookup"><span data-stu-id="bde17-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bde17-107">GetReturnValueLiveOffset 方法</span><span class="sxs-lookup"><span data-stu-id="bde17-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="bde17-108">对于指定的 IL 偏移量，获取本机偏移量，以便调试器可以从函数获取返回值应放置一个断点。</span><span class="sxs-lookup"><span data-stu-id="bde17-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bde17-109">备注</span><span class="sxs-lookup"><span data-stu-id="bde17-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bde17-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="bde17-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bde17-111">要求</span><span class="sxs-lookup"><span data-stu-id="bde17-111">Requirements</span></span>  
 <span data-ttu-id="bde17-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bde17-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bde17-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bde17-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bde17-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bde17-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bde17-115">**.NET Framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bde17-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bde17-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bde17-116">See also</span></span>



- [<span data-ttu-id="bde17-117">ICorDebugILFrame3 接口</span><span class="sxs-lookup"><span data-stu-id="bde17-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
- [<span data-ttu-id="bde17-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="bde17-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
