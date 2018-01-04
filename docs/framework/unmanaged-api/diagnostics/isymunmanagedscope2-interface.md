---
title: "ISymUnmanagedScope2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2
helpviewer_keywords: ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6d2ec846a34b2d3424f7bf8b54f1d4d12d4102e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="d0a1a-102">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="d0a1a-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="d0a1a-103">表示的方法内的词法范围。</span><span class="sxs-lookup"><span data-stu-id="d0a1a-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="d0a1a-104">此接口扩展[ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)使用的方法来获取有关定义的常量的信息的范围内的接口。</span><span class="sxs-lookup"><span data-stu-id="d0a1a-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0a1a-105">方法</span><span class="sxs-lookup"><span data-stu-id="d0a1a-105">Methods</span></span>  
  
|<span data-ttu-id="d0a1a-106">方法</span><span class="sxs-lookup"><span data-stu-id="d0a1a-106">Method</span></span>|<span data-ttu-id="d0a1a-107">描述</span><span class="sxs-lookup"><span data-stu-id="d0a1a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0a1a-108">GetConstantCount 方法</span><span class="sxs-lookup"><span data-stu-id="d0a1a-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="d0a1a-109">获取此范围内定义的常量的计数。</span><span class="sxs-lookup"><span data-stu-id="d0a1a-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="d0a1a-110">GetConstants 方法</span><span class="sxs-lookup"><span data-stu-id="d0a1a-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="d0a1a-111">获取此范围内定义的局部常量。</span><span class="sxs-lookup"><span data-stu-id="d0a1a-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0a1a-112">惠?</span><span class="sxs-lookup"><span data-stu-id="d0a1a-112">Requirements</span></span>  
 <span data-ttu-id="d0a1a-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d0a1a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a1a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0a1a-114">See Also</span></span>  
 [<span data-ttu-id="d0a1a-115">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="d0a1a-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="d0a1a-116">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="d0a1a-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
