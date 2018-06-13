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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fba01c1dfdea83b2580f45b7dbcef91fb7b73fb2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452899"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="87995-102">ICorProfilerInfo::GetFunctionFromIP 方法</span><span class="sxs-lookup"><span data-stu-id="87995-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="87995-103">映射到托管的代码指令指针`FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="87995-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87995-104">语法</span><span class="sxs-lookup"><span data-stu-id="87995-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87995-105">参数</span><span class="sxs-lookup"><span data-stu-id="87995-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="87995-106">[in]托管代码中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="87995-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="87995-107">[out]返回的函数 id。</span><span class="sxs-lookup"><span data-stu-id="87995-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87995-108">要求</span><span class="sxs-lookup"><span data-stu-id="87995-108">Requirements</span></span>  
 <span data-ttu-id="87995-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87995-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87995-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87995-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87995-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87995-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87995-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87995-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87995-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="87995-113">See Also</span></span>  
 [<span data-ttu-id="87995-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="87995-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
