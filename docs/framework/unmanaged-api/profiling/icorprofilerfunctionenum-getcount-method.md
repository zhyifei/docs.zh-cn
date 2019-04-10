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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5061750489c74e0385f2ce020c88518604b3167
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169281"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="5ab85-102">ICorProfilerFunctionEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="5ab85-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="5ab85-103">获取应用程序加载的函数数量或探查器强制加载的函数数量。</span><span class="sxs-lookup"><span data-stu-id="5ab85-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab85-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ab85-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab85-105">参数</span><span class="sxs-lookup"><span data-stu-id="5ab85-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5ab85-106">[out]已加载的函数的数目。</span><span class="sxs-lookup"><span data-stu-id="5ab85-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab85-107">要求</span><span class="sxs-lookup"><span data-stu-id="5ab85-107">Requirements</span></span>  
 <span data-ttu-id="5ab85-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5ab85-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ab85-109">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ab85-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ab85-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ab85-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5ab85-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5ab85-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5ab85-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ab85-112">See also</span></span>

- [<span data-ttu-id="5ab85-113">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="5ab85-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="5ab85-114">分析接口</span><span class="sxs-lookup"><span data-stu-id="5ab85-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
