---
title: "IMetaDataEmit::MergeEnd 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 265fc007b5817e8dffd5846738a7a0003bbddf9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="a9bf9-102">IMetaDataEmit::MergeEnd 方法</span><span class="sxs-lookup"><span data-stu-id="a9bf9-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="a9bf9-103">合并到当前作用域指定一个或多个之前调用的所有元数据作用域[imetadataemit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9bf9-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9bf9-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9bf9-105">参数</span><span class="sxs-lookup"><span data-stu-id="a9bf9-105">Parameters</span></span>  
 <span data-ttu-id="a9bf9-106">此方法采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9bf9-107">备注</span><span class="sxs-lookup"><span data-stu-id="a9bf9-107">Remarks</span></span>  
 <span data-ttu-id="a9bf9-108">此例程会触发实际合并元数据，所有导入以前调用指定作用域`IMetaDataEmit::Merge`，纳入当前输出范围。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="a9bf9-109">以下特殊情况适用于合并：</span><span class="sxs-lookup"><span data-stu-id="a9bf9-109">The following special conditions apply to the merge:</span></span>  
  
-   <span data-ttu-id="a9bf9-110">模块版本标识符 (MVID) 永远不会导入，因为它是唯一的导入作用域中的元数据。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
-   <span data-ttu-id="a9bf9-111">没有现有的模块级属性将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="a9bf9-112">如果模块的属性已设置为当前作用域，导不入任何模块的属性。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="a9bf9-113">但是，如果模块的属性不在当前范围内已设置，它们是导入后仅当它们首次遇到。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="a9bf9-114">如果再次遇到这些模块的属性，它们是重复项。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="a9bf9-115">如果 （MVID 除外） 的所有模块属性的值进行比较，并且没有重复项位于，将引发错误。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
-   <span data-ttu-id="a9bf9-116">对于类型定义 (`TypeDef`)，没有重复项将合并到当前作用域。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="a9bf9-117">`TypeDef`针对每个重复项来检查对象*完全限定对象名称* + *GUID* + *版本号*。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="a9bf9-118">如果没有匹配名称或 GUID，并且任何其他两个元素是不同，将引发错误。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="a9bf9-119">否则为如果所有三个项匹配，`MergeEnd`执行粗略检查以确保这些项确实重复项; 否则，将引发错误。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="a9bf9-120">此粗略检查将查找：</span><span class="sxs-lookup"><span data-stu-id="a9bf9-120">This cursory check looks for:</span></span>  
  
    -   <span data-ttu-id="a9bf9-121">相同的成员声明中的相同顺序出现。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="a9bf9-122">成员标记为`mdPrivateScope`(请参阅[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举) 中此检查; 不包括特殊合并。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    -   <span data-ttu-id="a9bf9-123">相同的类布局。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-123">The same class layout.</span></span>  
  
     <span data-ttu-id="a9bf9-124">这意味着，`TypeDef`对象必须始终完全且一致地定义每个元数据范围内声明它; 如果其成员的实现 （为类） 分布在多个编译单元中，假定完整定义为存在于每个范围内，不是增量到每个作用域。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="a9bf9-125">例如，如果与协定相关参数名称，它们必须发出相同的方式到每个作用域;如果它们不是相关的它们不应将发送到元数据。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="a9bf9-126">例外情况是，`TypeDef`对象可以拥有增量成员标记为`mdPrivateScope`。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="a9bf9-127">在遇到这些`MergeEnd`以增量方式将它们添加到当前范围中不考虑重复项。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="a9bf9-128">因为编译器理解的专用的作用域，因此编译器必须负责强制执行规则。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
-   <span data-ttu-id="a9bf9-129">不导入或合并; 相对虚拟地址 (Rva)编译器需要重新发送此信息。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
-   <span data-ttu-id="a9bf9-130">自定义特性，仅当合并合并附加到的项。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="a9bf9-131">例如，当第一次遇到类合并与类相关联的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="a9bf9-132">如果与之关联的自定义特性`TypeDef`或`MemberDef`特定于编译单元 （例如成员编译的时间戳），它们将不会合并，并将由编译器删除或更新此类元数据。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9bf9-133">惠?</span><span class="sxs-lookup"><span data-stu-id="a9bf9-133">Requirements</span></span>  
 <span data-ttu-id="a9bf9-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9bf9-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9bf9-135">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9bf9-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9bf9-136">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a9bf9-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9bf9-137">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9bf9-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9bf9-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9bf9-138">See Also</span></span>  
 [<span data-ttu-id="a9bf9-139">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="a9bf9-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a9bf9-140">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="a9bf9-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
