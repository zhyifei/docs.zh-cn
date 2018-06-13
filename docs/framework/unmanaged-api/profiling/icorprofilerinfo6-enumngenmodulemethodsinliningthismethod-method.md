---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 564f3b1cdfab2a3020b6bb5ac8d9af03c6532c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459666"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="3f53e-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法</span><span class="sxs-lookup"><span data-stu-id="3f53e-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>
<span data-ttu-id="3f53e-103">[在.NET Framework 4.6 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="3f53e-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="3f53e-104">返回到给定的 NGen 模块和内联给定方法中定义的所有方法的枚举。</span><span class="sxs-lookup"><span data-stu-id="3f53e-104">Returns an enumerator to all the methods that          are defined in  a given NGen module and          inline a given method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f53e-105">语法</span><span class="sxs-lookup"><span data-stu-id="3f53e-105">Syntax</span></span>  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f53e-106">参数</span><span class="sxs-lookup"><span data-stu-id="3f53e-106">Parameters</span></span>  
 `inlinersModuleId`  
 <span data-ttu-id="3f53e-107">[in]NGen 模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="3f53e-107">[in] The identifier of an NGen module.</span></span>  
  
 `inlineeModuleId`  
 <span data-ttu-id="3f53e-108">[in]定义模块的标识符`inlineeMethodId`。</span><span class="sxs-lookup"><span data-stu-id="3f53e-108">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="3f53e-109">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="3f53e-109">See the Remarks section for more information.</span></span>  
  
 `inlineeMethodId`  
 <span data-ttu-id="3f53e-110">[in]内联方法的标识符。</span><span class="sxs-lookup"><span data-stu-id="3f53e-110">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="3f53e-111">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="3f53e-111">See the Remarks section for more information.</span></span>  
  
 `incompleteData`  
 <span data-ttu-id="3f53e-112">[out]一个标志，指示是否`ppEnum`包含给定的方法的所有内联的方法。</span><span class="sxs-lookup"><span data-stu-id="3f53e-112">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="3f53e-113">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="3f53e-113">See the Remarks section for more information.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="3f53e-114">[out]枚举器的地址指针</span><span class="sxs-lookup"><span data-stu-id="3f53e-114">[out] A pointer to the address of an enumerator</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f53e-115">备注</span><span class="sxs-lookup"><span data-stu-id="3f53e-115">Remarks</span></span>  
 <span data-ttu-id="3f53e-116">`inlineeModuleId` 和`inlineeMethodId`一起构成了可能是内联的方法的完整标识符。</span><span class="sxs-lookup"><span data-stu-id="3f53e-116">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="3f53e-117">例如，假定模块`A`定义的方法`Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="3f53e-117">For example, assume module `A` defines a method `Simple.Add`:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 <span data-ttu-id="3f53e-118">和模块 Bdefines `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="3f53e-118">and module Bdefines `Fancy.AddTwice`:</span></span>  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 <span data-ttu-id="3f53e-119">允许还假定`Fancy.AddTwice`内联调用到`SimpleAdd`。</span><span class="sxs-lookup"><span data-stu-id="3f53e-119">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="3f53e-120">探查器可以使用此枚举器查找模块 B 中哪些以内联方式定义的所有方法`Simple.Add`，结果将枚举和`AddTwice`。</span><span class="sxs-lookup"><span data-stu-id="3f53e-120">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="3f53e-121">`inlineeModuleId` 是模块的标识符`A`，和`inlineeeMethodId`是标识符`Simple.Add(int a, int b)`。</span><span class="sxs-lookup"><span data-stu-id="3f53e-121">`inlineeModuleId` is the identifier of module `A`,   and `inlineeeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>  
  
 <span data-ttu-id="3f53e-122">如果`incompleteData`true 后该函数返回时，枚举数不包含内联的所有方法的给定的方法。</span><span class="sxs-lookup"><span data-stu-id="3f53e-122">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="3f53e-123">这可能会在一个或多直接或间接依赖关系的内联模块尚未尚未加载。</span><span class="sxs-lookup"><span data-stu-id="3f53e-123">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="3f53e-124">如果探查器需要准确的数据，它应稍后重试更多模块加载后，最好是在每个模块加载。</span><span class="sxs-lookup"><span data-stu-id="3f53e-124">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>  
  
 <span data-ttu-id="3f53e-125">`EnumNgenModuleMethodsInliningThisMethod`方法可以用于解决上的限制为 ReJIT 内联。</span><span class="sxs-lookup"><span data-stu-id="3f53e-125">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="3f53e-126">ReJIT 允许探查器更改方法的实现，然后动态为它创建新的代码。</span><span class="sxs-lookup"><span data-stu-id="3f53e-126">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="3f53e-127">例如，我们无法更改`Simple.Add`，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3f53e-127">For example, we could change `Simple.Add` as follows:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 <span data-ttu-id="3f53e-128">但是因为`Fancy.AddTwice`具有已内联`Simple.Add`，它将继续像以前那样具有相同的行为。</span><span class="sxs-lookup"><span data-stu-id="3f53e-128">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="3f53e-129">若要解决这种限制，调用方具有在其中进行搜索的所有方法的所有模块中内联`Simple.Add`并用`ICorProfilerInfo5::RequestRejit`上的每个这些方法。</span><span class="sxs-lookup"><span data-stu-id="3f53e-129">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="3f53e-130">重新编译方法时，它们将具有新的行为`Simple.Add`而不是这一旧行为。</span><span class="sxs-lookup"><span data-stu-id="3f53e-130">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f53e-131">要求</span><span class="sxs-lookup"><span data-stu-id="3f53e-131">Requirements</span></span>  
 <span data-ttu-id="3f53e-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f53e-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f53e-133">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f53e-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f53e-134">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f53e-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f53e-135">**.NET framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f53e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f53e-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f53e-136">See Also</span></span>  
 [<span data-ttu-id="3f53e-137">ICorProfilerInfo6 接口</span><span class="sxs-lookup"><span data-stu-id="3f53e-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
