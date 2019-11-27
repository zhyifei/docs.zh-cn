---
title: ICorProfilerFunctionEnum::GetCount 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
ms.openlocfilehash: 5ccd90e92e83d7f9f6f19a082fb84dc1f1c35f4c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447817"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="ff4c2-102">ICorProfilerFunctionEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="ff4c2-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="ff4c2-103">获取应用程序加载的函数数量或探查器强制加载的函数数量。</span><span class="sxs-lookup"><span data-stu-id="ff4c2-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff4c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff4c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff4c2-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff4c2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ff4c2-106">弄已加载的函数的数目。</span><span class="sxs-lookup"><span data-stu-id="ff4c2-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff4c2-107">要求</span><span class="sxs-lookup"><span data-stu-id="ff4c2-107">Requirements</span></span>  
 <span data-ttu-id="ff4c2-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff4c2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff4c2-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff4c2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff4c2-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff4c2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff4c2-111">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff4c2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4c2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff4c2-112">See also</span></span>

- [<span data-ttu-id="ff4c2-113">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="ff4c2-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="ff4c2-114">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="ff4c2-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
