---
title: ICorDebugILFrame2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e82238fbd617d56feb5c71c6161b6fd206b8b5b6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970852"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="c27b5-102">ICorDebugILFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="c27b5-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="c27b5-103">ICorDebugILFrame 接口逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="c27b5-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c27b5-104">方法</span><span class="sxs-lookup"><span data-stu-id="c27b5-104">Methods</span></span>  
  
|<span data-ttu-id="c27b5-105">方法</span><span class="sxs-lookup"><span data-stu-id="c27b5-105">Method</span></span>|<span data-ttu-id="c27b5-106">描述</span><span class="sxs-lookup"><span data-stu-id="c27b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c27b5-107">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="c27b5-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="c27b5-108">获取一个包含 ICorDebugTypeEnum 对象<xref:System.Type>此帧中的参数。</span><span class="sxs-lookup"><span data-stu-id="c27b5-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="c27b5-109">RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="c27b5-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="c27b5-110">通过指定新的 MSIL 偏移量，将重新经过编辑的函数映射。</span><span class="sxs-lookup"><span data-stu-id="c27b5-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c27b5-111">备注</span><span class="sxs-lookup"><span data-stu-id="c27b5-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c27b5-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="c27b5-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c27b5-113">要求</span><span class="sxs-lookup"><span data-stu-id="c27b5-113">Requirements</span></span>  
 <span data-ttu-id="c27b5-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c27b5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c27b5-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c27b5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c27b5-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c27b5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c27b5-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c27b5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c27b5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c27b5-118">See also</span></span>
- [<span data-ttu-id="c27b5-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="c27b5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
