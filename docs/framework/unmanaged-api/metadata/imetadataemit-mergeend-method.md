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
ms.openlocfilehash: 34ecfc2f01f22971e135358806adeea632e02f8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448036"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="4f0f2-102">IMetaDataEmit::MergeEnd 方法</span><span class="sxs-lookup"><span data-stu-id="4f0f2-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="4f0f2-103">合并到当前作用域中由一个或多个之前调用[IMetaDataEmit：： Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)指定的元数据作用域。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="4f0f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f0f2-104">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="4f0f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="4f0f2-105">Parameters</span></span>

<span data-ttu-id="4f0f2-106">此方法不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f0f2-107">备注</span><span class="sxs-lookup"><span data-stu-id="4f0f2-107">Remarks</span></span>

<span data-ttu-id="4f0f2-108">此例程触发元数据的实际合并，这些元数据由前面对 `IMetaDataEmit::Merge`的调用指定的所有导入范围合并到当前输出范围内。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="4f0f2-109">以下特殊条件适用于合并：</span><span class="sxs-lookup"><span data-stu-id="4f0f2-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="4f0f2-110">永远不会导入模块版本标识符（MVID），因为它对于导入范围内的元数据是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="4f0f2-111">不会覆盖现有的模块范围的属性。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="4f0f2-112">如果已为当前作用域设置了模块属性，则不会导入任何模块属性。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="4f0f2-113">但是，如果未在当前范围中设置模块属性，则在第一次遇到时，它们只会导入一次。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="4f0f2-114">如果再次遇到这些模块属性，则它们是重复的。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="4f0f2-115">如果比较所有模块属性（MVID 除外）的值，并且找不到重复项，则会引发错误。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="4f0f2-116">对于类型定义（`TypeDef`），无重复项合并到当前作用域中。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="4f0f2-117">针对每个*完全限定的对象名称* + *GUID* + *版本号*检查 `TypeDef` 对象是否存在重复项。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="4f0f2-118">如果名称或 GUID 上存在匹配项，并且其他两个元素不同，则会引发错误。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="4f0f2-119">否则，如果所有三个项均匹配，`MergeEnd` 将粗略检查以确保条目确实重复;如果不是，则会引发错误。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="4f0f2-120">此粗略检查查找：</span><span class="sxs-lookup"><span data-stu-id="4f0f2-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="4f0f2-121">相同的成员声明，按相同顺序发生。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="4f0f2-122">标记为 `mdPrivateScope` 的成员（请参阅[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举）未包含在此检查中;它们是专门合并的。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="4f0f2-123">相同的类布局。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-123">The same class layout.</span></span>

  <span data-ttu-id="4f0f2-124">这意味着 `TypeDef` 对象必须始终在声明它的每个元数据范围内完全一致地定义;如果其成员实现（对于某个类）分布在多个编译单元中，则假定该完整定义存在于每个作用域中，而不是增量分配给每个作用域。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="4f0f2-125">例如，如果参数名称与协定相关，则必须在每个范围中以相同方式发出它们;如果不相关，则不应将其发送到元数据中。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="4f0f2-126">例外情况是 `TypeDef` 对象可以具有标记为 `mdPrivateScope`的增量成员。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="4f0f2-127">如果遇到这些问题，`MergeEnd` 将以增量方式将它们添加到当前作用域，而不考虑重复项。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="4f0f2-128">由于编译器理解专用范围，因此编译器必须负责强制执行规则。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="4f0f2-129">相对虚拟地址（Rva）不会导入或合并;编译器应重新发出此信息。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="4f0f2-130">自定义特性仅在其附加到的项合并时进行合并。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="4f0f2-131">例如，当第一次遇到类时，将合并与类关联的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="4f0f2-132">如果自定义属性与特定于编译单元的 `TypeDef` 或 `MemberDef` （如成员编译的时间戳）关联，则不会合并这些属性，而是由编译器删除或更新此类元数据。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="4f0f2-133">要求</span><span class="sxs-lookup"><span data-stu-id="4f0f2-133">Requirements</span></span>

<span data-ttu-id="4f0f2-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f0f2-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="4f0f2-135">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="4f0f2-135">**Header:** Cor.h</span></span>

<span data-ttu-id="4f0f2-136">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4f0f2-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="4f0f2-137">**.NET Framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f0f2-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4f0f2-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f0f2-138">See also</span></span>

- [<span data-ttu-id="4f0f2-139">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="4f0f2-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4f0f2-140">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="4f0f2-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
