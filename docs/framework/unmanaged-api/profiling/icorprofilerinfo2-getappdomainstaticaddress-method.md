---
title: ICorProfilerInfo2::GetAppDomainStaticAddress 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 05d8c44655d8670194035c336bd62ae5d53bfec3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862953"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="9943c-102">ICorProfilerInfo2::GetAppDomainStaticAddress 方法</span><span class="sxs-lookup"><span data-stu-id="9943c-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="9943c-103">获取指定应用程序域静态字段在指定应用程序域范围内的地址。</span><span class="sxs-lookup"><span data-stu-id="9943c-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9943c-104">语法</span><span class="sxs-lookup"><span data-stu-id="9943c-104">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9943c-105">参数</span><span class="sxs-lookup"><span data-stu-id="9943c-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="9943c-106">中包含请求的应用程序域静态字段的类的类 ID。</span><span class="sxs-lookup"><span data-stu-id="9943c-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="9943c-107">中请求的应用程序域静态字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="9943c-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="9943c-108">中作为所请求的静态字段的作用域的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="9943c-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="9943c-109">弄指向指定应用程序域中的静态字段的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9943c-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9943c-110">备注</span><span class="sxs-lookup"><span data-stu-id="9943c-110">Remarks</span></span>  
 <span data-ttu-id="9943c-111">`GetAppDomainStaticAddress` 方法可能会返回以下内容之一：</span><span class="sxs-lookup"><span data-stu-id="9943c-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="9943c-112">如果未在指定的上下文中为给定的静态字段分配地址，则 CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="9943c-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="9943c-113">可能位于垃圾回收堆中的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="9943c-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="9943c-114">这些地址可能会在垃圾回收后失效，因此，在垃圾回收后，探查器不应假定它们是有效的。</span><span class="sxs-lookup"><span data-stu-id="9943c-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="9943c-115">在类的类构造函数完成之前，尽管某些静态字段可能已经初始化并为垃圾回收对象提供了根，`GetAppDomainStaticAddress` 仍将返回其所有静态字段的 CORPROF_E_DATAINCOMPLETE。</span><span class="sxs-lookup"><span data-stu-id="9943c-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9943c-116">需求</span><span class="sxs-lookup"><span data-stu-id="9943c-116">Requirements</span></span>  
 <span data-ttu-id="9943c-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9943c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9943c-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9943c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9943c-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9943c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9943c-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9943c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9943c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9943c-121">See also</span></span>

- [<span data-ttu-id="9943c-122">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="9943c-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="9943c-123">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="9943c-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
