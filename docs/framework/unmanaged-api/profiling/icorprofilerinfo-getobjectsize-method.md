---
title: ICorProfilerInfo::GetObjectSize 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ad2092c902b137df0dfe108743ef4081ca5f04d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948118"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="3a32c-102">ICorProfilerInfo::GetObjectSize 方法</span><span class="sxs-lookup"><span data-stu-id="3a32c-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="3a32c-103">获取指定对象的大小。</span><span class="sxs-lookup"><span data-stu-id="3a32c-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a32c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a32c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a32c-105">参数</span><span class="sxs-lookup"><span data-stu-id="3a32c-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="3a32c-106">中对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="3a32c-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="3a32c-107">弄一个指针, 指向对象的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="3a32c-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a32c-108">备注</span><span class="sxs-lookup"><span data-stu-id="3a32c-108">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3a32c-109">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="3a32c-109">This method is obsolete.</span></span> <span data-ttu-id="3a32c-110">对于64位平台上大于4GB 的对象, 它将返回 COR_E_OVERFLOW。</span><span class="sxs-lookup"><span data-stu-id="3a32c-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="3a32c-111">改为使用[ICorProfilerInfo4:: GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3a32c-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="3a32c-112">相同类型的不同对象通常具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="3a32c-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="3a32c-113">但是, 某些类型 (例如数组或字符串) 对于每个对象可能有不同的大小。</span><span class="sxs-lookup"><span data-stu-id="3a32c-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="3a32c-114">`GetObjectSize`方法返回的大小不包括对象在垃圾回收堆上时可能出现的任何对齐填充。</span><span class="sxs-lookup"><span data-stu-id="3a32c-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="3a32c-115">如果使用`GetObjectSize`方法从对象到垃圾回收堆上的对象前进, 请根据需要手动添加对齐填充。</span><span class="sxs-lookup"><span data-stu-id="3a32c-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="3a32c-116">在32位 Windows、COR_PRF_GC_GEN_0、COR_PRF_GC_GEN_1 和 COR_PRF_GC_GEN_2 上, 使用4字节对齐, 而 COR_PRF_GC_LARGE_OBJECT_HEAP 使用8字节对齐。</span><span class="sxs-lookup"><span data-stu-id="3a32c-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="3a32c-117">在64位 Windows 上, 对齐始终为8个字节。</span><span class="sxs-lookup"><span data-stu-id="3a32c-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a32c-118">要求</span><span class="sxs-lookup"><span data-stu-id="3a32c-118">Requirements</span></span>  
 <span data-ttu-id="3a32c-119">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3a32c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a32c-120">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="3a32c-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a32c-121">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a32c-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a32c-122">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a32c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a32c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a32c-123">See also</span></span>

- [<span data-ttu-id="3a32c-124">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="3a32c-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
