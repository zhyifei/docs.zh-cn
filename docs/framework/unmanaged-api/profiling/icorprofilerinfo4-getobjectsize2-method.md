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
ms.openlocfilehash: 8ebbc3422f48c0c2b8ff7b807228c63fbb35dd7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454091"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="240ec-102">ICorProfilerInfo4::GetObjectSize2 方法</span><span class="sxs-lookup"><span data-stu-id="240ec-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="240ec-103">返回指定对象的大小。</span><span class="sxs-lookup"><span data-stu-id="240ec-103">Returns the size of a specified object.</span></span> <span data-ttu-id="240ec-104">替换[icorprofilerinfo:: Getobjectsize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)通过报告大于什么可以用来表示的对象的大小的方法`ULONG`。</span><span class="sxs-lookup"><span data-stu-id="240ec-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="240ec-105">语法</span><span class="sxs-lookup"><span data-stu-id="240ec-105">Syntax</span></span>  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="240ec-106">参数</span><span class="sxs-lookup"><span data-stu-id="240ec-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="240ec-107">[in]对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="240ec-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="240ec-108">[out]指向对象的大小，以字节为单位的指针。</span><span class="sxs-lookup"><span data-stu-id="240ec-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="240ec-109">备注</span><span class="sxs-lookup"><span data-stu-id="240ec-109">Remarks</span></span>  
 <span data-ttu-id="240ec-110">相同的类型的不同对象通常具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="240ec-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="240ec-111">但是，某些类型，如数组或字符串，可能具有不同大小的每个对象。</span><span class="sxs-lookup"><span data-stu-id="240ec-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="240ec-112">要求</span><span class="sxs-lookup"><span data-stu-id="240ec-112">Requirements</span></span>  
 <span data-ttu-id="240ec-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="240ec-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="240ec-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="240ec-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="240ec-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="240ec-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="240ec-116">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="240ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240ec-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="240ec-117">See Also</span></span>  
 [<span data-ttu-id="240ec-118">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="240ec-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
