---
title: ISymUnmanagedWriter::GetDebugInfo 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 41d96c6d2024dbc3cab669f2dba2f99faef89f4b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074243"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="ab943-102">ISymUnmanagedWriter::GetDebugInfo 方法</span><span class="sxs-lookup"><span data-stu-id="ab943-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>
<span data-ttu-id="ab943-103">返回编译器编写可移植可执行 (PE) 文件头中的调试目录项所需的信息。</span><span class="sxs-lookup"><span data-stu-id="ab943-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="ab943-104">符号编辑器填写所有字段除外`TimeDateStamp`和`PointerToRawData`。</span><span class="sxs-lookup"><span data-stu-id="ab943-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="ab943-105">（编译器负责适当地设置这两个字段。）</span><span class="sxs-lookup"><span data-stu-id="ab943-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="ab943-106">编译器应调用此方法，发出到 PE 文件的数据 blob，设置`PointerToRawData`字段 IMAGE_DEBUG_DIRECTORY 指向发出的数据，并将 IMAGE_DEBUG_DIRECTORY 写到 PE 文件中。</span><span class="sxs-lookup"><span data-stu-id="ab943-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="ab943-107">编译器还应设置`TimeDateStamp`字段为等于`TimeDateStamp`正在生成的 PE 文件。</span><span class="sxs-lookup"><span data-stu-id="ab943-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab943-108">语法</span><span class="sxs-lookup"><span data-stu-id="ab943-108">Syntax</span></span>  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab943-109">参数</span><span class="sxs-lookup"><span data-stu-id="ab943-109">Parameters</span></span>  
 `pIDD`  
 <span data-ttu-id="ab943-110">[in、 out]指向符号编写器将填写 IMAGE_DEBUG_DIRECTORY 的指针。</span><span class="sxs-lookup"><span data-stu-id="ab943-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="ab943-111">[in]一个`DWORD`包含调试数据的大小。</span><span class="sxs-lookup"><span data-stu-id="ab943-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="ab943-112">[out]一个指向`DWORD`接收包含调试数据所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="ab943-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="ab943-113">[out]指向的缓冲区，则大到足以保留符号存储区的调试数据的指针。</span><span class="sxs-lookup"><span data-stu-id="ab943-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab943-114">返回值</span><span class="sxs-lookup"><span data-stu-id="ab943-114">Return Value</span></span>  
 <span data-ttu-id="ab943-115">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="ab943-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab943-116">要求</span><span class="sxs-lookup"><span data-stu-id="ab943-116">Requirements</span></span>  
 <span data-ttu-id="ab943-117">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ab943-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab943-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab943-118">See also</span></span>

- [<span data-ttu-id="ab943-119">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="ab943-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
