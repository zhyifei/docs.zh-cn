---
title: ICorDebugValue3::GetSize64 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c0b45e08f7b88d9374023f95c6e3e22139c8949
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144763"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="8acc9-102">ICorDebugValue3::GetSize64 方法</span><span class="sxs-lookup"><span data-stu-id="8acc9-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="8acc9-103">获取大小，以字节为单位，此[ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="8acc9-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8acc9-104">语法</span><span class="sxs-lookup"><span data-stu-id="8acc9-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8acc9-105">参数</span><span class="sxs-lookup"><span data-stu-id="8acc9-105">Parameters</span></span>  
 <span data-ttu-id="8acc9-106">pSize</span><span class="sxs-lookup"><span data-stu-id="8acc9-106">pSize</span></span>  
 <span data-ttu-id="8acc9-107">[out]指向的大小，以字节为单位，此对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8acc9-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8acc9-108">备注</span><span class="sxs-lookup"><span data-stu-id="8acc9-108">Remarks</span></span>  
 <span data-ttu-id="8acc9-109">如果此值的类型是引用类型，此方法返回的指针的大小而不是对象的大小。</span><span class="sxs-lookup"><span data-stu-id="8acc9-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="8acc9-110">`ICorDebugValue3::GetSize`方法不同于[icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)及其输出参数的类型中的方法。</span><span class="sxs-lookup"><span data-stu-id="8acc9-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="8acc9-111">在中[icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)，输出参数是`ULONG32`; 在`ICorDebugValue3::GetSize`，它是`ULONG64`。</span><span class="sxs-lookup"><span data-stu-id="8acc9-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="8acc9-112">这使得[ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)接口报告的大小超过 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="8acc9-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8acc9-113">要求</span><span class="sxs-lookup"><span data-stu-id="8acc9-113">Requirements</span></span>  
 <span data-ttu-id="8acc9-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8acc9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8acc9-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8acc9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8acc9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8acc9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8acc9-117">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8acc9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8acc9-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8acc9-118">See also</span></span>

- [<span data-ttu-id="8acc9-119">ICorDebugValue3 接口</span><span class="sxs-lookup"><span data-stu-id="8acc9-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="8acc9-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="8acc9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
