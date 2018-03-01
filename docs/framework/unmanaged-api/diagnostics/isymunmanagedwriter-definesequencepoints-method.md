---
title: "ISymUnmanagedWriter::DefineSequencePoints 方法"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e1dcc427a6d034ce108ca66f71cc24b1050a72f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="98728-102">ISymUnmanagedWriter::DefineSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="98728-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="98728-103">在当前方法内定义一组序列点。</span><span class="sxs-lookup"><span data-stu-id="98728-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="98728-104">每个起始行和起始列定义方法中的语句的开始。</span><span class="sxs-lookup"><span data-stu-id="98728-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="98728-105">每个结束行和结束列定义的方法内语句的末尾。</span><span class="sxs-lookup"><span data-stu-id="98728-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="98728-106">数组应按偏移量的升序排序。</span><span class="sxs-lookup"><span data-stu-id="98728-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="98728-107">位移始终被指从开始处的方法，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="98728-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98728-108">语法</span><span class="sxs-lookup"><span data-stu-id="98728-108">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="98728-109">参数</span><span class="sxs-lookup"><span data-stu-id="98728-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="98728-110">[in]正在为其定义的序列点文档对象。</span><span class="sxs-lookup"><span data-stu-id="98728-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="98728-111">[in]A `ULONG32` ，指示每个大小`offsets`， `lines`， `columns`， `endLines`，和`endColumns`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="98728-111">[in] A `ULONG32` that that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="98728-112">[in]从方法的开头算起的序列点的偏移量。</span><span class="sxs-lookup"><span data-stu-id="98728-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="98728-113">[in]序列点的起始行号。</span><span class="sxs-lookup"><span data-stu-id="98728-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="98728-114">[in]序列点的起始列号。</span><span class="sxs-lookup"><span data-stu-id="98728-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="98728-115">[in]序列点的结束行号。</span><span class="sxs-lookup"><span data-stu-id="98728-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="98728-116">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="98728-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="98728-117">[in]序列点的结束列号。</span><span class="sxs-lookup"><span data-stu-id="98728-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="98728-118">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="98728-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98728-119">返回值</span><span class="sxs-lookup"><span data-stu-id="98728-119">Return Value</span></span>  
 <span data-ttu-id="98728-120">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="98728-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98728-121">惠?</span><span class="sxs-lookup"><span data-stu-id="98728-121">Requirements</span></span>  
 <span data-ttu-id="98728-122">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="98728-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98728-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="98728-123">See Also</span></span>  
 [<span data-ttu-id="98728-124">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="98728-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
