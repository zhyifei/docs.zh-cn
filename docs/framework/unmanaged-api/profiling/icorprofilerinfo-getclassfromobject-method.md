---
title: ICorProfilerInfo::GetClassFromObject 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
ms.openlocfilehash: a5573765486112a83f5ea7cc9258447692f72166
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864046"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="89113-102">ICorProfilerInfo::GetClassFromObject 方法</span><span class="sxs-lookup"><span data-stu-id="89113-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="89113-103">在给定对象 `ObjectID`的情况下，获取该对象的 `ClassID`。</span><span class="sxs-lookup"><span data-stu-id="89113-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89113-104">语法</span><span class="sxs-lookup"><span data-stu-id="89113-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89113-105">参数</span><span class="sxs-lookup"><span data-stu-id="89113-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="89113-106">中要获取其 `ClassID`的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="89113-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="89113-107">弄指向返回的 `ClassID`的指针。</span><span class="sxs-lookup"><span data-stu-id="89113-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89113-108">备注</span><span class="sxs-lookup"><span data-stu-id="89113-108">Remarks</span></span>  
 <span data-ttu-id="89113-109">Null `pClassId` 指示 `objectId` 具有正在卸载的类型。</span><span class="sxs-lookup"><span data-stu-id="89113-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89113-110">需求</span><span class="sxs-lookup"><span data-stu-id="89113-110">Requirements</span></span>  
 <span data-ttu-id="89113-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89113-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89113-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89113-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89113-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89113-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89113-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89113-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89113-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89113-115">See also</span></span>

- [<span data-ttu-id="89113-116">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="89113-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
