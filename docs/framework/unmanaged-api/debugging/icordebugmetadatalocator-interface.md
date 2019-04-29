---
title: ICorDebugMetaDataLocator 接口
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e9b9221aa2f5e048a94c225660ba2ac9214549c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780891"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="6ea8e-102">ICorDebugMetaDataLocator 接口</span><span class="sxs-lookup"><span data-stu-id="6ea8e-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="6ea8e-103">向调试器提供元数据信息。</span><span class="sxs-lookup"><span data-stu-id="6ea8e-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ea8e-104">方法</span><span class="sxs-lookup"><span data-stu-id="6ea8e-104">Methods</span></span>  
  
|<span data-ttu-id="6ea8e-105">方法</span><span class="sxs-lookup"><span data-stu-id="6ea8e-105">Method</span></span>|<span data-ttu-id="6ea8e-106">描述</span><span class="sxs-lookup"><span data-stu-id="6ea8e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ea8e-107">GetMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="6ea8e-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="6ea8e-108">要求调试器返回模块（完成该调试器请求的操作需要其元数据）的完整路径。</span><span class="sxs-lookup"><span data-stu-id="6ea8e-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ea8e-109">备注</span><span class="sxs-lookup"><span data-stu-id="6ea8e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ea8e-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="6ea8e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea8e-111">要求</span><span class="sxs-lookup"><span data-stu-id="6ea8e-111">Requirements</span></span>  
 <span data-ttu-id="6ea8e-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea8e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea8e-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ea8e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ea8e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ea8e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ea8e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea8e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea8e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea8e-116">See also</span></span>

- [<span data-ttu-id="6ea8e-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="6ea8e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6ea8e-118">调试</span><span class="sxs-lookup"><span data-stu-id="6ea8e-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
