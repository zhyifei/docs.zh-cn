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
ms.openlocfilehash: 89be772ee3d8a6fc5acb74d5ebe6d3c691764f89
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441950"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="511d9-102">ISymENCUnmanagedMethod::GetDocumentsForMethod 方法</span><span class="sxs-lookup"><span data-stu-id="511d9-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="511d9-103">获取此方法在中具有线条的文档。</span><span class="sxs-lookup"><span data-stu-id="511d9-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="511d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="511d9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="511d9-105">参数</span><span class="sxs-lookup"><span data-stu-id="511d9-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="511d9-106">中所指向的缓冲区的长度 `pcDocs` 。</span><span class="sxs-lookup"><span data-stu-id="511d9-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="511d9-107">弄指向的指针， `ULONG32` 该指针接收包含文档所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="511d9-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="511d9-108">中包含文档的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="511d9-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="511d9-109">返回值</span><span class="sxs-lookup"><span data-stu-id="511d9-109">Return Value</span></span>  
 <span data-ttu-id="511d9-110">如果该方法成功，则 S_OK;否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="511d9-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="511d9-111">要求</span><span class="sxs-lookup"><span data-stu-id="511d9-111">Requirements</span></span>  
 <span data-ttu-id="511d9-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="511d9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="511d9-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="511d9-113">See also</span></span>

- [<span data-ttu-id="511d9-114">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="511d9-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
