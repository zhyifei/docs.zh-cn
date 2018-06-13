---
title: ICorDebugNativeFrame2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd8f1adee6bbcb3b57b87a2d6c85c01c624da9ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421225"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="4d72e-102">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="4d72e-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="4d72e-103">提供用于测试子帧与父帧关系的方法。</span><span class="sxs-lookup"><span data-stu-id="4d72e-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d72e-104">方法</span><span class="sxs-lookup"><span data-stu-id="4d72e-104">Methods</span></span>  
  
|<span data-ttu-id="4d72e-105">方法</span><span class="sxs-lookup"><span data-stu-id="4d72e-105">Method</span></span>|<span data-ttu-id="4d72e-106">描述</span><span class="sxs-lookup"><span data-stu-id="4d72e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d72e-107">IsChild 方法</span><span class="sxs-lookup"><span data-stu-id="4d72e-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="4d72e-108">确定当前帧是否子帧。</span><span class="sxs-lookup"><span data-stu-id="4d72e-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="4d72e-109">IsMatchingParentFrame 方法</span><span class="sxs-lookup"><span data-stu-id="4d72e-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="4d72e-110">确定是否为指定的框架为当前帧的父级。</span><span class="sxs-lookup"><span data-stu-id="4d72e-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="4d72e-111">GetStackParameterSize 方法</span><span class="sxs-lookup"><span data-stu-id="4d72e-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="4d72e-112">在 x86 操作系统上的堆栈上返回参数的累积大小。</span><span class="sxs-lookup"><span data-stu-id="4d72e-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d72e-113">备注</span><span class="sxs-lookup"><span data-stu-id="4d72e-113">Remarks</span></span>  
 <span data-ttu-id="4d72e-114">此接口进行逻辑扩展"ICorDebugNativeFrame"接口。</span><span class="sxs-lookup"><span data-stu-id="4d72e-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d72e-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4d72e-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d72e-116">要求</span><span class="sxs-lookup"><span data-stu-id="4d72e-116">Requirements</span></span>  
 <span data-ttu-id="4d72e-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d72e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d72e-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d72e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d72e-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d72e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d72e-120">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d72e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d72e-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d72e-121">See Also</span></span>  
    
 [<span data-ttu-id="4d72e-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="4d72e-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4d72e-123">调试</span><span class="sxs-lookup"><span data-stu-id="4d72e-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
