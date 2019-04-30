---
title: ICorDebugChainEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum
helpviewer_keywords:
- ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6639335c-48e1-4e74-a4f3-70a6a0f54af1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d8a64b7dcaf4758cba217be06fa7d09f6c76920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989243"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="db471-102">ICorDebugChainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="db471-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="db471-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugChain 数组。</span><span class="sxs-lookup"><span data-stu-id="db471-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db471-104">方法</span><span class="sxs-lookup"><span data-stu-id="db471-104">Methods</span></span>  
  
|<span data-ttu-id="db471-105">方法</span><span class="sxs-lookup"><span data-stu-id="db471-105">Method</span></span>|<span data-ttu-id="db471-106">描述</span><span class="sxs-lookup"><span data-stu-id="db471-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db471-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="db471-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-next-method.md)|<span data-ttu-id="db471-108">获取指定的数目的`ICorDebugChain`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="db471-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db471-109">备注</span><span class="sxs-lookup"><span data-stu-id="db471-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db471-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="db471-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db471-111">要求</span><span class="sxs-lookup"><span data-stu-id="db471-111">Requirements</span></span>  
 <span data-ttu-id="db471-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db471-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db471-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db471-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db471-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db471-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db471-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db471-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db471-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="db471-116">See also</span></span>

- [<span data-ttu-id="db471-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="db471-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
