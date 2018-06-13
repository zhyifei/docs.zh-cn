---
title: ISymUnmanagedDocument::GetSourceRange 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00baed93bd9ab48c92de83dac76931c3149afc2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424622"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="66d44-102">ISymUnmanagedDocument::GetSourceRange 方法</span><span class="sxs-lookup"><span data-stu-id="66d44-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="66d44-103">返回到给定缓冲区中嵌入源的指定的范围。</span><span class="sxs-lookup"><span data-stu-id="66d44-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="66d44-104">缓冲区必须足够大以保存源。</span><span class="sxs-lookup"><span data-stu-id="66d44-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d44-105">语法</span><span class="sxs-lookup"><span data-stu-id="66d44-105">Syntax</span></span>  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66d44-106">参数</span><span class="sxs-lookup"><span data-stu-id="66d44-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="66d44-107">[in]当前文档中的起始行。</span><span class="sxs-lookup"><span data-stu-id="66d44-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="66d44-108">[in]当前文档中的起始列。</span><span class="sxs-lookup"><span data-stu-id="66d44-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="66d44-109">[in]当前文档中的最后一行。</span><span class="sxs-lookup"><span data-stu-id="66d44-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="66d44-110">[in]当前文档中最后一列。</span><span class="sxs-lookup"><span data-stu-id="66d44-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="66d44-111">[in]源，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="66d44-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="66d44-112">[out]指向接收源大小的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="66d44-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="66d44-113">[out]大小和源文档，以字节为单位的指定范围的长度。</span><span class="sxs-lookup"><span data-stu-id="66d44-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66d44-114">返回值</span><span class="sxs-lookup"><span data-stu-id="66d44-114">Return Value</span></span>  
 <span data-ttu-id="66d44-115">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="66d44-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d44-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="66d44-116">See Also</span></span>  
 [<span data-ttu-id="66d44-117">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="66d44-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
