---
title: ISymUnmanagedScope 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 8da4da38d23ed65a0fdc44a0f919ee8cad2fe18e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446261"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="223e2-102">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="223e2-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="223e2-103">表示方法中的词法范围。</span><span class="sxs-lookup"><span data-stu-id="223e2-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="223e2-104">方法</span><span class="sxs-lookup"><span data-stu-id="223e2-104">Methods</span></span>  
  
|<span data-ttu-id="223e2-105">方法</span><span class="sxs-lookup"><span data-stu-id="223e2-105">Method</span></span>|<span data-ttu-id="223e2-106">说明</span><span class="sxs-lookup"><span data-stu-id="223e2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="223e2-107">GetChildren 方法</span><span class="sxs-lookup"><span data-stu-id="223e2-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="223e2-108">获取此作用域的子级。</span><span class="sxs-lookup"><span data-stu-id="223e2-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="223e2-109">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="223e2-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="223e2-110">获取此范围的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="223e2-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="223e2-111">GetLocalCount 方法</span><span class="sxs-lookup"><span data-stu-id="223e2-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="223e2-112">获取在此范围内定义的局部变量的计数。</span><span class="sxs-lookup"><span data-stu-id="223e2-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="223e2-113">GetLocals 方法</span><span class="sxs-lookup"><span data-stu-id="223e2-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="223e2-114">获取在此范围内定义的局部变量。</span><span class="sxs-lookup"><span data-stu-id="223e2-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="223e2-115">GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="223e2-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="223e2-116">获取包含此范围的方法。</span><span class="sxs-lookup"><span data-stu-id="223e2-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="223e2-117">GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="223e2-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="223e2-118">获取正在此范围内使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="223e2-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="223e2-119">GetParent 方法</span><span class="sxs-lookup"><span data-stu-id="223e2-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="223e2-120">获取此范围的父范围。</span><span class="sxs-lookup"><span data-stu-id="223e2-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="223e2-121">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="223e2-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="223e2-122">获取此范围的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="223e2-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="223e2-123">要求</span><span class="sxs-lookup"><span data-stu-id="223e2-123">Requirements</span></span>  
 <span data-ttu-id="223e2-124">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="223e2-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223e2-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="223e2-125">See also</span></span>

- [<span data-ttu-id="223e2-126">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="223e2-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="223e2-127">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="223e2-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
