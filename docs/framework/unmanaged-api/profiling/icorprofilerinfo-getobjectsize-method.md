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
ms.openlocfilehash: d366a0093ca82d2e5b3c40729777a1b6c0766bda
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049539"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="f44f7-102">ICorProfilerInfo::GetObjectSize 方法</span><span class="sxs-lookup"><span data-stu-id="f44f7-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="f44f7-103">获取指定对象的大小。</span><span class="sxs-lookup"><span data-stu-id="f44f7-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f44f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="f44f7-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f44f7-105">参数</span><span class="sxs-lookup"><span data-stu-id="f44f7-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="f44f7-106">[in]对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="f44f7-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="f44f7-107">[out]指向对象的大小，以字节为单位的指针。</span><span class="sxs-lookup"><span data-stu-id="f44f7-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f44f7-108">备注</span><span class="sxs-lookup"><span data-stu-id="f44f7-108">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f44f7-109">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="f44f7-109">This method is obsolete.</span></span> <span data-ttu-id="f44f7-110">它返回 COR_E_OVERFLOW 对象大于 4 GB 64 位平台上。</span><span class="sxs-lookup"><span data-stu-id="f44f7-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="f44f7-111">使用[ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="f44f7-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="f44f7-112">相同类型的不同对象通常具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="f44f7-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="f44f7-113">但是，某些类型，如数组或字符串，可能具有不同大小的每个对象。</span><span class="sxs-lookup"><span data-stu-id="f44f7-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="f44f7-114">返回的大小`GetObjectSize`方法不包括任何可能出现在垃圾回收堆上对象后的对齐方式填充。</span><span class="sxs-lookup"><span data-stu-id="f44f7-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="f44f7-115">如果使用`GetObjectSize`方法上垃圾回收堆，提前对象之间添加根据需要手动填充的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="f44f7-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="f44f7-116">在 32 位 Windows 上 COR_PRF_GC_GEN_0、 COR_PRF_GC_GEN_1 和 COR_PRF_GC_GEN_2 使用 4 字节对齐方式，并 COR_PRF_GC_LARGE_OBJECT_HEAP 使用 8 字节对齐方式。</span><span class="sxs-lookup"><span data-stu-id="f44f7-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="f44f7-117">在 64 位 Windows 上的对齐方式始终是 8 个字节。</span><span class="sxs-lookup"><span data-stu-id="f44f7-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f44f7-118">要求</span><span class="sxs-lookup"><span data-stu-id="f44f7-118">Requirements</span></span>  
 <span data-ttu-id="f44f7-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f44f7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f44f7-120">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f44f7-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f44f7-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f44f7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f44f7-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f44f7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f44f7-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f44f7-123">See also</span></span>

- [<span data-ttu-id="f44f7-124">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="f44f7-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
