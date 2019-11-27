---
title: ISymUnmanagedWriter::DefineDocument 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
ms.openlocfilehash: 02b270677131d0960db67b0ac8db38cba2b5e2df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428056"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="58d1c-102">ISymUnmanagedWriter::DefineDocument 方法</span><span class="sxs-lookup"><span data-stu-id="58d1c-102">ISymUnmanagedWriter::DefineDocument Method</span></span>
<span data-ttu-id="58d1c-103">定义源文档。</span><span class="sxs-lookup"><span data-stu-id="58d1c-103">Defines a source document.</span></span> <span data-ttu-id="58d1c-104">为已知语言、供应商和文档类型提供了 Guid。</span><span class="sxs-lookup"><span data-stu-id="58d1c-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d1c-105">语法</span><span class="sxs-lookup"><span data-stu-id="58d1c-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58d1c-106">参数</span><span class="sxs-lookup"><span data-stu-id="58d1c-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="58d1c-107">中指向 `WCHAR` 的指针，该指针定义标识文档的统一资源定位器（URL）。</span><span class="sxs-lookup"><span data-stu-id="58d1c-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="58d1c-108">中指向定义文档语言的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="58d1c-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="58d1c-109">中一个指针，指向用于定义文档语言的供应商标识的 GUID。</span><span class="sxs-lookup"><span data-stu-id="58d1c-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="58d1c-110">中指向定义文档类型的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="58d1c-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="58d1c-111">弄指向返回的[ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="58d1c-111">[out] A pointer to the returned [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58d1c-112">返回值</span><span class="sxs-lookup"><span data-stu-id="58d1c-112">Return Value</span></span>  
 <span data-ttu-id="58d1c-113">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="58d1c-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58d1c-114">要求</span><span class="sxs-lookup"><span data-stu-id="58d1c-114">Requirements</span></span>  
 <span data-ttu-id="58d1c-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="58d1c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d1c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58d1c-116">See also</span></span>

- [<span data-ttu-id="58d1c-117">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="58d1c-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
