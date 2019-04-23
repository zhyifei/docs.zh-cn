---
title: ICorProfilerInfo4::GetObjectSize2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15829e08a755b91ff91ca939b92a5a87bd377e8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176288"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="18d2e-102">ICorProfilerInfo4::GetObjectSize2 方法</span><span class="sxs-lookup"><span data-stu-id="18d2e-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="18d2e-103">返回指定对象的大小。</span><span class="sxs-lookup"><span data-stu-id="18d2e-103">Returns the size of a specified object.</span></span> <span data-ttu-id="18d2e-104">将替换[icorprofilerinfo:: Getobjectsize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)通过报告大小大于可表达中的对象的方法`ULONG`。</span><span class="sxs-lookup"><span data-stu-id="18d2e-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d2e-105">语法</span><span class="sxs-lookup"><span data-stu-id="18d2e-105">Syntax</span></span>  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18d2e-106">参数</span><span class="sxs-lookup"><span data-stu-id="18d2e-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="18d2e-107">[in]对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="18d2e-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="18d2e-108">[out]指向对象的大小，以字节为单位的指针。</span><span class="sxs-lookup"><span data-stu-id="18d2e-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18d2e-109">备注</span><span class="sxs-lookup"><span data-stu-id="18d2e-109">Remarks</span></span>  
 <span data-ttu-id="18d2e-110">相同类型的不同对象通常具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="18d2e-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="18d2e-111">但是，某些类型，如数组或字符串，可能具有不同大小的每个对象。</span><span class="sxs-lookup"><span data-stu-id="18d2e-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18d2e-112">要求</span><span class="sxs-lookup"><span data-stu-id="18d2e-112">Requirements</span></span>  
 <span data-ttu-id="18d2e-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18d2e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18d2e-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18d2e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="18d2e-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18d2e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18d2e-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18d2e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18d2e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="18d2e-117">See also</span></span>

- [<span data-ttu-id="18d2e-118">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="18d2e-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
