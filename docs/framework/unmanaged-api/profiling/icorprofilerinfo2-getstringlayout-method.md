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
ms.openlocfilehash: faa5ecf63ac3795a58369d94f9fb15f853edb576
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490710"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="b2682-102">ICorProfilerInfo2::GetStringLayout 方法</span><span class="sxs-lookup"><span data-stu-id="b2682-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="b2682-103">获取有关字符串对象布局的信息。</span><span class="sxs-lookup"><span data-stu-id="b2682-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="b2682-104">此方法在.NET Framework 4 中，已弃用，并且已被取代[ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b2682-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2682-105">语法</span><span class="sxs-lookup"><span data-stu-id="b2682-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2682-106">参数</span><span class="sxs-lookup"><span data-stu-id="b2682-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="b2682-107">[out]指向的位置，相对于的偏移量的`ObjectID`指针，用于存储字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="b2682-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="b2682-108">长度存储为`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="b2682-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2682-109">此参数将返回字符串本身，而不是缓冲区的长度的长度。</span><span class="sxs-lookup"><span data-stu-id="b2682-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="b2682-110">缓冲区的长度不再可用。</span><span class="sxs-lookup"><span data-stu-id="b2682-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="b2682-111">[out]指向的位置，相对于的偏移量的`ObjectID`指针，用于存储字符串本身的长度。</span><span class="sxs-lookup"><span data-stu-id="b2682-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="b2682-112">长度存储为`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="b2682-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="b2682-113">[out]指向缓冲区，相对于的偏移量的`ObjectID`指针，存储的宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="b2682-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2682-114">备注</span><span class="sxs-lookup"><span data-stu-id="b2682-114">Remarks</span></span>  
 <span data-ttu-id="b2682-115">`GetStringLayout`方法获取偏移量，相对于`ObjectID`指针，以下在其中存储的位置：</span><span class="sxs-lookup"><span data-stu-id="b2682-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="b2682-116">字符串的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="b2682-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="b2682-117">该字符串本身的长度。</span><span class="sxs-lookup"><span data-stu-id="b2682-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="b2682-118">包含实际的宽字符字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b2682-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="b2682-119">字符串可以是以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="b2682-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2682-120">要求</span><span class="sxs-lookup"><span data-stu-id="b2682-120">Requirements</span></span>  
 <span data-ttu-id="b2682-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2682-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2682-122">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2682-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2682-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2682-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2682-124">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2682-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2682-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2682-125">See also</span></span>

- [<span data-ttu-id="b2682-126">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="b2682-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="b2682-127">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="b2682-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
