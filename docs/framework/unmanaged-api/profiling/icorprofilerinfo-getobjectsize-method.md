---
title: "ICorProfilerInfo::GetObjectSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetObjectSize
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9425938042485c4330fe3fbc50cdabde6451b427
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="88b2f-102">ICorProfilerInfo::GetObjectSize 方法</span><span class="sxs-lookup"><span data-stu-id="88b2f-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="88b2f-103">获取指定对象的大小。</span><span class="sxs-lookup"><span data-stu-id="88b2f-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88b2f-104">语法</span><span class="sxs-lookup"><span data-stu-id="88b2f-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88b2f-105">参数</span><span class="sxs-lookup"><span data-stu-id="88b2f-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="88b2f-106">[in]对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="88b2f-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="88b2f-107">[out]指向对象的大小，以字节为单位的指针。</span><span class="sxs-lookup"><span data-stu-id="88b2f-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88b2f-108">备注</span><span class="sxs-lookup"><span data-stu-id="88b2f-108">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88b2f-109">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="88b2f-109">This method is obsolete.</span></span> <span data-ttu-id="88b2f-110">它返回 COR_E_OVERFLOW 对象大于 4 GB 在 64 位平台上。</span><span class="sxs-lookup"><span data-stu-id="88b2f-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="88b2f-111">使用[icorprofilerinfo4:: Getobjectsize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="88b2f-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="88b2f-112">相同的类型的不同对象通常具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="88b2f-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="88b2f-113">但是，某些类型，如数组或字符串，可能具有不同大小的每个对象。</span><span class="sxs-lookup"><span data-stu-id="88b2f-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="88b2f-114">通过返回的大小`GetObjectSize`方法不包括在垃圾回收堆上对象后可能会出现任何对齐方式填充。</span><span class="sxs-lookup"><span data-stu-id="88b2f-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="88b2f-115">如果你使用`GetObjectSize`方法，使对象与对象前进上垃圾回收堆中，添加手动，根据需要填充的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="88b2f-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
-   <span data-ttu-id="88b2f-116">在 32 位 Windows 上，COR_PRF_GC_GEN_0、 COR_PRF_GC_GEN_1 和 COR_PRF_GC_GEN_2 使用 4 字节对齐方式，并 COR_PRF_GC_LARGE_OBJECT_HEAP 使用 8 字节对齐方式。</span><span class="sxs-lookup"><span data-stu-id="88b2f-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
-   <span data-ttu-id="88b2f-117">在 64 位 Windows 上对齐始终是 8 个字节。</span><span class="sxs-lookup"><span data-stu-id="88b2f-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88b2f-118">惠?</span><span class="sxs-lookup"><span data-stu-id="88b2f-118">Requirements</span></span>  
 <span data-ttu-id="88b2f-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88b2f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88b2f-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="88b2f-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="88b2f-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88b2f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88b2f-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88b2f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b2f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="88b2f-123">See Also</span></span>  
 [<span data-ttu-id="88b2f-124">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="88b2f-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
