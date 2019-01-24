---
title: ICorProfilerInfo3::GetStringLayout2 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ca40a0a172563368f971a83035c5dead66c70a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552003"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="d943e-102">ICorProfilerInfo3::GetStringLayout2 方法</span><span class="sxs-lookup"><span data-stu-id="d943e-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="d943e-103">获取有关字符串对象布局的信息。</span><span class="sxs-lookup"><span data-stu-id="d943e-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="d943e-104">此方法取代[ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d943e-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d943e-105">语法</span><span class="sxs-lookup"><span data-stu-id="d943e-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d943e-106">参数</span><span class="sxs-lookup"><span data-stu-id="d943e-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="d943e-107">[out]指向的位置，相对于的偏移量的`ObjectID`指针，用于存储字符串本身的长度。</span><span class="sxs-lookup"><span data-stu-id="d943e-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="d943e-108">长度存储为`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="d943e-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="d943e-109">[out]指向缓冲区，相对于的偏移量的`ObjectID`指针，它将存储的宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="d943e-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d943e-110">备注</span><span class="sxs-lookup"><span data-stu-id="d943e-110">Remarks</span></span>  
 <span data-ttu-id="d943e-111">可能或可能不是以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="d943e-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d943e-112">要求</span><span class="sxs-lookup"><span data-stu-id="d943e-112">Requirements</span></span>  
 <span data-ttu-id="d943e-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d943e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d943e-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d943e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d943e-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d943e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d943e-116">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d943e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d943e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d943e-117">See also</span></span>
- [<span data-ttu-id="d943e-118">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="d943e-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="d943e-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="d943e-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
