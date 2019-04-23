---
title: ICorDebugProcess3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ccc45482f691d9950c641ef126a657052a280e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213624"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="9d063-102">ICorDebugProcess3 接口</span><span class="sxs-lookup"><span data-stu-id="9d063-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="9d063-103">控制自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="9d063-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d063-104">方法</span><span class="sxs-lookup"><span data-stu-id="9d063-104">Methods</span></span>  
  
|<span data-ttu-id="9d063-105">方法</span><span class="sxs-lookup"><span data-stu-id="9d063-105">Method</span></span>|<span data-ttu-id="9d063-106">描述</span><span class="sxs-lookup"><span data-stu-id="9d063-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d063-107">SetEnableCustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="9d063-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="9d063-108">启用和禁用的指定类型的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="9d063-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d063-109">备注</span><span class="sxs-lookup"><span data-stu-id="9d063-109">Remarks</span></span>  
 <span data-ttu-id="9d063-110">此接口进行逻辑扩展的 ICorDebugProcess 和 ICorDebugProcess2 接口。</span><span class="sxs-lookup"><span data-stu-id="9d063-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d063-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="9d063-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d063-112">要求</span><span class="sxs-lookup"><span data-stu-id="9d063-112">Requirements</span></span>  
 <span data-ttu-id="9d063-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d063-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d063-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d063-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d063-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d063-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d063-116">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d063-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d063-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d063-117">See also</span></span>

- [<span data-ttu-id="9d063-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="9d063-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9d063-119">调试</span><span class="sxs-lookup"><span data-stu-id="9d063-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
