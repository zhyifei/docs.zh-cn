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
ms.openlocfilehash: c2cc541b2a78f16d5ca6b19405794faa825a9d72
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615028"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="42737-102">ISymUnmanagedReader::GetDocumentVersion 方法</span><span class="sxs-lookup"><span data-stu-id="42737-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="42737-103">获取指定文档的指定版本。</span><span class="sxs-lookup"><span data-stu-id="42737-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="42737-104">文档版本从1开始，并在每次使用[UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md)方法更新文档时递增。</span><span class="sxs-lookup"><span data-stu-id="42737-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="42737-105">如果 `pbCurrent` 参数为 `true` ，则这是最新版本的文档。</span><span class="sxs-lookup"><span data-stu-id="42737-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42737-106">语法</span><span class="sxs-lookup"><span data-stu-id="42737-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42737-107">参数</span><span class="sxs-lookup"><span data-stu-id="42737-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="42737-108">中指定的文档。</span><span class="sxs-lookup"><span data-stu-id="42737-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="42737-109">弄指向一个变量的指针，该变量接收指定文档的版本。</span><span class="sxs-lookup"><span data-stu-id="42737-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="42737-110">弄指向一个变量的指针， `true` 如果这是该文档的最新版本，则为; `false` 如果它不是最新版本，则为。</span><span class="sxs-lookup"><span data-stu-id="42737-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42737-111">返回值</span><span class="sxs-lookup"><span data-stu-id="42737-111">Return Value</span></span>  
 <span data-ttu-id="42737-112">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="42737-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42737-113">要求</span><span class="sxs-lookup"><span data-stu-id="42737-113">Requirements</span></span>  
 <span data-ttu-id="42737-114">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="42737-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42737-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42737-115">See also</span></span>

- [<span data-ttu-id="42737-116">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="42737-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
