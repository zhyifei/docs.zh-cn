---
title: ICorProfilerModuleEnum::GetCount 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 190d6477e0474a7f865f231dbf116e845a403a34
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471181"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="e3524-102">ICorProfilerModuleEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="e3524-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="e3524-103">获取已加载到应用程序的托管模块数。</span><span class="sxs-lookup"><span data-stu-id="e3524-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3524-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3524-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3524-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3524-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e3524-106">[out]集合中的运行时模块数。</span><span class="sxs-lookup"><span data-stu-id="e3524-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3524-107">要求</span><span class="sxs-lookup"><span data-stu-id="e3524-107">Requirements</span></span>  
 <span data-ttu-id="e3524-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3524-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3524-109">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3524-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3524-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3524-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3524-111">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3524-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3524-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3524-112">See also</span></span>
- [<span data-ttu-id="e3524-113">ICorProfilerModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="e3524-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="e3524-114">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="e3524-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
