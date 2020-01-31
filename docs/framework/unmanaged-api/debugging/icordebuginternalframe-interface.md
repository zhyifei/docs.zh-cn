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
ms.openlocfilehash: 6bc24450cdda2e3ed324256b53b2d137d1eb90e4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788485"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="4c9da-102">ICorDebugInternalFrame 接口</span><span class="sxs-lookup"><span data-stu-id="4c9da-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="4c9da-103">表示堆栈上的运行时内部帧。</span><span class="sxs-lookup"><span data-stu-id="4c9da-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="4c9da-104">此接口是 ICorDebugFrame 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="4c9da-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c9da-105">方法</span><span class="sxs-lookup"><span data-stu-id="4c9da-105">Methods</span></span>  
  
|<span data-ttu-id="4c9da-106">方法</span><span class="sxs-lookup"><span data-stu-id="4c9da-106">Method</span></span>|<span data-ttu-id="4c9da-107">描述</span><span class="sxs-lookup"><span data-stu-id="4c9da-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c9da-108">GetFrameType 方法</span><span class="sxs-lookup"><span data-stu-id="4c9da-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="4c9da-109">获取此内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="4c9da-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c9da-110">备注</span><span class="sxs-lookup"><span data-stu-id="4c9da-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c9da-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4c9da-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c9da-112">需求</span><span class="sxs-lookup"><span data-stu-id="4c9da-112">Requirements</span></span>  
 <span data-ttu-id="4c9da-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c9da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c9da-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c9da-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c9da-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c9da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c9da-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c9da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9da-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c9da-117">See also</span></span>

- [<span data-ttu-id="4c9da-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="4c9da-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
