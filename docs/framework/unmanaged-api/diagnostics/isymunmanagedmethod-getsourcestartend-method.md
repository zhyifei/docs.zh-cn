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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d32e3ac0ff3179a9bb32f82e5ca33fd89c4ec410
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151185"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="125fb-102">ISymUnmanagedMethod::GetSourceStartEnd 方法</span><span class="sxs-lookup"><span data-stu-id="125fb-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="125fb-103">获取此方法的源的开始和结束文档位置。</span><span class="sxs-lookup"><span data-stu-id="125fb-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="125fb-104">第一个数组位置开始，且第二个数组位置是终点。</span><span class="sxs-lookup"><span data-stu-id="125fb-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="125fb-105">语法</span><span class="sxs-lookup"><span data-stu-id="125fb-105">Syntax</span></span>  
  
```  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="125fb-106">参数</span><span class="sxs-lookup"><span data-stu-id="125fb-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="125fb-107">[in]起始和结束源文档。</span><span class="sxs-lookup"><span data-stu-id="125fb-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="125fb-108">[in]起始和结束行中相应的源文档。</span><span class="sxs-lookup"><span data-stu-id="125fb-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="125fb-109">[in]起始和结束列在相应的源文档。</span><span class="sxs-lookup"><span data-stu-id="125fb-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="125fb-110">[out]`true`位置定义; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="125fb-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="125fb-111">返回值</span><span class="sxs-lookup"><span data-stu-id="125fb-111">Return Value</span></span>  
 <span data-ttu-id="125fb-112">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="125fb-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="125fb-113">要求</span><span class="sxs-lookup"><span data-stu-id="125fb-113">Requirements</span></span>  
 <span data-ttu-id="125fb-114">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="125fb-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="125fb-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="125fb-115">See also</span></span>

- [<span data-ttu-id="125fb-116">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="125fb-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
