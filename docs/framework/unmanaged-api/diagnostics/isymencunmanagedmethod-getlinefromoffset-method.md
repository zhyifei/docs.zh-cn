---
title: ISymENCUnmanagedMethod::GetLineFromOffset 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: 94a571a4bc01b805387aebe5a6e23bad0b735313
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448650"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="dcf25-102">ISymENCUnmanagedMethod::GetLineFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="dcf25-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="dcf25-103">获取与偏移量关联的行信息。</span><span class="sxs-lookup"><span data-stu-id="dcf25-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="dcf25-104">如果 offset 参数（`dwOffset`）不是序列点，则此方法将获取与上一个偏移量关联的行信息。</span><span class="sxs-lookup"><span data-stu-id="dcf25-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf25-105">语法</span><span class="sxs-lookup"><span data-stu-id="dcf25-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcf25-106">参数</span><span class="sxs-lookup"><span data-stu-id="dcf25-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="dcf25-107">中一个包含偏移量的 `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="dcf25-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="dcf25-108">弄指向接收行的 `ULONG32` 的指针。</span><span class="sxs-lookup"><span data-stu-id="dcf25-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="dcf25-109">弄指向接收列的 `ULONG32` 的指针。</span><span class="sxs-lookup"><span data-stu-id="dcf25-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="dcf25-110">弄指向接收结束行的 `ULONG32` 的指针。</span><span class="sxs-lookup"><span data-stu-id="dcf25-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="dcf25-111">弄指向接收结束列的 `ULONG32` 的指针。</span><span class="sxs-lookup"><span data-stu-id="dcf25-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="dcf25-112">弄指向接收关联序列点的 `ULONG32` 的指针。</span><span class="sxs-lookup"><span data-stu-id="dcf25-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dcf25-113">返回值</span><span class="sxs-lookup"><span data-stu-id="dcf25-113">Return Value</span></span>  
 <span data-ttu-id="dcf25-114">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="dcf25-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf25-115">要求</span><span class="sxs-lookup"><span data-stu-id="dcf25-115">Requirements</span></span>  
 <span data-ttu-id="dcf25-116">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="dcf25-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf25-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcf25-117">See also</span></span>

- [<span data-ttu-id="dcf25-118">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="dcf25-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
