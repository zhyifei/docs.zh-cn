---
title: ISymUnmanagedWriter::Initialize 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 417cf623948d16147f9a1242d714f4df1311a314
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212045"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="d1aaa-102">ISymUnmanagedWriter::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="d1aaa-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="d1aaa-103">此编写器将与之关联的元数据发射器接口和设置输出文件将写入调试符号的名称。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="d1aaa-104">只有一次调用此方法，必须在调用之前编写器的任何其他方法。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="d1aaa-105">某些编写器可能需要的文件名称。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-105">Some writers may require a file name.</span></span> <span data-ttu-id="d1aaa-106">但是，你始终可以给此方法没有任何负面影响的未使用的文件名的编写器传递文件名称。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1aaa-107">语法</span><span class="sxs-lookup"><span data-stu-id="d1aaa-107">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1aaa-108">参数</span><span class="sxs-lookup"><span data-stu-id="d1aaa-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="d1aaa-109">[in]指向元数据发射器接口的指针。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="d1aaa-110">[in]写入调试符号的文件名。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="d1aaa-111">如果为不使用文件名的编写器指定文件名，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="d1aaa-112">[in]如果指定，符号编写器将发出符号置于给定<xref:System.Runtime.InteropServices.ComTypes.IStream>而不是文件中指定`filename`参数。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="d1aaa-113">`pIStream` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="d1aaa-114">[in]`true`如果这是完全重新生成;`false`如果这是增量编译。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1aaa-115">返回值</span><span class="sxs-lookup"><span data-stu-id="d1aaa-115">Return Value</span></span>  
 <span data-ttu-id="d1aaa-116">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1aaa-117">要求</span><span class="sxs-lookup"><span data-stu-id="d1aaa-117">Requirements</span></span>  
 <span data-ttu-id="d1aaa-118">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d1aaa-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1aaa-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1aaa-119">See also</span></span>

- [<span data-ttu-id="d1aaa-120">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="d1aaa-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d1aaa-121">Initialize2 方法</span><span class="sxs-lookup"><span data-stu-id="d1aaa-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
