---
title: ISymUnmanagedMethod 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 1d3ccb2265f056d5776199d997dc067c8d5513e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448787"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="1a3fa-102">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="1a3fa-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="1a3fa-103">表示符号存储区中的方法。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="1a3fa-104">此接口仅提供对方法的符号相关属性的访问，而不提供与类型相关的属性的访问。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a3fa-105">方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-105">Methods</span></span>  
  
|<span data-ttu-id="1a3fa-106">方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-106">Method</span></span>|<span data-ttu-id="1a3fa-107">说明</span><span class="sxs-lookup"><span data-stu-id="1a3fa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a3fa-108">GetNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="1a3fa-109">获取在其中定义此方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="1a3fa-110">GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="1a3fa-111">返回此方法内的偏移量，该偏移量对应于文档中的给定位置。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="1a3fa-112">GetParameters 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="1a3fa-113">获取此方法的参数。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="1a3fa-114">GetRanges 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="1a3fa-115">给定文档中的某个位置后，将返回与该位置涵盖在此方法中的 Microsoft 中间语言（MSIL）范围对应的起始和结束偏移量对的数组。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="1a3fa-116">GetRootScope 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="1a3fa-117">获取此方法内的根词法范围。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="1a3fa-118">此范围包括整个方法。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="1a3fa-119">GetScopeFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="1a3fa-120">获取此方法内包含给定偏移量的最封闭的词法范围。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="1a3fa-121">GetSequencePointCount 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="1a3fa-122">获取此方法中序列点的计数。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="1a3fa-123">GetSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="1a3fa-124">获取此方法中的所有序列点。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="1a3fa-125">GetSourceStartEnd 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="1a3fa-126">获取此方法的源的起始和结束文档位置。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="1a3fa-127">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="1a3fa-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="1a3fa-128">返回此方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1a3fa-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a3fa-129">要求</span><span class="sxs-lookup"><span data-stu-id="1a3fa-129">Requirements</span></span>  
 <span data-ttu-id="1a3fa-130">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="1a3fa-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a3fa-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a3fa-131">See also</span></span>

- [<span data-ttu-id="1a3fa-132">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="1a3fa-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
