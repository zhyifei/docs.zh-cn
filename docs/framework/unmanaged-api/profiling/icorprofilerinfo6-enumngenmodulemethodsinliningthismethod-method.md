---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130375"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="6f216-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法</span><span class="sxs-lookup"><span data-stu-id="6f216-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="6f216-103">返回一个枚举器，该枚举器指向给定的 NGen 模块中定义的所有方法，并内联给定方法。</span><span class="sxs-lookup"><span data-stu-id="6f216-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f216-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f216-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="6f216-105">参数</span><span class="sxs-lookup"><span data-stu-id="6f216-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="6f216-106">中NGen 模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="6f216-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="6f216-107">中定义 `inlineeMethodId`的模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="6f216-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="6f216-108">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="6f216-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="6f216-109">中内联方法的标识符。</span><span class="sxs-lookup"><span data-stu-id="6f216-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="6f216-110">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="6f216-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="6f216-111">弄指示 `ppEnum` 是否包含内联给定方法的所有方法的标志。</span><span class="sxs-lookup"><span data-stu-id="6f216-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="6f216-112">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="6f216-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="6f216-113">弄指向枚举器地址的指针</span><span class="sxs-lookup"><span data-stu-id="6f216-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="6f216-114">备注</span><span class="sxs-lookup"><span data-stu-id="6f216-114">Remarks</span></span>

<span data-ttu-id="6f216-115">`inlineeModuleId` 和 `inlineeMethodId` 一起构成了可能内联的方法的完整标识符。</span><span class="sxs-lookup"><span data-stu-id="6f216-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="6f216-116">例如，假设 module `A` 定义方法 `Simple.Add`：</span><span class="sxs-lookup"><span data-stu-id="6f216-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="6f216-117">和模块 B 定义 `Fancy.AddTwice`：</span><span class="sxs-lookup"><span data-stu-id="6f216-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="6f216-118">还假定 `Fancy.AddTwice` inlines 调用 `SimpleAdd`。</span><span class="sxs-lookup"><span data-stu-id="6f216-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="6f216-119">探查器可以使用此枚举器来查找模块 B 中定义的内联 `Simple.Add`的所有方法，结果将枚举 `AddTwice`。</span><span class="sxs-lookup"><span data-stu-id="6f216-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="6f216-120">`inlineeModuleId` 是模块 `A`的标识符，`inlineeMethodId` 是 `Simple.Add(int a, int b)`的标识符。</span><span class="sxs-lookup"><span data-stu-id="6f216-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="6f216-121">如果在函数返回后 `incompleteData` 为 true，则枚举器不包含内联给定方法的所有方法。</span><span class="sxs-lookup"><span data-stu-id="6f216-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="6f216-122">如果尚未加载 inliners 模块的一个或多个直接或间接依赖项，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="6f216-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="6f216-123">如果探查器需要准确的数据，则应在加载更多模块时重试，最好是在每个模块加载时重试。</span><span class="sxs-lookup"><span data-stu-id="6f216-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="6f216-124">`EnumNgenModuleMethodsInliningThisMethod` 方法可用于解决 ReJIT 的内联限制。</span><span class="sxs-lookup"><span data-stu-id="6f216-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="6f216-125">ReJIT 使探查器可以更改方法的实现，然后动态为其创建新代码。</span><span class="sxs-lookup"><span data-stu-id="6f216-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="6f216-126">例如，我们可以按如下所示更改 `Simple.Add`：</span><span class="sxs-lookup"><span data-stu-id="6f216-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="6f216-127">但是，因为 `Fancy.AddTwice` 已经内联 `Simple.Add`，它将继续与之前一样具有相同的行为。</span><span class="sxs-lookup"><span data-stu-id="6f216-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="6f216-128">若要解决此限制，调用方必须搜索内联 `Simple.Add` 的所有模块中的所有方法，并对这些方法使用 `ICorProfilerInfo5::RequestRejit`。</span><span class="sxs-lookup"><span data-stu-id="6f216-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="6f216-129">重新编译这些方法时，它们将具有 `Simple.Add` 的新行为，而不是旧的行为。</span><span class="sxs-lookup"><span data-stu-id="6f216-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="6f216-130">要求</span><span class="sxs-lookup"><span data-stu-id="6f216-130">Requirements</span></span>

<span data-ttu-id="6f216-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6f216-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6f216-132">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f216-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="6f216-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f216-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="6f216-134">**.NET Framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f216-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6f216-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f216-135">See also</span></span>

- [<span data-ttu-id="6f216-136">ICorProfilerInfo6 接口</span><span class="sxs-lookup"><span data-stu-id="6f216-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
