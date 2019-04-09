---
title: 'Icordebugvirtualunwinder:: Next 方法'
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74be827dc97213507b96da9e025923f859011acd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076882"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="a6ff0-102">Icordebugvirtualunwinder:: Next 方法</span><span class="sxs-lookup"><span data-stu-id="a6ff0-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="a6ff0-103">前进到调用方的上下文。</span><span class="sxs-lookup"><span data-stu-id="a6ff0-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ff0-104">语法</span><span class="sxs-lookup"><span data-stu-id="a6ff0-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6ff0-105">参数</span><span class="sxs-lookup"><span data-stu-id="a6ff0-105">Parameters</span></span>  
 <span data-ttu-id="a6ff0-106">无。</span><span class="sxs-lookup"><span data-stu-id="a6ff0-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6ff0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a6ff0-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="a6ff0-108">如果成功进行展开或`CORDBG_S_AT_END_OF_STACK`如果无法完成展开，因为没有更多的帧。</span><span class="sxs-lookup"><span data-stu-id="a6ff0-108">if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="a6ff0-109">如果返回失败的 HRESULT，则 ICorDebug API 将返回 `CORDBG_E_DATA_TARGET_ERROR`。</span><span class="sxs-lookup"><span data-stu-id="a6ff0-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6ff0-110">备注</span><span class="sxs-lookup"><span data-stu-id="a6ff0-110">Remarks</span></span>  
 <span data-ttu-id="a6ff0-111">堆栈查看器应确保向前推进，以便最后 `Next` 的调用将返回失败的 HRESULT 或 `CORDBG_S_AT_END_OF_STACK`。</span><span class="sxs-lookup"><span data-stu-id="a6ff0-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="a6ff0-112">返回`S_OK`无限期可能会导致无限循环。</span><span class="sxs-lookup"><span data-stu-id="a6ff0-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6ff0-113">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a6ff0-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6ff0-114">要求</span><span class="sxs-lookup"><span data-stu-id="a6ff0-114">Requirements</span></span>  
 <span data-ttu-id="a6ff0-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6ff0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ff0-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6ff0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6ff0-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6ff0-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a6ff0-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a6ff0-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a6ff0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6ff0-119">See also</span></span>

- [<span data-ttu-id="a6ff0-120">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="a6ff0-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="a6ff0-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="a6ff0-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
