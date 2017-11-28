---
title: "ISymUnmanagedWriter::Initialize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bae368919941e6a0b234736f789320b62405a17b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="e0920-102">ISymUnmanagedWriter::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="e0920-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="e0920-103">设置元数据发射器接口此编写器将与之相关联，并设置将向其写入调试符号的输出文件名称。</span><span class="sxs-lookup"><span data-stu-id="e0920-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="e0920-104">可以一次调用此方法，它必须在编写器的任何其他方法之前调用。</span><span class="sxs-lookup"><span data-stu-id="e0920-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="e0920-105">某些编写器可能需要的文件名称。</span><span class="sxs-lookup"><span data-stu-id="e0920-105">Some writers may require a file name.</span></span> <span data-ttu-id="e0920-106">但是，始终可以向此方法，而不使用文件名的编写器任何负面影响传递文件名称。</span><span class="sxs-lookup"><span data-stu-id="e0920-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0920-107">语法</span><span class="sxs-lookup"><span data-stu-id="e0920-107">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0920-108">参数</span><span class="sxs-lookup"><span data-stu-id="e0920-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="e0920-109">[in]指向元数据发射器接口的指针。</span><span class="sxs-lookup"><span data-stu-id="e0920-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="e0920-110">[in]将写入调试符号的文件名。</span><span class="sxs-lookup"><span data-stu-id="e0920-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="e0920-111">如果为不使用文件名的编写器指定文件名，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="e0920-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="e0920-112">[in]如果指定，符号编写器将发出到符号给定<xref:System.Runtime.InteropServices.ComTypes.IStream>而不是中指定的文件`filename`参数。</span><span class="sxs-lookup"><span data-stu-id="e0920-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="e0920-113">`pIStream` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="e0920-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="e0920-114">[in]`true`如果这是完全重新生成;`false`如果这是增量编译。</span><span class="sxs-lookup"><span data-stu-id="e0920-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0920-115">返回值</span><span class="sxs-lookup"><span data-stu-id="e0920-115">Return Value</span></span>  
 <span data-ttu-id="e0920-116">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e0920-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0920-117">要求</span><span class="sxs-lookup"><span data-stu-id="e0920-117">Requirements</span></span>  
 <span data-ttu-id="e0920-118">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e0920-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0920-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0920-119">See Also</span></span>  
 [<span data-ttu-id="e0920-120">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="e0920-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="e0920-121">Initialize2 方法</span><span class="sxs-lookup"><span data-stu-id="e0920-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
