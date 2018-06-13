---
title: ICorProfilerInfo2::GetStringLayout 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d1bd732a82028afe809f4c2141e1d61668eae1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454911"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="e6975-102">ICorProfilerInfo2::GetStringLayout 方法</span><span class="sxs-lookup"><span data-stu-id="e6975-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="e6975-103">获取有关字符串对象布局的信息。</span><span class="sxs-lookup"><span data-stu-id="e6975-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="e6975-104">此方法已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]，并且由取代[icorprofilerinfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e6975-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6975-105">语法</span><span class="sxs-lookup"><span data-stu-id="e6975-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6975-106">参数</span><span class="sxs-lookup"><span data-stu-id="e6975-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="e6975-107">[out]指向的位置，相对于的偏移量的指针`ObjectID`指针，用于存储字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="e6975-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="e6975-108">作为存储长度`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="e6975-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6975-109">此参数返回的字符串本身，而不缓冲区的长度的长度。</span><span class="sxs-lookup"><span data-stu-id="e6975-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="e6975-110">缓冲区的长度不再可用。</span><span class="sxs-lookup"><span data-stu-id="e6975-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="e6975-111">[out]指向的位置，相对于的偏移量的指针`ObjectID`指针，用于存储本身的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="e6975-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="e6975-112">作为存储长度`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="e6975-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="e6975-113">[out]指向的缓冲区，相对于的偏移量的指针`ObjectID`指针，存储的宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="e6975-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6975-114">备注</span><span class="sxs-lookup"><span data-stu-id="e6975-114">Remarks</span></span>  
 <span data-ttu-id="e6975-115">`GetStringLayout`方法获取相对于偏移量，`ObjectID`指针，以下存储所在的位置：</span><span class="sxs-lookup"><span data-stu-id="e6975-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="e6975-116">字符串的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="e6975-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="e6975-117">字符串本身的长度。</span><span class="sxs-lookup"><span data-stu-id="e6975-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="e6975-118">包含实际的宽字符字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e6975-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="e6975-119">字符串可能是以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="e6975-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6975-120">要求</span><span class="sxs-lookup"><span data-stu-id="e6975-120">Requirements</span></span>  
 <span data-ttu-id="e6975-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6975-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6975-122">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6975-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6975-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6975-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6975-124">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6975-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6975-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6975-125">See Also</span></span>  
 [<span data-ttu-id="e6975-126">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="e6975-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="e6975-127">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="e6975-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
