---
title: ISymUnmanagedMethod::GetRanges 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
ms.openlocfilehash: 1f1bd9c33f24847eae4ff7d26c5b996cd34afb72
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448935"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="e9fbf-102">ISymUnmanagedMethod::GetRanges 方法</span><span class="sxs-lookup"><span data-stu-id="e9fbf-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="e9fbf-103">给定文档中的某个位置后，将返回与该位置涵盖在此方法中的 Microsoft 中间语言（MSIL）范围对应的起始和结束偏移量对的数组。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="e9fbf-104">数组是整数数组，格式为 [开始、结束、启动、结束]。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="e9fbf-105">范围对的数目是数组的长度除以2。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9fbf-106">语法</span><span class="sxs-lookup"><span data-stu-id="e9fbf-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9fbf-107">参数</span><span class="sxs-lookup"><span data-stu-id="e9fbf-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="e9fbf-108">中为其请求偏移量的文档。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="e9fbf-109">中与范围对应的文档行。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="e9fbf-110">中与范围对应的文档列。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="e9fbf-111">[in] `ranges` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="e9fbf-112">弄指向 `ULONG32` 的指针，该指针接收包含范围所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="e9fbf-113">弄指向接收范围的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9fbf-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e9fbf-114">Return Value</span></span>  
 <span data-ttu-id="e9fbf-115">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="e9fbf-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9fbf-116">要求</span><span class="sxs-lookup"><span data-stu-id="e9fbf-116">Requirements</span></span>  
 <span data-ttu-id="e9fbf-117">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e9fbf-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9fbf-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9fbf-118">See also</span></span>

- [<span data-ttu-id="e9fbf-119">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="e9fbf-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
