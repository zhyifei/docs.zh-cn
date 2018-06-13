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
ms.openlocfilehash: 84a71ac3a1ba30e20bb6ec7e6a0e31db9d3b5738
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455701"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="655e2-102">ICorProfilerThreadEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="655e2-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="655e2-103">获取对此副本的接口指针[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="655e2-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="655e2-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="655e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="655e2-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="655e2-106">[out]指向指针的接口指针，用于，反过来，指向这份[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="655e2-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="655e2-107">枚举器的副本将保持独立于此枚举器自己枚举状态。</span><span class="sxs-lookup"><span data-stu-id="655e2-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="655e2-108">但是，初始光标位置的复制操作的枚举数此当前光标位置相同。</span><span class="sxs-lookup"><span data-stu-id="655e2-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="655e2-109">要求</span><span class="sxs-lookup"><span data-stu-id="655e2-109">Requirements</span></span>  
 <span data-ttu-id="655e2-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="655e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="655e2-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="655e2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="655e2-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="655e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="655e2-113">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="655e2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655e2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="655e2-114">See Also</span></span>  
 [<span data-ttu-id="655e2-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="655e2-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="655e2-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="655e2-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
