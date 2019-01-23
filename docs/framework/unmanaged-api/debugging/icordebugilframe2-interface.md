---
title: ICorDebugILFrame2 Interface1
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
ms.openlocfilehash: 0996fee88d37bbc826a4e012dc44ea9005008ae4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575510"
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="c9573-102">ICorDebugILFrame2 Interface1</span><span class="sxs-lookup"><span data-stu-id="c9573-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="c9573-103">ICorDebugILFrame 接口逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="c9573-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9573-104">方法</span><span class="sxs-lookup"><span data-stu-id="c9573-104">Methods</span></span>  
  
|<span data-ttu-id="c9573-105">方法</span><span class="sxs-lookup"><span data-stu-id="c9573-105">Method</span></span>|<span data-ttu-id="c9573-106">描述</span><span class="sxs-lookup"><span data-stu-id="c9573-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9573-107">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="c9573-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="c9573-108">获取一个包含 ICorDebugTypeEnum 对象<xref:System.Type>此帧中的参数。</span><span class="sxs-lookup"><span data-stu-id="c9573-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="c9573-109">RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="c9573-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="c9573-110">通过指定新的 MSIL 偏移量，将重新经过编辑的函数映射。</span><span class="sxs-lookup"><span data-stu-id="c9573-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9573-111">备注</span><span class="sxs-lookup"><span data-stu-id="c9573-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9573-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="c9573-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9573-113">要求</span><span class="sxs-lookup"><span data-stu-id="c9573-113">Requirements</span></span>  
 <span data-ttu-id="c9573-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9573-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9573-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9573-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9573-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9573-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9573-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9573-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9573-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9573-118">See also</span></span>
- [<span data-ttu-id="c9573-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="c9573-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
