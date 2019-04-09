---
title: ICorProfilerThreadEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0301334621a2e393a59e7cc34f2964450a81213f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074165"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="9f02f-102">ICorProfilerThreadEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="9f02f-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="9f02f-103">此副本中获取的接口指针[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="9f02f-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f02f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f02f-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f02f-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f02f-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="9f02f-106">[out]指向指针的接口指针，用于又指向这份[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="9f02f-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="9f02f-107">枚举器的副本维护其自己的枚举状态独立于此枚举器。</span><span class="sxs-lookup"><span data-stu-id="9f02f-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="9f02f-108">但是，副本的初始光标位置是此当前光标位置的枚举器相同。</span><span class="sxs-lookup"><span data-stu-id="9f02f-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f02f-109">要求</span><span class="sxs-lookup"><span data-stu-id="9f02f-109">Requirements</span></span>  
 <span data-ttu-id="9f02f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f02f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f02f-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9f02f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9f02f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f02f-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9f02f-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="9f02f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9f02f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f02f-114">See also</span></span>

- [<span data-ttu-id="9f02f-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="9f02f-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="9f02f-116">分析接口</span><span class="sxs-lookup"><span data-stu-id="9f02f-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
