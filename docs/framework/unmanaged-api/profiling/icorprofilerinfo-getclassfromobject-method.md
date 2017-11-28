---
title: "ICorProfilerInfo::GetClassFromObject 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetClassFromObject
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 706118a197677ec97672cca36f5bcf6421a1c328
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="bbf04-102">ICorProfilerInfo::GetClassFromObject 方法</span><span class="sxs-lookup"><span data-stu-id="bbf04-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="bbf04-103">获取`ClassID`的对象，提供其`ObjectID`。</span><span class="sxs-lookup"><span data-stu-id="bbf04-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbf04-104">语法</span><span class="sxs-lookup"><span data-stu-id="bbf04-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbf04-105">参数</span><span class="sxs-lookup"><span data-stu-id="bbf04-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="bbf04-106">[in]要为其获取对象的 ID `ClassID`。</span><span class="sxs-lookup"><span data-stu-id="bbf04-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="bbf04-107">[out]指向返回的指针`ClassID`。</span><span class="sxs-lookup"><span data-stu-id="bbf04-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbf04-108">备注</span><span class="sxs-lookup"><span data-stu-id="bbf04-108">Remarks</span></span>  
 <span data-ttu-id="bbf04-109">Null`pClassId`指示`objectId`具有正在卸载的类型。</span><span class="sxs-lookup"><span data-stu-id="bbf04-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbf04-110">要求</span><span class="sxs-lookup"><span data-stu-id="bbf04-110">Requirements</span></span>  
 <span data-ttu-id="bbf04-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf04-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbf04-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bbf04-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bbf04-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbf04-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbf04-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbf04-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf04-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbf04-115">See Also</span></span>  
 [<span data-ttu-id="bbf04-116">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="bbf04-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
