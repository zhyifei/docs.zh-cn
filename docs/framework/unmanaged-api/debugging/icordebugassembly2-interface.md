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
ms.openlocfilehash: 70eac63855f16205c3d5dbcb28305481b986484c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645547"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="d5404-102">ICorDebugAssembly2 接口</span><span class="sxs-lookup"><span data-stu-id="d5404-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="d5404-103">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="d5404-103">Represents an assembly.</span></span> <span data-ttu-id="d5404-104">此接口是 icor 调试程序集接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="d5404-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5404-105">方法</span><span class="sxs-lookup"><span data-stu-id="d5404-105">Methods</span></span>  
  
|<span data-ttu-id="d5404-106">方法</span><span class="sxs-lookup"><span data-stu-id="d5404-106">Method</span></span>|<span data-ttu-id="d5404-107">描述</span><span class="sxs-lookup"><span data-stu-id="d5404-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5404-108">IsFullyTrusted 方法</span><span class="sxs-lookup"><span data-stu-id="d5404-108">IsFullyTrusted Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="d5404-109">获取一个值，该值指示运行时安全系统是否已向程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="d5404-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5404-110">备注</span><span class="sxs-lookup"><span data-stu-id="d5404-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5404-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d5404-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5404-112">要求</span><span class="sxs-lookup"><span data-stu-id="d5404-112">Requirements</span></span>  
 <span data-ttu-id="d5404-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5404-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5404-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5404-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5404-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5404-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5404-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5404-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5404-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5404-117">See also</span></span>

- [<span data-ttu-id="d5404-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="d5404-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
