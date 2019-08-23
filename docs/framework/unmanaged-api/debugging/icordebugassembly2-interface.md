---
title: ICorDebugAssembly2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2
helpviewer_keywords:
- ICorDebugAssembly2 interface [.NET Framework debugging]
ms.assetid: c0766e29-e573-4f9a-a928-167d1de5aa7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b42cb2bff677963c44bfc04f8bdd6c60497e4731
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909884"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="fc9d3-102">ICorDebugAssembly2 接口</span><span class="sxs-lookup"><span data-stu-id="fc9d3-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="fc9d3-103">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="fc9d3-103">Represents an assembly.</span></span> <span data-ttu-id="fc9d3-104">此接口是 ICorDebugAssembly 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="fc9d3-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc9d3-105">方法</span><span class="sxs-lookup"><span data-stu-id="fc9d3-105">Methods</span></span>  
  
|<span data-ttu-id="fc9d3-106">方法</span><span class="sxs-lookup"><span data-stu-id="fc9d3-106">Method</span></span>|<span data-ttu-id="fc9d3-107">描述</span><span class="sxs-lookup"><span data-stu-id="fc9d3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc9d3-108">IsFullyTrusted 方法</span><span class="sxs-lookup"><span data-stu-id="fc9d3-108">IsFullyTrusted Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="fc9d3-109">获取一个值, 该值指示运行时安全系统是否已向程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="fc9d3-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc9d3-110">备注</span><span class="sxs-lookup"><span data-stu-id="fc9d3-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc9d3-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="fc9d3-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc9d3-112">要求</span><span class="sxs-lookup"><span data-stu-id="fc9d3-112">Requirements</span></span>  
 <span data-ttu-id="fc9d3-113">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc9d3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc9d3-114">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="fc9d3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc9d3-115">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc9d3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc9d3-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc9d3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc9d3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc9d3-117">See also</span></span>

- [<span data-ttu-id="fc9d3-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="fc9d3-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
