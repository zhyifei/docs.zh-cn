---
title: ICorDebugILFrame2 接口 1
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
ms.openlocfilehash: ccb39609b37aff09ac7890df562d6c08e3c3c159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412430"
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="960f4-102">ICorDebugILFrame2 接口 1</span><span class="sxs-lookup"><span data-stu-id="960f4-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="960f4-103">ICorDebugILFrame 接口逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="960f4-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="960f4-104">方法</span><span class="sxs-lookup"><span data-stu-id="960f4-104">Methods</span></span>  
  
|<span data-ttu-id="960f4-105">方法</span><span class="sxs-lookup"><span data-stu-id="960f4-105">Method</span></span>|<span data-ttu-id="960f4-106">描述</span><span class="sxs-lookup"><span data-stu-id="960f4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="960f4-107">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="960f4-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="960f4-108">获取一个包含的 ICorDebugTypeEnum 对象<xref:System.Type>此帧中的参数。</span><span class="sxs-lookup"><span data-stu-id="960f4-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="960f4-109">RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="960f4-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="960f4-110">通过指定新的 MSIL 偏移量，重新映射经过编辑的函数。</span><span class="sxs-lookup"><span data-stu-id="960f4-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="960f4-111">备注</span><span class="sxs-lookup"><span data-stu-id="960f4-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="960f4-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="960f4-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="960f4-113">要求</span><span class="sxs-lookup"><span data-stu-id="960f4-113">Requirements</span></span>  
 <span data-ttu-id="960f4-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="960f4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="960f4-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="960f4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="960f4-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="960f4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="960f4-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="960f4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="960f4-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="960f4-118">See Also</span></span>  
 [<span data-ttu-id="960f4-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="960f4-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
