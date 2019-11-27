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
ms.openlocfilehash: 2b901a3dac499f1ce3f843c59122dd8fd5022147
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427959"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="e811a-102">ISymUnmanagedWriter::GetDebugInfo 方法</span><span class="sxs-lookup"><span data-stu-id="e811a-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>
<span data-ttu-id="e811a-103">返回编译器编写可移植可执行（PE）文件头中的调试目录条目所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e811a-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="e811a-104">符号编写器填写除 `TimeDateStamp` 和 `PointerToRawData`之外的所有字段。</span><span class="sxs-lookup"><span data-stu-id="e811a-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="e811a-105">（编译器负责正确设置这两个字段。）</span><span class="sxs-lookup"><span data-stu-id="e811a-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="e811a-106">编译器应调用此方法，将数据 blob 发出到 PE 文件，将 IMAGE_DEBUG_DIRECTORY 中的 `PointerToRawData` 字段设置为指向发出的数据，并将 IMAGE_DEBUG_DIRECTORY 写入 PE 文件。</span><span class="sxs-lookup"><span data-stu-id="e811a-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="e811a-107">编译器还应将 `TimeDateStamp` 字段设置为等于正在生成的 PE 文件的 `TimeDateStamp`。</span><span class="sxs-lookup"><span data-stu-id="e811a-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e811a-108">语法</span><span class="sxs-lookup"><span data-stu-id="e811a-108">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e811a-109">参数</span><span class="sxs-lookup"><span data-stu-id="e811a-109">Parameters</span></span>  
 `pIDD`  
 <span data-ttu-id="e811a-110">[in，out]指向符号编写器将填写的 IMAGE_DEBUG_DIRECTORY 的指针。</span><span class="sxs-lookup"><span data-stu-id="e811a-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="e811a-111">中包含调试数据大小的 `DWORD`。</span><span class="sxs-lookup"><span data-stu-id="e811a-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="e811a-112">弄指向 `DWORD` 的指针，该指针接收包含调试数据所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="e811a-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="e811a-113">弄指向缓冲区的指针，该缓冲区足以容纳符号存储区的调试数据。</span><span class="sxs-lookup"><span data-stu-id="e811a-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e811a-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e811a-114">Return Value</span></span>  
 <span data-ttu-id="e811a-115">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="e811a-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e811a-116">要求</span><span class="sxs-lookup"><span data-stu-id="e811a-116">Requirements</span></span>  
 <span data-ttu-id="e811a-117">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e811a-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e811a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e811a-118">See also</span></span>

- [<span data-ttu-id="e811a-119">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="e811a-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
