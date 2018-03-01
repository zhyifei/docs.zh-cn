---
title: "ICorProfilerInfo3::GetStringLayout2 方法"
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
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 97f4ab9eefa8bf1f2b3a5057f24b6a940ba91f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="023da-102">ICorProfilerInfo3::GetStringLayout2 方法</span><span class="sxs-lookup"><span data-stu-id="023da-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="023da-103">获取有关字符串对象布局的信息。</span><span class="sxs-lookup"><span data-stu-id="023da-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="023da-104">此方法取代[icorprofilerinfo2:: Getstringlayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="023da-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="023da-105">语法</span><span class="sxs-lookup"><span data-stu-id="023da-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="023da-106">参数</span><span class="sxs-lookup"><span data-stu-id="023da-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="023da-107">[out]指向的位置，相对于的偏移量的指针`ObjectID`指针，用于存储本身的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="023da-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="023da-108">作为存储长度`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="023da-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="023da-109">[out]指向的缓冲区，相对于的偏移量的指针`ObjectID`指针，它存储的宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="023da-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="023da-110">备注</span><span class="sxs-lookup"><span data-stu-id="023da-110">Remarks</span></span>  
 <span data-ttu-id="023da-111">可能或可能不是以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="023da-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="023da-112">惠?</span><span class="sxs-lookup"><span data-stu-id="023da-112">Requirements</span></span>  
 <span data-ttu-id="023da-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="023da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="023da-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="023da-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="023da-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="023da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="023da-116">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="023da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023da-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="023da-117">See Also</span></span>  
 [<span data-ttu-id="023da-118">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="023da-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="023da-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="023da-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
