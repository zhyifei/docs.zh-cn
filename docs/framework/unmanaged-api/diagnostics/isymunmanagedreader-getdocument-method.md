---
title: ISymUnmanagedReader::GetDocument 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32b7505a9e512f3c3e3e7a9fcbff40276e98ecf4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759345"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="b6f9b-102">ISymUnmanagedReader::GetDocument 方法</span><span class="sxs-lookup"><span data-stu-id="b6f9b-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="b6f9b-103">查找文档。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-103">Finds a document.</span></span> <span data-ttu-id="b6f9b-104">文档语言、 供应商和类型是可选的。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6f9b-105">语法</span><span class="sxs-lookup"><span data-stu-id="b6f9b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6f9b-106">参数</span><span class="sxs-lookup"><span data-stu-id="b6f9b-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="b6f9b-107">[in]标识文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="b6f9b-108">[in]文档语言。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-108">[in] The document language.</span></span> <span data-ttu-id="b6f9b-109">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="b6f9b-110">[in]文档语言供应商的标识。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="b6f9b-111">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="b6f9b-112">[in]文档的类型。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-112">[in] The type of the document.</span></span> <span data-ttu-id="b6f9b-113">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b6f9b-114">[out]指向返回的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6f9b-115">返回值</span><span class="sxs-lookup"><span data-stu-id="b6f9b-115">Return Value</span></span>  
 <span data-ttu-id="b6f9b-116">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="b6f9b-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6f9b-117">要求</span><span class="sxs-lookup"><span data-stu-id="b6f9b-117">Requirements</span></span>  
 <span data-ttu-id="b6f9b-118">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6f9b-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6f9b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6f9b-119">See also</span></span>

- [<span data-ttu-id="b6f9b-120">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="b6f9b-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
