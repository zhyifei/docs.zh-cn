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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92353cfc2d9ce39074bf43937b5673ff51e34822
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080002"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="dd3f9-102">ISymUnmanagedReader::GetDocumentVersion 方法</span><span class="sxs-lookup"><span data-stu-id="dd3f9-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="dd3f9-103">获取指定的文档的指定的版本。</span><span class="sxs-lookup"><span data-stu-id="dd3f9-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="dd3f9-104">文档版本从 1 开始，每次更新文档时使用递增[UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="dd3f9-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="dd3f9-105">如果`pbCurrent`参数是`true`，这是文档的最新版本。</span><span class="sxs-lookup"><span data-stu-id="dd3f9-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd3f9-106">语法</span><span class="sxs-lookup"><span data-stu-id="dd3f9-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd3f9-107">参数</span><span class="sxs-lookup"><span data-stu-id="dd3f9-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="dd3f9-108">[in]指定的文档。</span><span class="sxs-lookup"><span data-stu-id="dd3f9-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="dd3f9-109">[out]指向一个变量来接收指定文档的版本的指针。</span><span class="sxs-lookup"><span data-stu-id="dd3f9-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="dd3f9-110">[out]指向一个变量来接收`true`如果这是最新版本的文档，或`false`如果不是最新版本。</span><span class="sxs-lookup"><span data-stu-id="dd3f9-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd3f9-111">返回值</span><span class="sxs-lookup"><span data-stu-id="dd3f9-111">Return Value</span></span>  
 <span data-ttu-id="dd3f9-112">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="dd3f9-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd3f9-113">要求</span><span class="sxs-lookup"><span data-stu-id="dd3f9-113">Requirements</span></span>  
 <span data-ttu-id="dd3f9-114">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dd3f9-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd3f9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd3f9-115">See also</span></span>

- [<span data-ttu-id="dd3f9-116">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="dd3f9-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
