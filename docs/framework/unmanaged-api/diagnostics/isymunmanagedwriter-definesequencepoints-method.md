---
title: ISymUnmanagedWriter::DefineSequencePoints 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
ms.openlocfilehash: 8889c412f414f38d1d18d33ec297e82fd052280d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614794"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="8a384-102">ISymUnmanagedWriter::DefineSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="8a384-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="8a384-103">在当前方法内定义一组序列点。</span><span class="sxs-lookup"><span data-stu-id="8a384-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="8a384-104">每个起始行和起始列定义方法中语句的开头。</span><span class="sxs-lookup"><span data-stu-id="8a384-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="8a384-105">每个结束行和结束列定义方法中语句的末尾。</span><span class="sxs-lookup"><span data-stu-id="8a384-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="8a384-106">应按偏移量的递增顺序对数组进行排序。</span><span class="sxs-lookup"><span data-stu-id="8a384-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="8a384-107">始终从方法的开头开始度量偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="8a384-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a384-108">语法</span><span class="sxs-lookup"><span data-stu-id="8a384-108">Syntax</span></span>  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a384-109">参数</span><span class="sxs-lookup"><span data-stu-id="8a384-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="8a384-110">中正在为其定义序列点的文档对象。</span><span class="sxs-lookup"><span data-stu-id="8a384-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="8a384-111">中， `ULONG32` 指示、、、 `offsets` `lines` `columns` `endLines` 和 `endColumns` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="8a384-111">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="8a384-112">中从方法的开头测量的序列点的偏移量。</span><span class="sxs-lookup"><span data-stu-id="8a384-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="8a384-113">中序列点的起始行号。</span><span class="sxs-lookup"><span data-stu-id="8a384-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="8a384-114">中序列点的起始列号。</span><span class="sxs-lookup"><span data-stu-id="8a384-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="8a384-115">中序列点的结束行号。</span><span class="sxs-lookup"><span data-stu-id="8a384-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="8a384-116">该参数为可选参数。</span><span class="sxs-lookup"><span data-stu-id="8a384-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="8a384-117">中序列点的结束列号。</span><span class="sxs-lookup"><span data-stu-id="8a384-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="8a384-118">该参数为可选参数。</span><span class="sxs-lookup"><span data-stu-id="8a384-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a384-119">返回值</span><span class="sxs-lookup"><span data-stu-id="8a384-119">Return Value</span></span>  
 <span data-ttu-id="8a384-120">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="8a384-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a384-121">要求</span><span class="sxs-lookup"><span data-stu-id="8a384-121">Requirements</span></span>  
 <span data-ttu-id="8a384-122">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="8a384-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a384-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a384-123">See also</span></span>

- [<span data-ttu-id="8a384-124">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="8a384-124">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
