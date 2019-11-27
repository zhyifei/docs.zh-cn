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
ms.openlocfilehash: 1e3dc4735af68da7f76fc6fce84d2dd4ac3f576e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449664"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="843b7-102">ICorProfilerInfo3::GetStringLayout2 方法</span><span class="sxs-lookup"><span data-stu-id="843b7-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="843b7-103">获取有关字符串对象布局的信息。</span><span class="sxs-lookup"><span data-stu-id="843b7-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="843b7-104">此方法取代了[ICorProfilerInfo2：： GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="843b7-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="843b7-105">语法</span><span class="sxs-lookup"><span data-stu-id="843b7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="843b7-106">参数</span><span class="sxs-lookup"><span data-stu-id="843b7-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="843b7-107">弄一个指针，它指向存储字符串本身的长度的位置相对于 `ObjectID` 指针的偏移量。</span><span class="sxs-lookup"><span data-stu-id="843b7-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="843b7-108">长度作为 `DWORD`存储。</span><span class="sxs-lookup"><span data-stu-id="843b7-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="843b7-109">弄指向缓冲区偏移量的指针，该指针相对于存储宽字符字符串的 `ObjectID` 指针。</span><span class="sxs-lookup"><span data-stu-id="843b7-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="843b7-110">备注</span><span class="sxs-lookup"><span data-stu-id="843b7-110">Remarks</span></span>  
 <span data-ttu-id="843b7-111">字符串可以是，也可以不是以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="843b7-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="843b7-112">要求</span><span class="sxs-lookup"><span data-stu-id="843b7-112">Requirements</span></span>  
 <span data-ttu-id="843b7-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="843b7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="843b7-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="843b7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="843b7-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="843b7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="843b7-116">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="843b7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="843b7-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="843b7-117">See also</span></span>

- [<span data-ttu-id="843b7-118">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="843b7-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="843b7-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="843b7-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
