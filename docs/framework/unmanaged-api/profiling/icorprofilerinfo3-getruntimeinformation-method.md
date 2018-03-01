---
title: "ICorProfilerInfo3::GetRuntimeInformation 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5eadd9970d29cc65d8411692407dcae5471e51c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="74b2d-102">ICorProfilerInfo3::GetRuntimeInformation 方法</span><span class="sxs-lookup"><span data-stu-id="74b2d-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="74b2d-103">提供有关所分析公共语言运行时 (CLR) 的版本信息。</span><span class="sxs-lookup"><span data-stu-id="74b2d-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74b2d-104">语法</span><span class="sxs-lookup"><span data-stu-id="74b2d-104">Syntax</span></span>  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74b2d-105">参数</span><span class="sxs-lookup"><span data-stu-id="74b2d-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="74b2d-106">[out]在进程中运行 CLR 实例代表 ID。</span><span class="sxs-lookup"><span data-stu-id="74b2d-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="74b2d-107">这是与相同`ClrInstanceID`事件跟踪 Windows (ETW) 启动事件的报告。</span><span class="sxs-lookup"><span data-stu-id="74b2d-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="74b2d-108">[out]运行时类型中。</span><span class="sxs-lookup"><span data-stu-id="74b2d-108">[out] The runtime type.</span></span> <span data-ttu-id="74b2d-109">此参数返回`COR_PRF_DESKTOP_CLR`桌面版本的 CLR，或`COR_PRF_CORE_CLR`Silverlight 中所用的 CLR 的核心版本。</span><span class="sxs-lookup"><span data-stu-id="74b2d-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="74b2d-110">[out]CLR 主版本号。</span><span class="sxs-lookup"><span data-stu-id="74b2d-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="74b2d-111">[out]CLR 次版本号。</span><span class="sxs-lookup"><span data-stu-id="74b2d-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="74b2d-112">[out]CLR 内部版本号。</span><span class="sxs-lookup"><span data-stu-id="74b2d-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="74b2d-113">[out]与软件更新关联的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="74b2d-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="74b2d-114">[in]长度，以字符为单位的缓冲区，`szVersionString`指向。</span><span class="sxs-lookup"><span data-stu-id="74b2d-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="74b2d-115">[out]长度，以字符为单位的`szVersionString`。</span><span class="sxs-lookup"><span data-stu-id="74b2d-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="74b2d-116">[out]CLR 版本字符串。</span><span class="sxs-lookup"><span data-stu-id="74b2d-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74b2d-117">备注</span><span class="sxs-lookup"><span data-stu-id="74b2d-117">Remarks</span></span>  
 <span data-ttu-id="74b2d-118">你可能会传递了 null 对于任何参数。</span><span class="sxs-lookup"><span data-stu-id="74b2d-118">You may pass null for any parameter.</span></span> <span data-ttu-id="74b2d-119">但是，`pcchVersionString`不能为 null 除非`szVersionString`也为 null。</span><span class="sxs-lookup"><span data-stu-id="74b2d-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74b2d-120">惠?</span><span class="sxs-lookup"><span data-stu-id="74b2d-120">Requirements</span></span>  
 <span data-ttu-id="74b2d-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74b2d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74b2d-122">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74b2d-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74b2d-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74b2d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74b2d-124">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74b2d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74b2d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="74b2d-125">See Also</span></span>  
 [<span data-ttu-id="74b2d-126">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="74b2d-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="74b2d-127">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="74b2d-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="74b2d-128">分析</span><span class="sxs-lookup"><span data-stu-id="74b2d-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
