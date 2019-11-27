---
title: ISymUnmanagedMethod::GetSourceStartEnd 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: 01ab69b73a7bc4929e2ebd49b3847f8d7c4646a2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448863"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="1147d-102">ISymUnmanagedMethod::GetSourceStartEnd 方法</span><span class="sxs-lookup"><span data-stu-id="1147d-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="1147d-103">获取此方法的源的起始和结束文档位置。</span><span class="sxs-lookup"><span data-stu-id="1147d-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="1147d-104">第一个数组位置是开始，第二个数组位置是结束。</span><span class="sxs-lookup"><span data-stu-id="1147d-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1147d-105">语法</span><span class="sxs-lookup"><span data-stu-id="1147d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1147d-106">参数</span><span class="sxs-lookup"><span data-stu-id="1147d-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="1147d-107">中起始和结束源文档。</span><span class="sxs-lookup"><span data-stu-id="1147d-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="1147d-108">中对应的源文档中的起始和结束行。</span><span class="sxs-lookup"><span data-stu-id="1147d-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="1147d-109">中对应的源文档中的起始和结束列。</span><span class="sxs-lookup"><span data-stu-id="1147d-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1147d-110">[out] `true` 是否定义了位置;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="1147d-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1147d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="1147d-111">Return Value</span></span>  
 <span data-ttu-id="1147d-112">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="1147d-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1147d-113">要求</span><span class="sxs-lookup"><span data-stu-id="1147d-113">Requirements</span></span>  
 <span data-ttu-id="1147d-114">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="1147d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1147d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1147d-115">See also</span></span>

- [<span data-ttu-id="1147d-116">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="1147d-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
