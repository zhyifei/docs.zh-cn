---
title: "ISymUnmanagedWriter::SetMethodSourceRange 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetMethodSourceRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 85ed0a73b4862702895e737f2df639b8da7f7679
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="a1ccd-102">ISymUnmanagedWriter::SetMethodSourceRange 方法</span><span class="sxs-lookup"><span data-stu-id="a1ccd-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="a1ccd-103">指定的真正开始和结束源文件中的方法。</span><span class="sxs-lookup"><span data-stu-id="a1ccd-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="a1ccd-104">使用此方法指定独立存在的方法中的序列点于方法的范围。</span><span class="sxs-lookup"><span data-stu-id="a1ccd-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1ccd-105">语法</span><span class="sxs-lookup"><span data-stu-id="a1ccd-105">Syntax</span></span>  
  
```  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1ccd-106">参数</span><span class="sxs-lookup"><span data-stu-id="a1ccd-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="a1ccd-107">[in]指向包含的起始位置的文档的指针。</span><span class="sxs-lookup"><span data-stu-id="a1ccd-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="a1ccd-108">[in]起始行号中。</span><span class="sxs-lookup"><span data-stu-id="a1ccd-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="a1ccd-109">[in]起始列。</span><span class="sxs-lookup"><span data-stu-id="a1ccd-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="a1ccd-110">[in]指向包含的结束位置的文档的指针。</span><span class="sxs-lookup"><span data-stu-id="a1ccd-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="a1ccd-111">[in]结束的行号。</span><span class="sxs-lookup"><span data-stu-id="a1ccd-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="a1ccd-112">[in]结束列号。</span><span class="sxs-lookup"><span data-stu-id="a1ccd-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1ccd-113">返回值</span><span class="sxs-lookup"><span data-stu-id="a1ccd-113">Return Value</span></span>  
 <span data-ttu-id="a1ccd-114">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="a1ccd-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1ccd-115">要求</span><span class="sxs-lookup"><span data-stu-id="a1ccd-115">Requirements</span></span>  
 <span data-ttu-id="a1ccd-116">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a1ccd-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ccd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1ccd-117">See Also</span></span>  
 [<span data-ttu-id="a1ccd-118">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="a1ccd-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
