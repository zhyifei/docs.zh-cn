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
ms.openlocfilehash: 22a3f39bc1f9b4e6cad1db4fd0a6480b7c04e8fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792754"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="b3e61-102">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="b3e61-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="b3e61-103">提供用于测试子帧与父帧关系的方法。</span><span class="sxs-lookup"><span data-stu-id="b3e61-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3e61-104">方法</span><span class="sxs-lookup"><span data-stu-id="b3e61-104">Methods</span></span>  
  
|<span data-ttu-id="b3e61-105">方法</span><span class="sxs-lookup"><span data-stu-id="b3e61-105">Method</span></span>|<span data-ttu-id="b3e61-106">描述</span><span class="sxs-lookup"><span data-stu-id="b3e61-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3e61-107">IsChild 方法</span><span class="sxs-lookup"><span data-stu-id="b3e61-107">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="b3e61-108">确定当前帧是否为子框架。</span><span class="sxs-lookup"><span data-stu-id="b3e61-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="b3e61-109">IsMatchingParentFrame 方法</span><span class="sxs-lookup"><span data-stu-id="b3e61-109">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="b3e61-110">确定指定的帧是否为当前帧的父级。</span><span class="sxs-lookup"><span data-stu-id="b3e61-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="b3e61-111">GetStackParameterSize 方法</span><span class="sxs-lookup"><span data-stu-id="b3e61-111">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="b3e61-112">返回 x86 操作系统上堆栈上的参数的累积大小。</span><span class="sxs-lookup"><span data-stu-id="b3e61-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3e61-113">备注</span><span class="sxs-lookup"><span data-stu-id="b3e61-113">Remarks</span></span>  
 <span data-ttu-id="b3e61-114">此接口以逻辑方式扩展了 "ICorDebugNativeFrame" 接口。</span><span class="sxs-lookup"><span data-stu-id="b3e61-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3e61-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="b3e61-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3e61-116">需求</span><span class="sxs-lookup"><span data-stu-id="b3e61-116">Requirements</span></span>  
 <span data-ttu-id="b3e61-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b3e61-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3e61-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3e61-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3e61-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3e61-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3e61-120">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3e61-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e61-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3e61-121">See also</span></span>

- [<span data-ttu-id="b3e61-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="b3e61-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b3e61-123">调试</span><span class="sxs-lookup"><span data-stu-id="b3e61-123">Debugging</span></span>](index.md)
