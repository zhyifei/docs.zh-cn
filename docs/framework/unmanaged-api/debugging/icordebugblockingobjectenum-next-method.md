---
title: ICorDebugBlockingObjectEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e94e4da0eea06ce9cc0110002b1def9e4dd4989
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939147"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="f0cff-102">ICorDebugBlockingObjectEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="f0cff-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="f0cff-103">从当前位置开始, 获取枚举中指定的[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)对象数。</span><span class="sxs-lookup"><span data-stu-id="f0cff-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0cff-104">语法</span><span class="sxs-lookup"><span data-stu-id="f0cff-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0cff-105">参数</span><span class="sxs-lookup"><span data-stu-id="f0cff-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f0cff-106">中要检索的对象的数目。</span><span class="sxs-lookup"><span data-stu-id="f0cff-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="f0cff-107">弄指向[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)对象的指针的数组。</span><span class="sxs-lookup"><span data-stu-id="f0cff-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f0cff-108">弄一个指针, 指向已检索到的对象的数目。</span><span class="sxs-lookup"><span data-stu-id="f0cff-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0cff-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f0cff-109">Return Value</span></span>  
 <span data-ttu-id="f0cff-110">此方法会返回以下特定的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="f0cff-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="f0cff-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0cff-111">HRESULT</span></span>|<span data-ttu-id="f0cff-112">描述</span><span class="sxs-lookup"><span data-stu-id="f0cff-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0cff-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0cff-113">S_OK</span></span>|<span data-ttu-id="f0cff-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="f0cff-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f0cff-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f0cff-115">S_FALSE</span></span>|<span data-ttu-id="f0cff-116">`pceltFetched` 不等于 `celt`。</span><span class="sxs-lookup"><span data-stu-id="f0cff-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0cff-117">备注</span><span class="sxs-lookup"><span data-stu-id="f0cff-117">Remarks</span></span>  
 <span data-ttu-id="f0cff-118">此方法的功能类似于典型的 COM 枚举器。</span><span class="sxs-lookup"><span data-stu-id="f0cff-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="f0cff-119">输入数组值必须至少为大小`celt`。</span><span class="sxs-lookup"><span data-stu-id="f0cff-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="f0cff-120">数组将用枚举中的下一个`celt`值填充, 如果小于`celt`保留, 则用所有剩余值填充。</span><span class="sxs-lookup"><span data-stu-id="f0cff-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="f0cff-121">此方法返回时, `pceltFetched`将用检索到的值的数目进行填充。</span><span class="sxs-lookup"><span data-stu-id="f0cff-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="f0cff-122">如果`values`包含无效指针或指向`celt`小于的缓冲区, 或者如果`pceltFetched`是无效指针, 则结果是不确定的。</span><span class="sxs-lookup"><span data-stu-id="f0cff-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0cff-123">尽管不需要释放[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构, 但它内的 "ICorDebugValue" 接口需要释放。</span><span class="sxs-lookup"><span data-stu-id="f0cff-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0cff-124">要求</span><span class="sxs-lookup"><span data-stu-id="f0cff-124">Requirements</span></span>  
 <span data-ttu-id="f0cff-125">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f0cff-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0cff-126">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="f0cff-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0cff-127">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0cff-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0cff-128">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0cff-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0cff-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0cff-129">See also</span></span>

- [<span data-ttu-id="f0cff-130">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="f0cff-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="f0cff-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="f0cff-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f0cff-132">调试</span><span class="sxs-lookup"><span data-stu-id="f0cff-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
