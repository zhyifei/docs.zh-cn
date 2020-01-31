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
ms.openlocfilehash: cd1f3982fe1439135bf96579370a5a798c61dd2e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863772"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="b803d-102">ICorProfilerInfo::GetFunctionFromIP 方法</span><span class="sxs-lookup"><span data-stu-id="b803d-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="b803d-103">将托管代码指令指针映射到 `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="b803d-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b803d-104">语法</span><span class="sxs-lookup"><span data-stu-id="b803d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b803d-105">参数</span><span class="sxs-lookup"><span data-stu-id="b803d-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="b803d-106">\[中的] 托管代码中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="b803d-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="b803d-107">\[out] 返回的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="b803d-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="b803d-108">需求</span><span class="sxs-lookup"><span data-stu-id="b803d-108">Requirements</span></span>  
 <span data-ttu-id="b803d-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b803d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b803d-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b803d-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b803d-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b803d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b803d-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b803d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b803d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b803d-113">See also</span></span>

- [<span data-ttu-id="b803d-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="b803d-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
