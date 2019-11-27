---
title: ISymUnmanagedReader::GetDocumentVersion 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: 3bc578be680951a1d41c92fb2169c860882b2e31
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448305"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="399bc-102">ISymUnmanagedReader::GetDocumentVersion 方法</span><span class="sxs-lookup"><span data-stu-id="399bc-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="399bc-103">获取指定文档的指定版本。</span><span class="sxs-lookup"><span data-stu-id="399bc-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="399bc-104">文档版本从1开始，并在每次使用[UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)方法更新文档时递增。</span><span class="sxs-lookup"><span data-stu-id="399bc-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="399bc-105">如果 `pbCurrent` 参数 `true`，则这是该文档的最新版本。</span><span class="sxs-lookup"><span data-stu-id="399bc-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="399bc-106">语法</span><span class="sxs-lookup"><span data-stu-id="399bc-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="399bc-107">参数</span><span class="sxs-lookup"><span data-stu-id="399bc-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="399bc-108">中指定的文档。</span><span class="sxs-lookup"><span data-stu-id="399bc-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="399bc-109">弄指向一个变量的指针，该变量接收指定文档的版本。</span><span class="sxs-lookup"><span data-stu-id="399bc-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="399bc-110">弄指向一个变量的指针，该变量接收 `true` 如果这是最新版本的文档，则为; 如果不是最新版本，则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="399bc-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="399bc-111">返回值</span><span class="sxs-lookup"><span data-stu-id="399bc-111">Return Value</span></span>  
 <span data-ttu-id="399bc-112">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="399bc-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="399bc-113">要求</span><span class="sxs-lookup"><span data-stu-id="399bc-113">Requirements</span></span>  
 <span data-ttu-id="399bc-114">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="399bc-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399bc-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="399bc-115">See also</span></span>

- [<span data-ttu-id="399bc-116">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="399bc-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
