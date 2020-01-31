---
title: ICorDebugBoxValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
ms.openlocfilehash: 1ec54f4fe36aaf38d7c0ce0586733729bd2fddea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784470"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="8684d-102">ICorDebugBoxValue 接口</span><span class="sxs-lookup"><span data-stu-id="8684d-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="8684d-103">表示装箱值类对象的 "ICorDebugHeapValue" 的子类。</span><span class="sxs-lookup"><span data-stu-id="8684d-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8684d-104">方法</span><span class="sxs-lookup"><span data-stu-id="8684d-104">Methods</span></span>  
  
|<span data-ttu-id="8684d-105">方法</span><span class="sxs-lookup"><span data-stu-id="8684d-105">Method</span></span>|<span data-ttu-id="8684d-106">描述</span><span class="sxs-lookup"><span data-stu-id="8684d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8684d-107">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="8684d-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="8684d-108">获取指向装箱的 "ICorDebugObjectValue" 实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="8684d-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8684d-109">备注</span><span class="sxs-lookup"><span data-stu-id="8684d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8684d-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8684d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8684d-111">需求</span><span class="sxs-lookup"><span data-stu-id="8684d-111">Requirements</span></span>  
 <span data-ttu-id="8684d-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8684d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8684d-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8684d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8684d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8684d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8684d-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8684d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8684d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8684d-116">See also</span></span>

- [<span data-ttu-id="8684d-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="8684d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
