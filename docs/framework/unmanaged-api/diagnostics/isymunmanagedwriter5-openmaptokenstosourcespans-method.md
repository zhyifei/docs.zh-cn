---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 方法
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60c1984e6193481efdaaeb82a2bc025aef67a33f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534430"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="f8afd-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="f8afd-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="f8afd-103">打开一个特殊的自定义数据分区发出令牌源范围映射到的信息。</span><span class="sxs-lookup"><span data-stu-id="f8afd-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="f8afd-104">方法已打开，或反之，是错误时，请打开此部分。</span><span class="sxs-lookup"><span data-stu-id="f8afd-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8afd-105">语法</span><span class="sxs-lookup"><span data-stu-id="f8afd-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f8afd-106">返回值</span><span class="sxs-lookup"><span data-stu-id="f8afd-106">Return Value</span></span>  
 <span data-ttu-id="f8afd-107">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="f8afd-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8afd-108">要求</span><span class="sxs-lookup"><span data-stu-id="f8afd-108">Requirements</span></span>  
 <span data-ttu-id="f8afd-109">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f8afd-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8afd-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8afd-110">See also</span></span>
- [<span data-ttu-id="f8afd-111">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="f8afd-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
