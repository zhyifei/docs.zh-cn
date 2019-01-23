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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98015af4a79a9fca4945708e6d0baeb61e46876f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531221"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="73cf4-102">ISymENCUnmanagedMethod::GetLineFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="73cf4-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="73cf4-103">获取与某一偏移量关联的行信息。</span><span class="sxs-lookup"><span data-stu-id="73cf4-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="73cf4-104">如果偏移量的参数 (`dwOffset`) 不是序列点，此方法获取与前一个偏移量关联的行信息。</span><span class="sxs-lookup"><span data-stu-id="73cf4-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73cf4-105">语法</span><span class="sxs-lookup"><span data-stu-id="73cf4-105">Syntax</span></span>  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73cf4-106">参数</span><span class="sxs-lookup"><span data-stu-id="73cf4-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="73cf4-107">[in]一个`ULONG32`包含的偏移量。</span><span class="sxs-lookup"><span data-stu-id="73cf4-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="73cf4-108">[out]一个指向`ULONG32`接收行。</span><span class="sxs-lookup"><span data-stu-id="73cf4-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="73cf4-109">[out]一个指向`ULONG32`接收列。</span><span class="sxs-lookup"><span data-stu-id="73cf4-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="73cf4-110">[out]一个指向`ULONG32`接收结束行。</span><span class="sxs-lookup"><span data-stu-id="73cf4-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="73cf4-111">[out]一个指向`ULONG32`，它接收的结束列。</span><span class="sxs-lookup"><span data-stu-id="73cf4-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="73cf4-112">[out]一个指向`ULONG32`接收相关联的序列点。</span><span class="sxs-lookup"><span data-stu-id="73cf4-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73cf4-113">返回值</span><span class="sxs-lookup"><span data-stu-id="73cf4-113">Return Value</span></span>  
 <span data-ttu-id="73cf4-114">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="73cf4-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73cf4-115">要求</span><span class="sxs-lookup"><span data-stu-id="73cf4-115">Requirements</span></span>  
 <span data-ttu-id="73cf4-116">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="73cf4-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73cf4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="73cf4-117">See also</span></span>
- [<span data-ttu-id="73cf4-118">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="73cf4-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
