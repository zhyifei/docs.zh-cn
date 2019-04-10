---
title: IMetaDataEmit::SetClassLayout 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 80bf9de3eb274bf536b2794ba2ed14e7e9b553cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157698"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="753ab-102">IMetaDataEmit::SetClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="753ab-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="753ab-103">完成已由调用之前定义的类的字段的布局[DefineTypeDef 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="753ab-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="753ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="753ab-104">Syntax</span></span>  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="753ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="753ab-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="753ab-106">[in]`mdTypeDef`标记，用于指定要进行布局的类。</span><span class="sxs-lookup"><span data-stu-id="753ab-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="753ab-107">[in]封装大小：1、 2、 4、 8 或 16 个字节。</span><span class="sxs-lookup"><span data-stu-id="753ab-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="753ab-108">封装大小为相邻的域之间的字节数。</span><span class="sxs-lookup"><span data-stu-id="753ab-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="753ab-109">[in]一个数组[COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)结构，其中每个指定的类的字段和字段的偏移量的类中。</span><span class="sxs-lookup"><span data-stu-id="753ab-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="753ab-110">终止与数组`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="753ab-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="753ab-111">[in]以字节为单位，类的大小。</span><span class="sxs-lookup"><span data-stu-id="753ab-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="753ab-112">备注</span><span class="sxs-lookup"><span data-stu-id="753ab-112">Remarks</span></span>  
 <span data-ttu-id="753ab-113">通过调用最初定义该类[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)方法，并指定三种布局的类的字段之一： 自动、 连续的或显式。</span><span class="sxs-lookup"><span data-stu-id="753ab-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="753ab-114">通常情况下，将使用自动布局，并让运行时选择最佳的方式进行布局的字段。</span><span class="sxs-lookup"><span data-stu-id="753ab-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="753ab-115">但是，您可能希望根据非托管代码使用的排列方式布局的字段。</span><span class="sxs-lookup"><span data-stu-id="753ab-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="753ab-116">在这种情况下，选择连续或显式布局，并调用`SetClassLayout`完成字段的布局：</span><span class="sxs-lookup"><span data-stu-id="753ab-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
-   <span data-ttu-id="753ab-117">顺序布局：指定封装大小。</span><span class="sxs-lookup"><span data-stu-id="753ab-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="753ab-118">字段对齐根据自然大小或包装大小，在较小的偏移量字段的任何结果。</span><span class="sxs-lookup"><span data-stu-id="753ab-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="753ab-119">设置`rFieldOffsets`和`ulClassSize`为零。</span><span class="sxs-lookup"><span data-stu-id="753ab-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
-   <span data-ttu-id="753ab-120">显式布局：指定每个字段的偏移量，或者指定类的大小和封装大小。</span><span class="sxs-lookup"><span data-stu-id="753ab-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="753ab-121">要求</span><span class="sxs-lookup"><span data-stu-id="753ab-121">Requirements</span></span>  
 <span data-ttu-id="753ab-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="753ab-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="753ab-123">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="753ab-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="753ab-124">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="753ab-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="753ab-125">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="753ab-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="753ab-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="753ab-126">See also</span></span>

- [<span data-ttu-id="753ab-127">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="753ab-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="753ab-128">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="753ab-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
