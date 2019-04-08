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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072951"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="77963-102">ICorDebugChainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="77963-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="77963-103">实现 ICorDebugEnum 方法，并枚举 ICorDebugChain 数组。</span><span class="sxs-lookup"><span data-stu-id="77963-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77963-104">方法</span><span class="sxs-lookup"><span data-stu-id="77963-104">Methods</span></span>  
  
|<span data-ttu-id="77963-105">方法</span><span class="sxs-lookup"><span data-stu-id="77963-105">Method</span></span>|<span data-ttu-id="77963-106">描述</span><span class="sxs-lookup"><span data-stu-id="77963-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77963-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="77963-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-next-method.md)|<span data-ttu-id="77963-108">获取指定的数目的`ICorDebugChain`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="77963-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77963-109">备注</span><span class="sxs-lookup"><span data-stu-id="77963-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77963-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="77963-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77963-111">要求</span><span class="sxs-lookup"><span data-stu-id="77963-111">Requirements</span></span>  
 <span data-ttu-id="77963-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77963-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77963-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77963-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77963-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77963-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="77963-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="77963-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="77963-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="77963-116">See also</span></span>

- [<span data-ttu-id="77963-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="77963-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
