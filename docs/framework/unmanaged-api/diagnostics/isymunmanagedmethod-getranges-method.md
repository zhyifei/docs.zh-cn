---
title: ISymUnmanagedMethod::GetRanges 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ca1db2bf85f42117f686a8cb483907003927c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939589"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="b35bc-102">ISymUnmanagedMethod::GetRanges 方法</span><span class="sxs-lookup"><span data-stu-id="b35bc-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="b35bc-103">给定文档中的一个位置，返回到 Microsoft 中间语言 (MSIL) 的位置在此方法内包括的范围对应的开始和结束偏移量对的数组。</span><span class="sxs-lookup"><span data-stu-id="b35bc-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="b35bc-104">数组是一个整数数组，具有 [开始、 结束、 开始和结束] 的格式。</span><span class="sxs-lookup"><span data-stu-id="b35bc-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="b35bc-105">区域对的数目是数组除以 2 的长度。</span><span class="sxs-lookup"><span data-stu-id="b35bc-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b35bc-106">语法</span><span class="sxs-lookup"><span data-stu-id="b35bc-106">Syntax</span></span>  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b35bc-107">参数</span><span class="sxs-lookup"><span data-stu-id="b35bc-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="b35bc-108">[in]为其请求偏移量的文档。</span><span class="sxs-lookup"><span data-stu-id="b35bc-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="b35bc-109">[in]与范围对应的文档行。</span><span class="sxs-lookup"><span data-stu-id="b35bc-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="b35bc-110">[in]与范围对应的文档列。</span><span class="sxs-lookup"><span data-stu-id="b35bc-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="b35bc-111">[in] `ranges` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="b35bc-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="b35bc-112">[out]一个指向`ULONG32`接收包含多个范围所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="b35bc-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="b35bc-113">[out]指向接收范围的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="b35bc-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b35bc-114">返回值</span><span class="sxs-lookup"><span data-stu-id="b35bc-114">Return Value</span></span>  
 <span data-ttu-id="b35bc-115">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="b35bc-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b35bc-116">要求</span><span class="sxs-lookup"><span data-stu-id="b35bc-116">Requirements</span></span>  
 <span data-ttu-id="b35bc-117">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b35bc-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35bc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b35bc-118">See also</span></span>

- [<span data-ttu-id="b35bc-119">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="b35bc-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
