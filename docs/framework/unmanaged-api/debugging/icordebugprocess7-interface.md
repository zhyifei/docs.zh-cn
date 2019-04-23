---
title: ICorDebugProcess7 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcess7
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 71aee5f3-5e10-44fa-be69-6d8a475f2c14
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0d73da04242bfe5a4958a62d2a48b609b474309
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195405"
---
# <a name="icordebugprocess7-interface"></a><span data-ttu-id="e36c0-102">ICorDebugProcess7 接口</span><span class="sxs-lookup"><span data-stu-id="e36c0-102">ICorDebugProcess7 Interface</span></span>
<span data-ttu-id="e36c0-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="e36c0-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e36c0-104">提供了一种方法，用于配置调试器以处理目标进程中的内存中元数据更新。</span><span class="sxs-lookup"><span data-stu-id="e36c0-104">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e36c0-105">方法</span><span class="sxs-lookup"><span data-stu-id="e36c0-105">Methods</span></span>  
  
|<span data-ttu-id="e36c0-106">方法</span><span class="sxs-lookup"><span data-stu-id="e36c0-106">Method</span></span>|<span data-ttu-id="e36c0-107">描述</span><span class="sxs-lookup"><span data-stu-id="e36c0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e36c0-108">SetWriteableMetadataUpdateMode 方法</span><span class="sxs-lookup"><span data-stu-id="e36c0-108">SetWriteableMetadataUpdateMode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)|<span data-ttu-id="e36c0-109">设置一个值，用于确定调试器如何处理目标进程中元数据的内存中更新。</span><span class="sxs-lookup"><span data-stu-id="e36c0-109">Sets a value that determines how the debugger handles in-memory updates to metadata within the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e36c0-110">备注</span><span class="sxs-lookup"><span data-stu-id="e36c0-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e36c0-111">要求</span><span class="sxs-lookup"><span data-stu-id="e36c0-111">Requirements</span></span>  
 <span data-ttu-id="e36c0-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e36c0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e36c0-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e36c0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e36c0-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e36c0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e36c0-115">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e36c0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36c0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e36c0-116">See also</span></span>

- [<span data-ttu-id="e36c0-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="e36c0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e36c0-118">调试</span><span class="sxs-lookup"><span data-stu-id="e36c0-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
