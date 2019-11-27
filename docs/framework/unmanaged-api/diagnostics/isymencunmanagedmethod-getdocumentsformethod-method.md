---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 49023424c21fced1c49b16ecdbea93c654b5e883
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448387"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="0dd88-102">ISymENCUnmanagedMethod::GetDocumentsForMethod 方法</span><span class="sxs-lookup"><span data-stu-id="0dd88-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="0dd88-103">获取此方法在中具有线条的文档。</span><span class="sxs-lookup"><span data-stu-id="0dd88-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd88-104">语法</span><span class="sxs-lookup"><span data-stu-id="0dd88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dd88-105">参数</span><span class="sxs-lookup"><span data-stu-id="0dd88-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="0dd88-106">中`pcDocs`所指向的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="0dd88-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="0dd88-107">弄指向 `ULONG32` 的指针，该指针接收包含文档所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="0dd88-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="0dd88-108">中包含文档的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0dd88-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0dd88-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0dd88-109">Return Value</span></span>  
 <span data-ttu-id="0dd88-110">如果该方法成功，则 S_OK;否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="0dd88-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dd88-111">要求</span><span class="sxs-lookup"><span data-stu-id="0dd88-111">Requirements</span></span>  
 <span data-ttu-id="0dd88-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="0dd88-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd88-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0dd88-113">See also</span></span>

- [<span data-ttu-id="0dd88-114">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="0dd88-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
