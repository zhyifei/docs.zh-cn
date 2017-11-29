---
title: "ISymUnmanagedScope 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope
helpviewer_keywords: ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d25d62dd42e3e93124c9a3bd8945be265f192663
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="0435d-102">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="0435d-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="0435d-103">表示的方法内的词法范围。</span><span class="sxs-lookup"><span data-stu-id="0435d-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0435d-104">方法</span><span class="sxs-lookup"><span data-stu-id="0435d-104">Methods</span></span>  
  
|<span data-ttu-id="0435d-105">方法</span><span class="sxs-lookup"><span data-stu-id="0435d-105">Method</span></span>|<span data-ttu-id="0435d-106">描述</span><span class="sxs-lookup"><span data-stu-id="0435d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0435d-107">GetChildren 方法</span><span class="sxs-lookup"><span data-stu-id="0435d-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="0435d-108">获取此作用域的子级。</span><span class="sxs-lookup"><span data-stu-id="0435d-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="0435d-109">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="0435d-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="0435d-110">获取此范围的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="0435d-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="0435d-111">GetLocalCount 方法</span><span class="sxs-lookup"><span data-stu-id="0435d-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="0435d-112">获取此范围内定义的本地变量的计数。</span><span class="sxs-lookup"><span data-stu-id="0435d-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="0435d-113">GetLocals 方法</span><span class="sxs-lookup"><span data-stu-id="0435d-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="0435d-114">获取此范围内定义的本地变量。</span><span class="sxs-lookup"><span data-stu-id="0435d-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="0435d-115">GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="0435d-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="0435d-116">获取包含此作用域的方法。</span><span class="sxs-lookup"><span data-stu-id="0435d-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="0435d-117">GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="0435d-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="0435d-118">获取在此作用域中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="0435d-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="0435d-119">GetParent 方法</span><span class="sxs-lookup"><span data-stu-id="0435d-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="0435d-120">获取此作用域的父作用域。</span><span class="sxs-lookup"><span data-stu-id="0435d-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="0435d-121">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="0435d-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="0435d-122">获取此范围的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="0435d-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0435d-123">要求</span><span class="sxs-lookup"><span data-stu-id="0435d-123">Requirements</span></span>  
 <span data-ttu-id="0435d-124">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0435d-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0435d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0435d-125">See Also</span></span>  
 [<span data-ttu-id="0435d-126">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="0435d-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="0435d-127">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="0435d-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
