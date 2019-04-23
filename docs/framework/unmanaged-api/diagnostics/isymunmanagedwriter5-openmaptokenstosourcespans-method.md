---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 方法
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dc2ced988f7277c994eb9449e7c26efa5450b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222674"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="aaa89-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="aaa89-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="aaa89-103">打开一个特殊的自定义数据分区发出令牌源范围映射到的信息。</span><span class="sxs-lookup"><span data-stu-id="aaa89-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="aaa89-104">方法已打开，或反之，是错误时，请打开此部分。</span><span class="sxs-lookup"><span data-stu-id="aaa89-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa89-105">语法</span><span class="sxs-lookup"><span data-stu-id="aaa89-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="aaa89-106">返回值</span><span class="sxs-lookup"><span data-stu-id="aaa89-106">Return Value</span></span>  
 <span data-ttu-id="aaa89-107">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="aaa89-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaa89-108">要求</span><span class="sxs-lookup"><span data-stu-id="aaa89-108">Requirements</span></span>  
 <span data-ttu-id="aaa89-109">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aaa89-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa89-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="aaa89-110">See also</span></span>

- [<span data-ttu-id="aaa89-111">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="aaa89-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
