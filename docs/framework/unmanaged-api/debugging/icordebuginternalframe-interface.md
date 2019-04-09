---
title: ICorDebugInternalFrame 接口
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f16b4628215bee2410708edeb337b41fbdc0311
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109819"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="47c0d-102">ICorDebugInternalFrame 接口</span><span class="sxs-lookup"><span data-stu-id="47c0d-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="47c0d-103">表示运行时内部框架在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="47c0d-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="47c0d-104">此接口是 ICorDebugFrame 接口子类。</span><span class="sxs-lookup"><span data-stu-id="47c0d-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47c0d-105">方法</span><span class="sxs-lookup"><span data-stu-id="47c0d-105">Methods</span></span>  
  
|<span data-ttu-id="47c0d-106">方法</span><span class="sxs-lookup"><span data-stu-id="47c0d-106">Method</span></span>|<span data-ttu-id="47c0d-107">描述</span><span class="sxs-lookup"><span data-stu-id="47c0d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47c0d-108">GetFrameType 方法</span><span class="sxs-lookup"><span data-stu-id="47c0d-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="47c0d-109">获取此内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="47c0d-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47c0d-110">备注</span><span class="sxs-lookup"><span data-stu-id="47c0d-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47c0d-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="47c0d-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c0d-112">要求</span><span class="sxs-lookup"><span data-stu-id="47c0d-112">Requirements</span></span>  
 <span data-ttu-id="47c0d-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47c0d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47c0d-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47c0d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47c0d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47c0d-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="47c0d-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="47c0d-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="47c0d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="47c0d-117">See also</span></span>

- [<span data-ttu-id="47c0d-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="47c0d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
