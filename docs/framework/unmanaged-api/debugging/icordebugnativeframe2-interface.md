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
ms.openlocfilehash: cc664d308d4db3e97597d785eda159e32255fa54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987839"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="8a029-102">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="8a029-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="8a029-103">提供用于测试子帧与父帧关系的方法。</span><span class="sxs-lookup"><span data-stu-id="8a029-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a029-104">方法</span><span class="sxs-lookup"><span data-stu-id="8a029-104">Methods</span></span>  
  
|<span data-ttu-id="8a029-105">方法</span><span class="sxs-lookup"><span data-stu-id="8a029-105">Method</span></span>|<span data-ttu-id="8a029-106">描述</span><span class="sxs-lookup"><span data-stu-id="8a029-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a029-107">IsChild 方法</span><span class="sxs-lookup"><span data-stu-id="8a029-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="8a029-108">确定当前帧是否为子框架。</span><span class="sxs-lookup"><span data-stu-id="8a029-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="8a029-109">IsMatchingParentFrame 方法</span><span class="sxs-lookup"><span data-stu-id="8a029-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="8a029-110">确定指定的范围是否为当前帧的父级。</span><span class="sxs-lookup"><span data-stu-id="8a029-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="8a029-111">GetStackParameterSize 方法</span><span class="sxs-lookup"><span data-stu-id="8a029-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="8a029-112">返回参数的累积大小 x86 操作系统上的堆栈上。</span><span class="sxs-lookup"><span data-stu-id="8a029-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a029-113">备注</span><span class="sxs-lookup"><span data-stu-id="8a029-113">Remarks</span></span>  
 <span data-ttu-id="8a029-114">此接口进行逻辑扩展"ICorDebugNativeFrame"接口。</span><span class="sxs-lookup"><span data-stu-id="8a029-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a029-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8a029-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a029-116">要求</span><span class="sxs-lookup"><span data-stu-id="8a029-116">Requirements</span></span>  
 <span data-ttu-id="8a029-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a029-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a029-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a029-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a029-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a029-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a029-120">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a029-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a029-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a029-121">See also</span></span>

- [<span data-ttu-id="8a029-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="8a029-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="8a029-123">调试</span><span class="sxs-lookup"><span data-stu-id="8a029-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
