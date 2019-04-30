---
title: ICorProfilerInfo3::GetRuntimeInformation 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a13e3e525c7f019e7dc49111b88ac374345830af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000592"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="904a9-102">ICorProfilerInfo3::GetRuntimeInformation 方法</span><span class="sxs-lookup"><span data-stu-id="904a9-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="904a9-103">提供有关所分析公共语言运行时 (CLR) 的版本信息。</span><span class="sxs-lookup"><span data-stu-id="904a9-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="904a9-104">语法</span><span class="sxs-lookup"><span data-stu-id="904a9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="904a9-105">参数</span><span class="sxs-lookup"><span data-stu-id="904a9-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="904a9-106">[out]在进程中正在运行的 CLR 实例代表 ID。</span><span class="sxs-lookup"><span data-stu-id="904a9-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="904a9-107">这是与相同`ClrInstanceID`Windows (ETW) 启动事件的事件跟踪报告。</span><span class="sxs-lookup"><span data-stu-id="904a9-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="904a9-108">[out]运行时类型中。</span><span class="sxs-lookup"><span data-stu-id="904a9-108">[out] The runtime type.</span></span> <span data-ttu-id="904a9-109">此参数返回`COR_PRF_DESKTOP_CLR`桌面版本的 CLR，或`COR_PRF_CORE_CLR`CLR 在 Silverlight 中使用的 core 版本。</span><span class="sxs-lookup"><span data-stu-id="904a9-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="904a9-110">[out]CLR 主版本号。</span><span class="sxs-lookup"><span data-stu-id="904a9-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="904a9-111">[out]CLR 次版本号。</span><span class="sxs-lookup"><span data-stu-id="904a9-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="904a9-112">[out]CLR 内部版本号。</span><span class="sxs-lookup"><span data-stu-id="904a9-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="904a9-113">[out]与软件更新关联的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="904a9-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="904a9-114">[in]长度，以字符为单位的缓冲区的`szVersionString`指向。</span><span class="sxs-lookup"><span data-stu-id="904a9-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="904a9-115">[out]长度，以字符为单位的`szVersionString`。</span><span class="sxs-lookup"><span data-stu-id="904a9-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="904a9-116">[out]CLR 版本字符串。</span><span class="sxs-lookup"><span data-stu-id="904a9-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="904a9-117">备注</span><span class="sxs-lookup"><span data-stu-id="904a9-117">Remarks</span></span>  
 <span data-ttu-id="904a9-118">可以传入任何参数为 null。</span><span class="sxs-lookup"><span data-stu-id="904a9-118">You may pass null for any parameter.</span></span> <span data-ttu-id="904a9-119">但是，`pcchVersionString`不能为 null 除非`szVersionString`也为 null。</span><span class="sxs-lookup"><span data-stu-id="904a9-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="904a9-120">要求</span><span class="sxs-lookup"><span data-stu-id="904a9-120">Requirements</span></span>  
 <span data-ttu-id="904a9-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="904a9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="904a9-122">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="904a9-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="904a9-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="904a9-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="904a9-124">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="904a9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="904a9-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="904a9-125">See also</span></span>

- [<span data-ttu-id="904a9-126">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="904a9-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="904a9-127">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="904a9-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="904a9-128">分析</span><span class="sxs-lookup"><span data-stu-id="904a9-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
