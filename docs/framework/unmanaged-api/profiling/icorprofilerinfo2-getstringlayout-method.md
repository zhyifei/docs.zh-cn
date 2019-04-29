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
ms.openlocfilehash: cc94c63edb602d87a7c08a9051eb2ef760834477
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791637"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="5b710-102">ICorProfilerInfo2::GetStringLayout 方法</span><span class="sxs-lookup"><span data-stu-id="5b710-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="5b710-103">获取有关字符串对象布局的信息。</span><span class="sxs-lookup"><span data-stu-id="5b710-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="5b710-104">此方法中已弃用[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]，并且被取代[ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5b710-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b710-105">语法</span><span class="sxs-lookup"><span data-stu-id="5b710-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b710-106">参数</span><span class="sxs-lookup"><span data-stu-id="5b710-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="5b710-107">[out]指向的位置，相对于的偏移量的`ObjectID`指针，用于存储字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="5b710-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="5b710-108">长度存储为`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="5b710-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b710-109">此参数将返回字符串本身，而不是缓冲区的长度的长度。</span><span class="sxs-lookup"><span data-stu-id="5b710-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="5b710-110">缓冲区的长度不再可用。</span><span class="sxs-lookup"><span data-stu-id="5b710-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="5b710-111">[out]指向的位置，相对于的偏移量的`ObjectID`指针，用于存储字符串本身的长度。</span><span class="sxs-lookup"><span data-stu-id="5b710-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="5b710-112">长度存储为`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="5b710-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="5b710-113">[out]指向缓冲区，相对于的偏移量的`ObjectID`指针，存储的宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="5b710-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b710-114">备注</span><span class="sxs-lookup"><span data-stu-id="5b710-114">Remarks</span></span>  
 <span data-ttu-id="5b710-115">`GetStringLayout`方法获取偏移量，相对于`ObjectID`指针，以下在其中存储的位置：</span><span class="sxs-lookup"><span data-stu-id="5b710-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="5b710-116">字符串的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="5b710-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="5b710-117">该字符串本身的长度。</span><span class="sxs-lookup"><span data-stu-id="5b710-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="5b710-118">包含实际的宽字符字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5b710-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="5b710-119">字符串可以是以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="5b710-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b710-120">要求</span><span class="sxs-lookup"><span data-stu-id="5b710-120">Requirements</span></span>  
 <span data-ttu-id="5b710-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b710-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b710-122">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b710-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b710-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b710-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b710-124">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b710-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b710-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b710-125">See also</span></span>

- [<span data-ttu-id="5b710-126">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="5b710-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="5b710-127">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="5b710-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
