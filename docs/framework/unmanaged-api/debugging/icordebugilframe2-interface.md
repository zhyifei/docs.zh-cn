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
ms.openlocfilehash: d02dab01eca3bd4f8ce3ae7ace7f9d4be8233dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917009"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="043ba-102">ICorDebugILFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="043ba-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="043ba-103">ICorDebugILFrame 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="043ba-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="043ba-104">方法</span><span class="sxs-lookup"><span data-stu-id="043ba-104">Methods</span></span>  
  
|<span data-ttu-id="043ba-105">方法</span><span class="sxs-lookup"><span data-stu-id="043ba-105">Method</span></span>|<span data-ttu-id="043ba-106">描述</span><span class="sxs-lookup"><span data-stu-id="043ba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="043ba-107">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="043ba-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="043ba-108">获取一个 ICorDebugTypeEnum 对象, 该对象<xref:System.Type>包含此帧中的参数。</span><span class="sxs-lookup"><span data-stu-id="043ba-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="043ba-109">RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="043ba-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="043ba-110">通过指定新的 MSIL 偏移量重新映射编辑的函数。</span><span class="sxs-lookup"><span data-stu-id="043ba-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="043ba-111">备注</span><span class="sxs-lookup"><span data-stu-id="043ba-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="043ba-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="043ba-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="043ba-113">要求</span><span class="sxs-lookup"><span data-stu-id="043ba-113">Requirements</span></span>  
 <span data-ttu-id="043ba-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="043ba-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="043ba-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="043ba-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="043ba-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="043ba-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="043ba-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="043ba-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="043ba-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="043ba-118">See also</span></span>

- [<span data-ttu-id="043ba-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="043ba-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
