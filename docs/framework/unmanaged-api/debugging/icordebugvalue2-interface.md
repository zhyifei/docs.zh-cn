---
title: ICorDebugValue2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: ab5adabe868c245ed7a773d9b4206b25d9e9a4f0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140246"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="2e347-102">ICorDebugValue2 接口</span><span class="sxs-lookup"><span data-stu-id="2e347-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="2e347-103">扩展 "ICorDebugValue" 接口，以提供对 "ICorDebugType" 对象的支持。</span><span class="sxs-lookup"><span data-stu-id="2e347-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e347-104">方法</span><span class="sxs-lookup"><span data-stu-id="2e347-104">Methods</span></span>  
  
|<span data-ttu-id="2e347-105">方法</span><span class="sxs-lookup"><span data-stu-id="2e347-105">Method</span></span>|<span data-ttu-id="2e347-106">描述</span><span class="sxs-lookup"><span data-stu-id="2e347-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e347-107">GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="2e347-107">GetExactType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="2e347-108">获取一个接口指针，该指针指向表示此值的 <xref:System.Type> 的 `ICorDebugType` 对象。</span><span class="sxs-lookup"><span data-stu-id="2e347-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e347-109">备注</span><span class="sxs-lookup"><span data-stu-id="2e347-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e347-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="2e347-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e347-111">要求</span><span class="sxs-lookup"><span data-stu-id="2e347-111">Requirements</span></span>  
 <span data-ttu-id="2e347-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e347-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e347-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e347-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e347-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e347-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e347-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e347-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e347-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e347-116">See also</span></span>

- [<span data-ttu-id="2e347-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="2e347-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

- [<span data-ttu-id="2e347-118">ICorDebugValue3 接口</span><span class="sxs-lookup"><span data-stu-id="2e347-118">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
