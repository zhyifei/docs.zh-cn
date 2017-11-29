---
title: "ISymUnmanagedReader2::GetMethodsInDocument 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetMethodsInDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 15053aeb3febd533a6977ef446fc1aa3bd8a92b8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="2bfc2-102">ISymUnmanagedReader2::GetMethodsInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="2bfc2-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="2bfc2-103">获取每个方法，提供的文档中包含行信息。</span><span class="sxs-lookup"><span data-stu-id="2bfc2-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bfc2-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bfc2-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2bfc2-105">参数</span><span class="sxs-lookup"><span data-stu-id="2bfc2-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="2bfc2-106">[in]指向文档的指针。</span><span class="sxs-lookup"><span data-stu-id="2bfc2-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="2bfc2-107">[in]A `ULONG32` ，该值指示的大小`pRetVal`数组。</span><span class="sxs-lookup"><span data-stu-id="2bfc2-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="2bfc2-108">[out]指向的指针`ULONG32`接收包含方法所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="2bfc2-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2bfc2-109">[out]指向接收方法的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="2bfc2-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bfc2-110">返回值</span><span class="sxs-lookup"><span data-stu-id="2bfc2-110">Return Value</span></span>  
 <span data-ttu-id="2bfc2-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="2bfc2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bfc2-112">要求</span><span class="sxs-lookup"><span data-stu-id="2bfc2-112">Requirements</span></span>  
 <span data-ttu-id="2bfc2-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2bfc2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bfc2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bfc2-114">See Also</span></span>  
 [<span data-ttu-id="2bfc2-115">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="2bfc2-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
