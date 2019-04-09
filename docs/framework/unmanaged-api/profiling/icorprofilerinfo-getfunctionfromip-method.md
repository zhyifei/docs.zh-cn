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
ms.openlocfilehash: 23fb9c58f2eac904b63294434654f3caf1ba9f41
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107960"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="e3e85-102">ICorProfilerInfo::GetFunctionFromIP 方法</span><span class="sxs-lookup"><span data-stu-id="e3e85-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="e3e85-103">映射到的托管的代码指令指针`FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="e3e85-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3e85-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3e85-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3e85-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3e85-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="e3e85-106">[in]托管代码中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="e3e85-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="e3e85-107">[out]返回的函数 id。</span><span class="sxs-lookup"><span data-stu-id="e3e85-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3e85-108">要求</span><span class="sxs-lookup"><span data-stu-id="e3e85-108">Requirements</span></span>  
 <span data-ttu-id="e3e85-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3e85-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3e85-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3e85-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3e85-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3e85-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e3e85-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="e3e85-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3e85-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3e85-113">See also</span></span>

- [<span data-ttu-id="e3e85-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="e3e85-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
