---
title: "ISymUnmanagedMethod::GetSequencePoints 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetSequencePoints
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3cde9de634534acdeafa40bd7a94c46624e49604
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="fde3b-102">ISymUnmanagedMethod::GetSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="fde3b-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="fde3b-103">获取在此方法内的所有序列点。</span><span class="sxs-lookup"><span data-stu-id="fde3b-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fde3b-104">语法</span><span class="sxs-lookup"><span data-stu-id="fde3b-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fde3b-105">参数</span><span class="sxs-lookup"><span data-stu-id="fde3b-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="fde3b-106">[in]A`ULONG32`接收的大小`offsets`， `documents`， `lines`， `columns`， `endLines`，和`endColumns`数组。</span><span class="sxs-lookup"><span data-stu-id="fde3b-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="fde3b-107">[out]指向的指针`ULONG32`接收包含序列点所需的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="fde3b-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="fde3b-108">[in]要在其中存储 Microsoft 中间语言 (MSIL) 偏移量从开始处的序列点的方法数组。</span><span class="sxs-lookup"><span data-stu-id="fde3b-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="fde3b-109">[in]在其中存储序列点所在的文档的数组。</span><span class="sxs-lookup"><span data-stu-id="fde3b-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="fde3b-110">[in]在其中存储序列点所在的文档中的行的数组。</span><span class="sxs-lookup"><span data-stu-id="fde3b-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="fde3b-111">[in]在其中存储序列点所在的文档中的列的数组。</span><span class="sxs-lookup"><span data-stu-id="fde3b-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="fde3b-112">[in]序列点结束的文档中的行的数组。</span><span class="sxs-lookup"><span data-stu-id="fde3b-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="fde3b-113">[in]序列点结束的文档中的列的数组。</span><span class="sxs-lookup"><span data-stu-id="fde3b-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fde3b-114">返回值</span><span class="sxs-lookup"><span data-stu-id="fde3b-114">Return Value</span></span>  
 <span data-ttu-id="fde3b-115">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="fde3b-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde3b-116">要求</span><span class="sxs-lookup"><span data-stu-id="fde3b-116">Requirements</span></span>  
 <span data-ttu-id="fde3b-117">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fde3b-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde3b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fde3b-118">See Also</span></span>  
 [<span data-ttu-id="fde3b-119">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="fde3b-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
