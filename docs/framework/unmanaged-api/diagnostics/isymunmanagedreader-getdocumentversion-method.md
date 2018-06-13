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
ms.openlocfilehash: 31b550c7b3cec999b0420fbdc06582a24f420abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425979"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="d3508-102">ISymUnmanagedReader::GetDocumentVersion 方法</span><span class="sxs-lookup"><span data-stu-id="d3508-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="d3508-103">获取指定的文档的指定的版本。</span><span class="sxs-lookup"><span data-stu-id="d3508-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="d3508-104">文档版本从 1 开始，并使用更新文档每次都会递增[UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d3508-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="d3508-105">如果`pbCurrent`参数是`true`，这是文档的最新版本。</span><span class="sxs-lookup"><span data-stu-id="d3508-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3508-106">语法</span><span class="sxs-lookup"><span data-stu-id="d3508-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3508-107">参数</span><span class="sxs-lookup"><span data-stu-id="d3508-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="d3508-108">[in]指定的文档。</span><span class="sxs-lookup"><span data-stu-id="d3508-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="d3508-109">[out]指向接收指定文档的版本的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="d3508-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="d3508-110">[out]指向接收的变量的指针`true`如果这是最新版本的文档，或`false`如果不是最新版本。</span><span class="sxs-lookup"><span data-stu-id="d3508-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3508-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d3508-111">Return Value</span></span>  
 <span data-ttu-id="d3508-112">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="d3508-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3508-113">要求</span><span class="sxs-lookup"><span data-stu-id="d3508-113">Requirements</span></span>  
 <span data-ttu-id="d3508-114">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d3508-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3508-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3508-115">See Also</span></span>  
 [<span data-ttu-id="d3508-116">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="d3508-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
