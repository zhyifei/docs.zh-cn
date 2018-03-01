---
title: "ISymUnmanagedDocumentWriter::SetSource 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 287eba260ca20bae9da94ed2d00dcf1661fe14cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="d7231-102">ISymUnmanagedDocumentWriter::SetSource 方法</span><span class="sxs-lookup"><span data-stu-id="d7231-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="d7231-103">正在写入的文档集嵌入的源。</span><span class="sxs-lookup"><span data-stu-id="d7231-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7231-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7231-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7231-105">参数</span><span class="sxs-lookup"><span data-stu-id="d7231-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="d7231-106">[in]A`ULONG32`包含大小的`source`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d7231-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="d7231-107">[in]存储嵌入的源的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d7231-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7231-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d7231-108">Return Value</span></span>  
 <span data-ttu-id="d7231-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="d7231-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7231-110">惠?</span><span class="sxs-lookup"><span data-stu-id="d7231-110">Requirements</span></span>  
 <span data-ttu-id="d7231-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d7231-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7231-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7231-112">See Also</span></span>  
 [<span data-ttu-id="d7231-113">ISymUnmanagedDocumentWriter 接口</span><span class="sxs-lookup"><span data-stu-id="d7231-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
