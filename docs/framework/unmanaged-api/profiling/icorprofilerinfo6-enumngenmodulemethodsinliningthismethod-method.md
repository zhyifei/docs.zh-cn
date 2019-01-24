---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07b1c905e587708336ce690bbf3d187b2d21e5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568148"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="12706-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法</span><span class="sxs-lookup"><span data-stu-id="12706-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>
<span data-ttu-id="12706-103">[.NET Framework 4.6 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="12706-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="12706-104">为给定的 NGen 模块和内联给定方法中定义的所有方法返回一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="12706-104">Returns an enumerator to all the methods that          are defined in  a given NGen module and          inline a given method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12706-105">语法</span><span class="sxs-lookup"><span data-stu-id="12706-105">Syntax</span></span>  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12706-106">参数</span><span class="sxs-lookup"><span data-stu-id="12706-106">Parameters</span></span>  
 `inlinersModuleId`  
 <span data-ttu-id="12706-107">[in]NGen 模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="12706-107">[in] The identifier of an NGen module.</span></span>  
  
 `inlineeModuleId`  
 <span data-ttu-id="12706-108">[in]定义的模块标识符`inlineeMethodId`。</span><span class="sxs-lookup"><span data-stu-id="12706-108">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="12706-109">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="12706-109">See the Remarks section for more information.</span></span>  
  
 `inlineeMethodId`  
 <span data-ttu-id="12706-110">[in]内联方法的标识符。</span><span class="sxs-lookup"><span data-stu-id="12706-110">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="12706-111">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="12706-111">See the Remarks section for more information.</span></span>  
  
 `incompleteData`  
 <span data-ttu-id="12706-112">[out]一个标志，指示是否`ppEnum`包含给定的方法的内联的所有方法。</span><span class="sxs-lookup"><span data-stu-id="12706-112">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="12706-113">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="12706-113">See the Remarks section for more information.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="12706-114">[out]一个指向枚举器的地址</span><span class="sxs-lookup"><span data-stu-id="12706-114">[out] A pointer to the address of an enumerator</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12706-115">备注</span><span class="sxs-lookup"><span data-stu-id="12706-115">Remarks</span></span>  
 <span data-ttu-id="12706-116">`inlineeModuleId` 和`inlineeMethodId`一起构成了可能会进行内联方法的完整标识符。</span><span class="sxs-lookup"><span data-stu-id="12706-116">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="12706-117">例如，假定模块`A`定义的方法`Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="12706-117">For example, assume module `A` defines a method `Simple.Add`:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 <span data-ttu-id="12706-118">和模块 Bdefines `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="12706-118">and module Bdefines `Fancy.AddTwice`:</span></span>  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 <span data-ttu-id="12706-119">允许并假设`Fancy.AddTwice`内嵌元素调用到`SimpleAdd`。</span><span class="sxs-lookup"><span data-stu-id="12706-119">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="12706-120">探查器可以使用此枚举器来查找模块 B 中哪些以内联方式定义的所有方法`Simple.Add`，并枚举结果会`AddTwice`。</span><span class="sxs-lookup"><span data-stu-id="12706-120">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="12706-121">`inlineeModuleId` 是的模块标识符`A`，并`inlineeeMethodId`是标识符`Simple.Add(int a, int b)`。</span><span class="sxs-lookup"><span data-stu-id="12706-121">`inlineeModuleId` is the identifier of module `A`,   and `inlineeeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>  
  
 <span data-ttu-id="12706-122">如果`incompleteData`函数的后面是 true，将返回枚举器不包含内联的所有方法的给定的方法。</span><span class="sxs-lookup"><span data-stu-id="12706-122">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="12706-123">这可能会在一个或多直接或间接依赖关系的内联模块尚未尚未加载。</span><span class="sxs-lookup"><span data-stu-id="12706-123">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="12706-124">如果探查器需要准确的数据，它应稍后重试多个模块加载时，最好是在每个模块加载。</span><span class="sxs-lookup"><span data-stu-id="12706-124">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>  
  
 <span data-ttu-id="12706-125">`EnumNgenModuleMethodsInliningThisMethod`方法可用于解决限制为 ReJIT 内联。</span><span class="sxs-lookup"><span data-stu-id="12706-125">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="12706-126">ReJIT 允许探查器更改方法的实现，然后动态为其创建新的代码。</span><span class="sxs-lookup"><span data-stu-id="12706-126">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="12706-127">例如，我们可能会更改`Simple.Add`，如下所示：</span><span class="sxs-lookup"><span data-stu-id="12706-127">For example, we could change `Simple.Add` as follows:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 <span data-ttu-id="12706-128">但是由于`Fancy.AddTwice`具有已内联`Simple.Add`，它将继续像以前一样具有相同的行为。</span><span class="sxs-lookup"><span data-stu-id="12706-128">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="12706-129">若要解决这一限制，调用方必须搜索所有方法的所有模块中内联`Simple.Add`，并使用`ICorProfilerInfo5::RequestRejit`上的每个这些方法。</span><span class="sxs-lookup"><span data-stu-id="12706-129">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="12706-130">重新编译方法时，它们将具有新行为的`Simple.Add`而不是这一旧行为。</span><span class="sxs-lookup"><span data-stu-id="12706-130">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12706-131">要求</span><span class="sxs-lookup"><span data-stu-id="12706-131">Requirements</span></span>  
 <span data-ttu-id="12706-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12706-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12706-133">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12706-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12706-134">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12706-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12706-135">**.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12706-135">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12706-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="12706-136">See also</span></span>
- [<span data-ttu-id="12706-137">ICorProfilerInfo6 接口</span><span class="sxs-lookup"><span data-stu-id="12706-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
