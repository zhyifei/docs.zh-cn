---
title: "ISymUnmanagedMethod 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod
helpviewer_keywords: ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6305625c3d02dbd126a284287e19b319e21eeba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="b2b51-102">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="b2b51-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="b2b51-103">表示符号存储区内的方法。</span><span class="sxs-lookup"><span data-stu-id="b2b51-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="b2b51-104">此接口提供的一种方法，而不是与类型相关的属性仅与符号相关的属性的访问。</span><span class="sxs-lookup"><span data-stu-id="b2b51-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2b51-105">方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-105">Methods</span></span>  
  
|<span data-ttu-id="b2b51-106">方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-106">Method</span></span>|<span data-ttu-id="b2b51-107">描述</span><span class="sxs-lookup"><span data-stu-id="b2b51-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2b51-108">GetNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="b2b51-109">获取在其中定义此方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b2b51-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="b2b51-110">GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="b2b51-111">返回到文档内的给定位置在此方法的相对应的偏移量。</span><span class="sxs-lookup"><span data-stu-id="b2b51-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="b2b51-112">GetParameters 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="b2b51-113">获取此方法的参数。</span><span class="sxs-lookup"><span data-stu-id="b2b51-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="b2b51-114">GetRanges 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="b2b51-115">给定文档中的一个位置，返回到的 Microsoft 中间语言 (MSIL) 的位置在此方法内包括的范围对应的开始和结束偏移量对的数组。</span><span class="sxs-lookup"><span data-stu-id="b2b51-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="b2b51-116">GetRootScope 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="b2b51-117">获取在此方法内的根词法范围。</span><span class="sxs-lookup"><span data-stu-id="b2b51-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="b2b51-118">此范围包括整个方法。</span><span class="sxs-lookup"><span data-stu-id="b2b51-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="b2b51-119">GetScopeFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="b2b51-120">获取在此方法包含给定的偏移量内最封闭的词法范围。</span><span class="sxs-lookup"><span data-stu-id="b2b51-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="b2b51-121">GetSequencePointCount 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="b2b51-122">获取在此方法内的序列点的计数。</span><span class="sxs-lookup"><span data-stu-id="b2b51-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="b2b51-123">GetSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="b2b51-124">获取在此方法内的所有序列点。</span><span class="sxs-lookup"><span data-stu-id="b2b51-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="b2b51-125">GetSourceStartEnd 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="b2b51-126">获取此方法的源的开始和结束文档位置。</span><span class="sxs-lookup"><span data-stu-id="b2b51-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="b2b51-127">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="b2b51-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="b2b51-128">返回此方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="b2b51-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2b51-129">惠?</span><span class="sxs-lookup"><span data-stu-id="b2b51-129">Requirements</span></span>  
 <span data-ttu-id="b2b51-130">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b2b51-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b51-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2b51-131">See Also</span></span>  
 [<span data-ttu-id="b2b51-132">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="b2b51-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
