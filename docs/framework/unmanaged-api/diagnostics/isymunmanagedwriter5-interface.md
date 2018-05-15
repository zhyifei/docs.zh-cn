---
title: ISymUnmanagedWriter5 接口
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5fd7c2bd4fae94d1ef5021b558a04b734803b68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="72c17-102">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="72c17-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="72c17-103">ISymUnmanagedWriter5 接口。</span><span class="sxs-lookup"><span data-stu-id="72c17-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c17-104">语法</span><span class="sxs-lookup"><span data-stu-id="72c17-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="72c17-105">方法</span><span class="sxs-lookup"><span data-stu-id="72c17-105">Methods</span></span>  
 <span data-ttu-id="72c17-106">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="72c17-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="72c17-107">方法</span><span class="sxs-lookup"><span data-stu-id="72c17-107">Method</span></span>|<span data-ttu-id="72c17-108">描述</span><span class="sxs-lookup"><span data-stu-id="72c17-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72c17-109">CloseMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="72c17-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="72c17-110">关闭映射信息的令牌源范围的特殊的自定义数据部分。</span><span class="sxs-lookup"><span data-stu-id="72c17-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="72c17-111">关闭后，可以不添加任何更多的映射信息。</span><span class="sxs-lookup"><span data-stu-id="72c17-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="72c17-112">MapTokenToSourceSpan 方法</span><span class="sxs-lookup"><span data-stu-id="72c17-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="72c17-113">在指定的源文件中映射到给定的源行的给定元数据标记的分布。</span><span class="sxs-lookup"><span data-stu-id="72c17-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="72c17-114">必须调用之间调用[OpenMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)和[CloseMapTokensToSourceSpans 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)。</span><span class="sxs-lookup"><span data-stu-id="72c17-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="72c17-115">OpenMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="72c17-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="72c17-116">打开一个特殊的自定义数据部分，以便发出令牌源范围映射到的信息。</span><span class="sxs-lookup"><span data-stu-id="72c17-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="72c17-117">方法已打开，或反之，是一个错误时，请打开此部分。</span><span class="sxs-lookup"><span data-stu-id="72c17-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72c17-118">要求</span><span class="sxs-lookup"><span data-stu-id="72c17-118">Requirements</span></span>  
 <span data-ttu-id="72c17-119">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="72c17-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c17-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="72c17-120">See Also</span></span>  
 [<span data-ttu-id="72c17-121">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="72c17-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="72c17-122">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="72c17-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
