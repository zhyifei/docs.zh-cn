---
title: ISymUnmanagedMethod::GetSequencePoints 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6b1e253fb7bf1a97f44e1eb05676fc356af9837
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939537"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="12bd7-102">ISymUnmanagedMethod::GetSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="12bd7-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="12bd7-103">获取在此方法内的所有序列点。</span><span class="sxs-lookup"><span data-stu-id="12bd7-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12bd7-104">语法</span><span class="sxs-lookup"><span data-stu-id="12bd7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="12bd7-105">参数</span><span class="sxs-lookup"><span data-stu-id="12bd7-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="12bd7-106">[in]一个`ULONG32`，它接收的大小`offsets`， `documents`， `lines`， `columns`， `endLines`，和`endColumns`数组。</span><span class="sxs-lookup"><span data-stu-id="12bd7-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="12bd7-107">[out]一个指向`ULONG32`接收包含序列点所需的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="12bd7-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="12bd7-108">[in]一个数组，要在其中存储 Microsoft 中间语言 (MSIL) 偏移量从序列点方法的开头。</span><span class="sxs-lookup"><span data-stu-id="12bd7-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="12bd7-109">[in]要在其中存储序列点所在的文档数组。</span><span class="sxs-lookup"><span data-stu-id="12bd7-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="12bd7-110">[in]在其中存储序列点所在的文档中的行的数组。</span><span class="sxs-lookup"><span data-stu-id="12bd7-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="12bd7-111">[in]在其中存储序列点所在的文档中的列的数组。</span><span class="sxs-lookup"><span data-stu-id="12bd7-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="12bd7-112">[in]序列点结束的文档中的行的数组。</span><span class="sxs-lookup"><span data-stu-id="12bd7-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="12bd7-113">[in]序列点结束的文档中的列的数组。</span><span class="sxs-lookup"><span data-stu-id="12bd7-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12bd7-114">返回值</span><span class="sxs-lookup"><span data-stu-id="12bd7-114">Return Value</span></span>  
 <span data-ttu-id="12bd7-115">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="12bd7-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12bd7-116">要求</span><span class="sxs-lookup"><span data-stu-id="12bd7-116">Requirements</span></span>  
 <span data-ttu-id="12bd7-117">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="12bd7-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12bd7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="12bd7-118">See also</span></span>

- [<span data-ttu-id="12bd7-119">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="12bd7-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
