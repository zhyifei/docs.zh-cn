---
title: ISymUnmanagedWriter5 接口
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6ed8c6e61c558a4bc9e3f92d559615ac93ecff8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962333"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="aea2a-102">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="aea2a-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="aea2a-103">ISymUnmanagedWriter5 接口。</span><span class="sxs-lookup"><span data-stu-id="aea2a-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aea2a-104">语法</span><span class="sxs-lookup"><span data-stu-id="aea2a-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="aea2a-105">方法</span><span class="sxs-lookup"><span data-stu-id="aea2a-105">Methods</span></span>  
 <span data-ttu-id="aea2a-106">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="aea2a-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="aea2a-107">方法</span><span class="sxs-lookup"><span data-stu-id="aea2a-107">Method</span></span>|<span data-ttu-id="aea2a-108">描述</span><span class="sxs-lookup"><span data-stu-id="aea2a-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aea2a-109">CloseMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="aea2a-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="aea2a-110">关闭令牌源跨度映射信息的特殊的自定义数据部分。</span><span class="sxs-lookup"><span data-stu-id="aea2a-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="aea2a-111">已关闭后，可以添加未映射的更多信息。</span><span class="sxs-lookup"><span data-stu-id="aea2a-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="aea2a-112">MapTokenToSourceSpan 方法</span><span class="sxs-lookup"><span data-stu-id="aea2a-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="aea2a-113">映射到给定的源行的给定元数据标记跨越中指定的源文件中。</span><span class="sxs-lookup"><span data-stu-id="aea2a-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="aea2a-114">必须调用之间调用[OpenMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)并[CloseMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)。</span><span class="sxs-lookup"><span data-stu-id="aea2a-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="aea2a-115">OpenMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="aea2a-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="aea2a-116">打开一个特殊的自定义数据分区发出令牌源范围映射到的信息。</span><span class="sxs-lookup"><span data-stu-id="aea2a-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="aea2a-117">方法已打开，或反之，是错误时，请打开此部分。</span><span class="sxs-lookup"><span data-stu-id="aea2a-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aea2a-118">要求</span><span class="sxs-lookup"><span data-stu-id="aea2a-118">Requirements</span></span>  
 <span data-ttu-id="aea2a-119">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aea2a-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea2a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="aea2a-120">See also</span></span>

- [<span data-ttu-id="aea2a-121">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="aea2a-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="aea2a-122">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="aea2a-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
