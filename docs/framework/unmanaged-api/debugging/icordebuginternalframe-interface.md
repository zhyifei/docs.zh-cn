---
title: ICorDebugInternalFrame 接口 1
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
ms.openlocfilehash: 45a710e6d8be4a041d9852585ea83fea85376f66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413821"
---
# <a name="icordebuginternalframe-interface1"></a><span data-ttu-id="bf076-102">ICorDebugInternalFrame 接口 1</span><span class="sxs-lookup"><span data-stu-id="bf076-102">ICorDebugInternalFrame Interface1</span></span>
<span data-ttu-id="bf076-103">表示在堆栈上的运行时内部帧。</span><span class="sxs-lookup"><span data-stu-id="bf076-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="bf076-104">此接口是 ICorDebugFrame 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="bf076-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf076-105">方法</span><span class="sxs-lookup"><span data-stu-id="bf076-105">Methods</span></span>  
  
|<span data-ttu-id="bf076-106">方法</span><span class="sxs-lookup"><span data-stu-id="bf076-106">Method</span></span>|<span data-ttu-id="bf076-107">描述</span><span class="sxs-lookup"><span data-stu-id="bf076-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf076-108">GetFrameType 方法</span><span class="sxs-lookup"><span data-stu-id="bf076-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="bf076-109">获取此内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="bf076-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf076-110">备注</span><span class="sxs-lookup"><span data-stu-id="bf076-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf076-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="bf076-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf076-112">要求</span><span class="sxs-lookup"><span data-stu-id="bf076-112">Requirements</span></span>  
 <span data-ttu-id="bf076-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf076-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf076-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf076-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf076-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf076-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf076-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf076-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf076-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf076-117">See Also</span></span>  
 [<span data-ttu-id="bf076-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="bf076-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
