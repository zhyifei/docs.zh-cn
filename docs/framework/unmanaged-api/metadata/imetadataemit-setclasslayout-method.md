---
title: "IMetaDataEmit::SetClassLayout 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a68d94cbea408bee90b117965f83f760ba7ea5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="d399d-102">IMetaDataEmit::SetClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="d399d-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="d399d-103">完成已由调用定义的类的字段的布局[DefineTypeDef 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d399d-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d399d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d399d-104">Syntax</span></span>  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d399d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d399d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d399d-106">[in]`mdTypeDef`标记，用于指定要进行布局的类。</span><span class="sxs-lookup"><span data-stu-id="d399d-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="d399d-107">[in]包装大小： 1、 2、 4、 8 或 16 字节。</span><span class="sxs-lookup"><span data-stu-id="d399d-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="d399d-108">封装大小为相邻字段之间的字节数。</span><span class="sxs-lookup"><span data-stu-id="d399d-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="d399d-109">[in]数组[COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)结构，其中每个指定类的字段和字段的偏移量在类中。</span><span class="sxs-lookup"><span data-stu-id="d399d-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="d399d-110">终止与数组`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="d399d-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="d399d-111">[in]以字节为单位，类的大小。</span><span class="sxs-lookup"><span data-stu-id="d399d-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d399d-112">备注</span><span class="sxs-lookup"><span data-stu-id="d399d-112">Remarks</span></span>  
 <span data-ttu-id="d399d-113">通过调用最初定义类[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)方法，并指定三种布局的类的字段之一： 自动、 顺序，或显式。</span><span class="sxs-lookup"><span data-stu-id="d399d-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="d399d-114">通常情况下，将使用自动布局，并让运行时选择字段的布局的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="d399d-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="d399d-115">但是，你可能想根据非托管代码使用的排列方式进行布局的字段。</span><span class="sxs-lookup"><span data-stu-id="d399d-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="d399d-116">在这种情况下，选择连续或显式布局，并调用`SetClassLayout`完成字段的布局：</span><span class="sxs-lookup"><span data-stu-id="d399d-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
-   <span data-ttu-id="d399d-117">顺序布局： 指定的包装大小。</span><span class="sxs-lookup"><span data-stu-id="d399d-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="d399d-118">根据其原始大小或包装大小，无论结果的较小的偏移量的字段对齐字段。</span><span class="sxs-lookup"><span data-stu-id="d399d-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="d399d-119">设置`rFieldOffsets`和`ulClassSize`为零。</span><span class="sxs-lookup"><span data-stu-id="d399d-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
-   <span data-ttu-id="d399d-120">显式布局： 指定每个字段的偏移量，或者指定类大小和封装大小。</span><span class="sxs-lookup"><span data-stu-id="d399d-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d399d-121">要求</span><span class="sxs-lookup"><span data-stu-id="d399d-121">Requirements</span></span>  
 <span data-ttu-id="d399d-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d399d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d399d-123">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d399d-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d399d-124">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d399d-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d399d-125">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d399d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d399d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d399d-126">See Also</span></span>  
 [<span data-ttu-id="d399d-127">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="d399d-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="d399d-128">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="d399d-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
