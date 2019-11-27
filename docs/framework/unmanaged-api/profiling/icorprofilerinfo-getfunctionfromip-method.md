---
title: ICorProfilerInfo::GetFunctionFromIP 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
ms.openlocfilehash: 14b152474cd71dc3ff7b59c94b6ec4fa0cd7ce0c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439209"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="572a2-102">ICorProfilerInfo::GetFunctionFromIP 方法</span><span class="sxs-lookup"><span data-stu-id="572a2-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="572a2-103">将托管代码指令指针映射到 `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="572a2-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="572a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="572a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="572a2-105">参数</span><span class="sxs-lookup"><span data-stu-id="572a2-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="572a2-106">中托管代码中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="572a2-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="572a2-107">弄返回的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="572a2-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="572a2-108">要求</span><span class="sxs-lookup"><span data-stu-id="572a2-108">Requirements</span></span>  
 <span data-ttu-id="572a2-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="572a2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="572a2-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="572a2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="572a2-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="572a2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="572a2-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="572a2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572a2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="572a2-113">See also</span></span>

- [<span data-ttu-id="572a2-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="572a2-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
