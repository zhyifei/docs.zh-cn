---
title: ICorProfilerInfo2::GetBoxClassLayout 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: 500cf74c320438fc1b78f0aac737b418716e1a11
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862823"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="def03-102">ICorProfilerInfo2::GetBoxClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="def03-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="def03-103">获取有关指定值类型的装箱位置的信息。</span><span class="sxs-lookup"><span data-stu-id="def03-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="def03-104">语法</span><span class="sxs-lookup"><span data-stu-id="def03-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="def03-105">参数</span><span class="sxs-lookup"><span data-stu-id="def03-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="def03-106">中描述装箱的值类型的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="def03-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="def03-107">弄一个整数，它是相对于值类型的装箱对象 ID 指针的偏移量。</span><span class="sxs-lookup"><span data-stu-id="def03-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="def03-108">备注</span><span class="sxs-lookup"><span data-stu-id="def03-108">Remarks</span></span>  
 <span data-ttu-id="def03-109">`pBufferOffset` 值是值类型在框中的位置。</span><span class="sxs-lookup"><span data-stu-id="def03-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="def03-110">将 `pBufferOffset` 应用于装箱对象后，可以使用值类型的类布局来解释该对象的值。</span><span class="sxs-lookup"><span data-stu-id="def03-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="def03-111">需求</span><span class="sxs-lookup"><span data-stu-id="def03-111">Requirements</span></span>  
 <span data-ttu-id="def03-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="def03-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="def03-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="def03-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="def03-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="def03-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="def03-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="def03-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def03-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="def03-116">See also</span></span>

- [<span data-ttu-id="def03-117">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="def03-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="def03-118">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="def03-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
