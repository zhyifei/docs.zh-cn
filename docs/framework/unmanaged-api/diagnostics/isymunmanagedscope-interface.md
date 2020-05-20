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
ms.openlocfilehash: 1ee406c97fa4ccb7f87098cba2925568d8ce069f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615340"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="e6d59-102">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="e6d59-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="e6d59-103">表示方法中的词法范围。</span><span class="sxs-lookup"><span data-stu-id="e6d59-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6d59-104">方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-104">Methods</span></span>  
  
|<span data-ttu-id="e6d59-105">方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-105">Method</span></span>|<span data-ttu-id="e6d59-106">说明</span><span class="sxs-lookup"><span data-stu-id="e6d59-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6d59-107">GetChildren 方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-107">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="e6d59-108">获取此作用域的子级。</span><span class="sxs-lookup"><span data-stu-id="e6d59-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="e6d59-109">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-109">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="e6d59-110">获取此范围的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="e6d59-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="e6d59-111">GetLocalCount 方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-111">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="e6d59-112">获取在此范围内定义的局部变量的计数。</span><span class="sxs-lookup"><span data-stu-id="e6d59-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="e6d59-113">GetLocals 方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-113">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="e6d59-114">获取在此范围内定义的局部变量。</span><span class="sxs-lookup"><span data-stu-id="e6d59-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="e6d59-115">GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-115">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="e6d59-116">获取包含此范围的方法。</span><span class="sxs-lookup"><span data-stu-id="e6d59-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="e6d59-117">GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-117">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="e6d59-118">获取正在此范围内使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e6d59-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="e6d59-119">GetParent 方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-119">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="e6d59-120">获取此范围的父范围。</span><span class="sxs-lookup"><span data-stu-id="e6d59-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="e6d59-121">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="e6d59-121">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="e6d59-122">获取此范围的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="e6d59-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6d59-123">要求</span><span class="sxs-lookup"><span data-stu-id="e6d59-123">Requirements</span></span>  
 <span data-ttu-id="e6d59-124">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e6d59-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d59-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6d59-125">See also</span></span>

- [<span data-ttu-id="e6d59-126">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="e6d59-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e6d59-127">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="e6d59-127">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
