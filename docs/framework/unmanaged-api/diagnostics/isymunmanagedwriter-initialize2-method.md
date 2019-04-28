---
title: ISymUnmanagedWriter::Initialize2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e645f79018d4ad41451faa07eba860e68b917539
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700782"
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="e231f-102">ISymUnmanagedWriter::Initialize2 方法</span><span class="sxs-lookup"><span data-stu-id="e231f-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="e231f-103">此编写器将与之关联的元数据发射器接口和设置输出文件将写入调试符号的名称。</span><span class="sxs-lookup"><span data-stu-id="e231f-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="e231f-104">此方法还允许您设置的程序数据库 (PDB) 文件的最终位置。</span><span class="sxs-lookup"><span data-stu-id="e231f-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e231f-105">语法</span><span class="sxs-lookup"><span data-stu-id="e231f-105">Syntax</span></span>  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e231f-106">参数</span><span class="sxs-lookup"><span data-stu-id="e231f-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="e231f-107">[in]指向元数据发射器接口的指针。</span><span class="sxs-lookup"><span data-stu-id="e231f-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="e231f-108">[in]一个指向`WCHAR`，其中包含要写入调试符号的文件名称。</span><span class="sxs-lookup"><span data-stu-id="e231f-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="e231f-109">如果为不使用文件名的编写器指定文件名，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="e231f-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="e231f-110">[in]如果指定，将符号编写器发出符号置于给定<xref:System.Runtime.InteropServices.ComTypes.IStream>而不是文件中指定`filename`参数。</span><span class="sxs-lookup"><span data-stu-id="e231f-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="e231f-111">`pIStream` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="e231f-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="e231f-112">[in]`true`如果这是完全重新生成;`false`如果这是增量编译。</span><span class="sxs-lookup"><span data-stu-id="e231f-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="e231f-113">[in]一个指向`WCHAR`，它是 PDB 文件的最后一个位置的路径字符串。</span><span class="sxs-lookup"><span data-stu-id="e231f-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e231f-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e231f-114">Return Value</span></span>  
 <span data-ttu-id="e231f-115">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e231f-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e231f-116">要求</span><span class="sxs-lookup"><span data-stu-id="e231f-116">Requirements</span></span>  
 <span data-ttu-id="e231f-117">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e231f-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e231f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e231f-118">See also</span></span>

- [<span data-ttu-id="e231f-119">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="e231f-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e231f-120">Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="e231f-120">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
