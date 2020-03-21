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
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177564"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="8ecfd-102">IMetaDataEmit::SetClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="8ecfd-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="8ecfd-103">完成由之前调用[DefineTypeDef 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)定义的类的字段布局。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ecfd-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ecfd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ecfd-105">parameters</span><span class="sxs-lookup"><span data-stu-id="8ecfd-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="8ecfd-106">[在]指定`mdTypeDef`要布局的类的令牌。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="8ecfd-107">[在]包装尺寸：1、2、4、8 或 16 字节。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="8ecfd-108">包装大小是相邻字段之间的字节数。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="8ecfd-109">[在][COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)结构数组，每个结构指定类的字段和类中的字段偏移量。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="8ecfd-110">使用 终止数组`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="8ecfd-111">[在]类的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ecfd-112">备注</span><span class="sxs-lookup"><span data-stu-id="8ecfd-112">Remarks</span></span>  
 <span data-ttu-id="8ecfd-113">类最初通过调用[IMetaDataEmit：:DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)方法来定义，并为类的字段指定三个布局之一：自动、顺序或显式。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="8ecfd-114">通常，您将使用自动布局，让运行时选择布局字段的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="8ecfd-115">但是，您可能希望根据非托管代码使用的排列方式布局字段。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="8ecfd-116">在这种情况下，选择顺序或显式布局并调用`SetClassLayout`以完成字段的布局：</span><span class="sxs-lookup"><span data-stu-id="8ecfd-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="8ecfd-117">顺序布局：指定包装大小。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="8ecfd-118">字段根据其自然大小或包装大小对齐，以导致字段偏移较小的为准。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="8ecfd-119">设置`rFieldOffsets`和`ulClassSize`零。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="8ecfd-120">显式布局：指定每个字段的偏移量或指定类大小和包装大小。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ecfd-121">要求</span><span class="sxs-lookup"><span data-stu-id="8ecfd-121">Requirements</span></span>  
 <span data-ttu-id="8ecfd-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ecfd-123">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="8ecfd-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ecfd-124">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8ecfd-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ecfd-125">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ecfd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ecfd-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ecfd-126">See also</span></span>

- [<span data-ttu-id="8ecfd-127">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="8ecfd-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8ecfd-128">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="8ecfd-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
