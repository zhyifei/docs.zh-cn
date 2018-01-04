---
title: "ISymUnmanagedReader::GetDocumentVersion 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocumentVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2cb0abf887abaac4d7433b52a795beca509ec61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="e21f3-102">ISymUnmanagedReader::GetDocumentVersion 方法</span><span class="sxs-lookup"><span data-stu-id="e21f3-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="e21f3-103">获取指定的文档的指定的版本。</span><span class="sxs-lookup"><span data-stu-id="e21f3-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="e21f3-104">文档版本从 1 开始，并使用更新文档每次都会递增[UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e21f3-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="e21f3-105">如果`pbCurrent`参数是`true`，这是文档的最新版本。</span><span class="sxs-lookup"><span data-stu-id="e21f3-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e21f3-106">语法</span><span class="sxs-lookup"><span data-stu-id="e21f3-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e21f3-107">参数</span><span class="sxs-lookup"><span data-stu-id="e21f3-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="e21f3-108">[in]指定的文档。</span><span class="sxs-lookup"><span data-stu-id="e21f3-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="e21f3-109">[out]指向接收指定文档的版本的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="e21f3-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="e21f3-110">[out]指向接收的变量的指针`true`如果这是最新版本的文档，或`false`如果不是最新版本。</span><span class="sxs-lookup"><span data-stu-id="e21f3-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e21f3-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e21f3-111">Return Value</span></span>  
 <span data-ttu-id="e21f3-112">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e21f3-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e21f3-113">惠?</span><span class="sxs-lookup"><span data-stu-id="e21f3-113">Requirements</span></span>  
 <span data-ttu-id="e21f3-114">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e21f3-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e21f3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e21f3-115">See Also</span></span>  
 [<span data-ttu-id="e21f3-116">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="e21f3-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
