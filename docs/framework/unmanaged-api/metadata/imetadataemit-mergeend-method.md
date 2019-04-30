---
title: IMetaDataEmit::MergeEnd 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 277e7e57ae01128039c3a280158110acde3363a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944542"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="d24e7-102">IMetaDataEmit::MergeEnd 方法</span><span class="sxs-lookup"><span data-stu-id="d24e7-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="d24e7-103">合并到当前作用域指定一个或多个以前调用的所有元数据作用域[imetadataemit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d24e7-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d24e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="d24e7-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
## <a name="parameters"></a><span data-ttu-id="d24e7-105">参数</span><span class="sxs-lookup"><span data-stu-id="d24e7-105">Parameters</span></span>  
 <span data-ttu-id="d24e7-106">此方法需要任何参数。</span><span class="sxs-lookup"><span data-stu-id="d24e7-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d24e7-107">备注</span><span class="sxs-lookup"><span data-stu-id="d24e7-107">Remarks</span></span>  
 <span data-ttu-id="d24e7-108">此例程将触发实际合并的元数据，所有的导入以前调用指定作用域`IMetaDataEmit::Merge`，到当前的输出范围。</span><span class="sxs-lookup"><span data-stu-id="d24e7-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="d24e7-109">以下特殊条件适用于合并：</span><span class="sxs-lookup"><span data-stu-id="d24e7-109">The following special conditions apply to the merge:</span></span>  
  
- <span data-ttu-id="d24e7-110">永远不会导入的模块版本标识符 （mvid） 发生，因为它是唯一的导入作用域中的元数据。</span><span class="sxs-lookup"><span data-stu-id="d24e7-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
- <span data-ttu-id="d24e7-111">将不覆盖任何现有模块范围内的属性。</span><span class="sxs-lookup"><span data-stu-id="d24e7-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="d24e7-112">如果已为当前作用域设置模块属性，导不入任何模块属性。</span><span class="sxs-lookup"><span data-stu-id="d24e7-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="d24e7-113">但是，如果尚未在当前作用域中设置模块属性，它们是导入后仅当其首先出现。</span><span class="sxs-lookup"><span data-stu-id="d24e7-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="d24e7-114">如果再次遇到这些模块属性，它们是重复项。</span><span class="sxs-lookup"><span data-stu-id="d24e7-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="d24e7-115">如果 （除了 mvid） 发生的所有模块属性的值进行比较并且找到了没有重复项，将引发错误。</span><span class="sxs-lookup"><span data-stu-id="d24e7-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
- <span data-ttu-id="d24e7-116">有关类型定义 (`TypeDef`)，没有重复项将合并到当前作用域。</span><span class="sxs-lookup"><span data-stu-id="d24e7-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="d24e7-117">`TypeDef` 检查对象是否已对每个重复项*完全限定对象名称* + *GUID* + *版本号*。</span><span class="sxs-lookup"><span data-stu-id="d24e7-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="d24e7-118">如果没有匹配名称或 GUID，并且任何其他两个元素则不同，将引发错误。</span><span class="sxs-lookup"><span data-stu-id="d24e7-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="d24e7-119">否则为如果所有三个项匹配，`MergeEnd`执行粗略检查以确保这些项确实重复项; 如果没有，将引发错误。</span><span class="sxs-lookup"><span data-stu-id="d24e7-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="d24e7-120">此粗略的检查是查找：</span><span class="sxs-lookup"><span data-stu-id="d24e7-120">This cursory check looks for:</span></span>  
  
    - <span data-ttu-id="d24e7-121">相同的成员声明中的相同顺序出现。</span><span class="sxs-lookup"><span data-stu-id="d24e7-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="d24e7-122">标记为成员`mdPrivateScope`(请参阅[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举) 不包含在此检查; 特别合并。</span><span class="sxs-lookup"><span data-stu-id="d24e7-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    - <span data-ttu-id="d24e7-123">相同的类布局。</span><span class="sxs-lookup"><span data-stu-id="d24e7-123">The same class layout.</span></span>  
  
     <span data-ttu-id="d24e7-124">这意味着，`TypeDef`对象必须始终完全且一致地定义每个元数据范围内声明它; 如果其成员的实现 （类） 分布在多个编译单元中，假定的完整定义为存在于每个范围内，不是增量对每个作用域。</span><span class="sxs-lookup"><span data-stu-id="d24e7-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="d24e7-125">例如，如果参数名称与协定相关，它们必须发出相同的方式引入每个作用域;如果它们不相关，它们不应将发送到元数据。</span><span class="sxs-lookup"><span data-stu-id="d24e7-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="d24e7-126">例外情况是，`TypeDef`对象可以具有标记为增量成员`mdPrivateScope`。</span><span class="sxs-lookup"><span data-stu-id="d24e7-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="d24e7-127">在遇到这些，`MergeEnd`以增量方式将其添加到当前作用域而不考虑重复项。</span><span class="sxs-lookup"><span data-stu-id="d24e7-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="d24e7-128">由于编译器能够识别专用作用域，编译器必须负责强制执行规则。</span><span class="sxs-lookup"><span data-stu-id="d24e7-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
- <span data-ttu-id="d24e7-129">不导入或合并; 相对虚拟地址 (Rva)编译器会重新发出此信息。</span><span class="sxs-lookup"><span data-stu-id="d24e7-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
- <span data-ttu-id="d24e7-130">仅当合并附加到的项时，将合并自定义属性。</span><span class="sxs-lookup"><span data-stu-id="d24e7-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="d24e7-131">例如，当第一次遇到此类合并与类关联的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="d24e7-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="d24e7-132">如果与之关联的自定义特性`TypeDef`或`MemberDef`这就是特定于编译单元 （例如成员编译的时间戳），它们将不会合并，并将由编译器删除或更新此类元数据。</span><span class="sxs-lookup"><span data-stu-id="d24e7-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d24e7-133">要求</span><span class="sxs-lookup"><span data-stu-id="d24e7-133">Requirements</span></span>  
 <span data-ttu-id="d24e7-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d24e7-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d24e7-135">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d24e7-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d24e7-136">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d24e7-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d24e7-137">**.NET Framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d24e7-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d24e7-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="d24e7-138">See also</span></span>

- [<span data-ttu-id="d24e7-139">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="d24e7-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d24e7-140">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="d24e7-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
