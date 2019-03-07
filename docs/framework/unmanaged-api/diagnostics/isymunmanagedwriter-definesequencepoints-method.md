---
title: ISymUnmanagedWriter::DefineSequencePoints 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4210dedd77c6ab041189fa287e192bb7038080b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491397"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="c28e6-102">ISymUnmanagedWriter::DefineSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="c28e6-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="c28e6-103">在当前方法内定义一组序列点。</span><span class="sxs-lookup"><span data-stu-id="c28e6-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="c28e6-104">每个起始行和起始列定义一种方法中的语句的开始。</span><span class="sxs-lookup"><span data-stu-id="c28e6-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="c28e6-105">每个结束行和结束列定义一种方法中的语句的结束。</span><span class="sxs-lookup"><span data-stu-id="c28e6-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="c28e6-106">数组应以偏移量的升序进行排序。</span><span class="sxs-lookup"><span data-stu-id="c28e6-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="c28e6-107">偏移量始终是从开始处的方法，以字节为单位度量的。</span><span class="sxs-lookup"><span data-stu-id="c28e6-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c28e6-108">语法</span><span class="sxs-lookup"><span data-stu-id="c28e6-108">Syntax</span></span>  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c28e6-109">参数</span><span class="sxs-lookup"><span data-stu-id="c28e6-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="c28e6-110">[in]要为其定义序列点的文档对象。</span><span class="sxs-lookup"><span data-stu-id="c28e6-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="c28e6-111">[in]一个`ULONG32`，该值指示每个的大小`offsets`， `lines`， `columns`， `endLines`，并`endColumns`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c28e6-111">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="c28e6-112">[in]从方法开始测量的序列点的偏移量。</span><span class="sxs-lookup"><span data-stu-id="c28e6-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="c28e6-113">[in]序列点的起始行号。</span><span class="sxs-lookup"><span data-stu-id="c28e6-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="c28e6-114">[in]序列点的起始列号。</span><span class="sxs-lookup"><span data-stu-id="c28e6-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="c28e6-115">[in]序列点的结束行号。</span><span class="sxs-lookup"><span data-stu-id="c28e6-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="c28e6-116">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="c28e6-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="c28e6-117">[in]序列点的结束列号。</span><span class="sxs-lookup"><span data-stu-id="c28e6-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="c28e6-118">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="c28e6-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c28e6-119">返回值</span><span class="sxs-lookup"><span data-stu-id="c28e6-119">Return Value</span></span>  
 <span data-ttu-id="c28e6-120">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c28e6-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c28e6-121">要求</span><span class="sxs-lookup"><span data-stu-id="c28e6-121">Requirements</span></span>  
 <span data-ttu-id="c28e6-122">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c28e6-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c28e6-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c28e6-123">See also</span></span>
- [<span data-ttu-id="c28e6-124">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="c28e6-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
