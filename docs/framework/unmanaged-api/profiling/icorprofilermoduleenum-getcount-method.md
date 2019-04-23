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
ms.openlocfilehash: d246acbf314a83ca3f8113e9a2fb223ac0ebcafe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223701"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="2a8d2-102">ICorProfilerModuleEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="2a8d2-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="2a8d2-103">获取已加载到应用程序的托管模块数。</span><span class="sxs-lookup"><span data-stu-id="2a8d2-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a8d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a8d2-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a8d2-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a8d2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2a8d2-106">[out]集合中的运行时模块数。</span><span class="sxs-lookup"><span data-stu-id="2a8d2-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a8d2-107">要求</span><span class="sxs-lookup"><span data-stu-id="2a8d2-107">Requirements</span></span>  
 <span data-ttu-id="2a8d2-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a8d2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a8d2-109">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a8d2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a8d2-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a8d2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a8d2-111">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a8d2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a8d2-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a8d2-112">See also</span></span>

- [<span data-ttu-id="2a8d2-113">ICorProfilerModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="2a8d2-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="2a8d2-114">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="2a8d2-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
