---
title: ICorProfilerObjectEnum::GetCount 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f08b3d9634362d47615fe14287ab9ec35e78ee65
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775059"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="b632c-102">ICorProfilerObjectEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="b632c-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="b632c-103">获取集合中的冻结对象总数。</span><span class="sxs-lookup"><span data-stu-id="b632c-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b632c-104">语法</span><span class="sxs-lookup"><span data-stu-id="b632c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b632c-105">参数</span><span class="sxs-lookup"><span data-stu-id="b632c-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="b632c-106">[out]指向集合中的冻结对象数的指针。</span><span class="sxs-lookup"><span data-stu-id="b632c-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="b632c-107">此方法将始终返回零的.NET Framework 3.5 版 Service Pack 1 (SP1) 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="b632c-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b632c-108">要求</span><span class="sxs-lookup"><span data-stu-id="b632c-108">Requirements</span></span>  
 <span data-ttu-id="b632c-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b632c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b632c-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b632c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b632c-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b632c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b632c-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b632c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b632c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b632c-113">See also</span></span>

- [<span data-ttu-id="b632c-114">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b632c-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
