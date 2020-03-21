---
title: 生成实例函数（非托管 API 引用）
description: SpawnInstance 函数创建类的新实例。
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a15eb8123c1ee807444bdb4c6fe71cdccc08f434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176716"
---
# <a name="spawninstance-function"></a><span data-ttu-id="eaf55-103">SpawnInstance 函数</span><span class="sxs-lookup"><span data-stu-id="eaf55-103">SpawnInstance function</span></span>
<span data-ttu-id="eaf55-104">创建类的新实例。</span><span class="sxs-lookup"><span data-stu-id="eaf55-104">Creates a new instance of a class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="eaf55-105">语法</span><span class="sxs-lookup"><span data-stu-id="eaf55-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a><span data-ttu-id="eaf55-106">parameters</span><span class="sxs-lookup"><span data-stu-id="eaf55-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="eaf55-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="eaf55-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="eaf55-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="eaf55-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="eaf55-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="eaf55-109">[in] Reserved.</span></span> <span data-ttu-id="eaf55-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="eaf55-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="eaf55-111">[出]接收指向类新实例的指针。</span><span class="sxs-lookup"><span data-stu-id="eaf55-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="eaf55-112">如果发生错误，则不会返回新对象，并且`ppNewInstance`未修改。</span><span class="sxs-lookup"><span data-stu-id="eaf55-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="eaf55-113">返回值</span><span class="sxs-lookup"><span data-stu-id="eaf55-113">Return value</span></span>

<span data-ttu-id="eaf55-114">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="eaf55-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="eaf55-115">一直</span><span class="sxs-lookup"><span data-stu-id="eaf55-115">Constant</span></span>  |<span data-ttu-id="eaf55-116">值</span><span class="sxs-lookup"><span data-stu-id="eaf55-116">Value</span></span>  |<span data-ttu-id="eaf55-117">说明</span><span class="sxs-lookup"><span data-stu-id="eaf55-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="eaf55-118">0 x80041020</span><span class="sxs-lookup"><span data-stu-id="eaf55-118">0x80041020</span></span> | <span data-ttu-id="eaf55-119">`ptr`不是有效的类定义，不能生成新实例。</span><span class="sxs-lookup"><span data-stu-id="eaf55-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="eaf55-120">要么不完整，要么没有通过调用[PutClassWmi](putclasswmi.md)在 Windows 管理中注册。</span><span class="sxs-lookup"><span data-stu-id="eaf55-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="eaf55-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="eaf55-121">0x80041006</span></span> | <span data-ttu-id="eaf55-122">没有足够的可用内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="eaf55-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="eaf55-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="eaf55-123">0x80041008</span></span> | <span data-ttu-id="eaf55-124">`ppNewClass` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="eaf55-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="eaf55-125">0</span><span class="sxs-lookup"><span data-stu-id="eaf55-125">0</span></span> | <span data-ttu-id="eaf55-126">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="eaf55-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="eaf55-127">备注</span><span class="sxs-lookup"><span data-stu-id="eaf55-127">Remarks</span></span>

<span data-ttu-id="eaf55-128">此函数将调用包起来到[IWbem ClassObject：：spawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance)方法。</span><span class="sxs-lookup"><span data-stu-id="eaf55-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="eaf55-129">`ptr`必须是从 Windows 管理获取的类定义。</span><span class="sxs-lookup"><span data-stu-id="eaf55-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="eaf55-130">（请注意，支持从实例生成实例，但返回的实例为空。然后，使用此类定义创建新实例。</span><span class="sxs-lookup"><span data-stu-id="eaf55-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="eaf55-131">如果要将实例写入 Windows 管理，则需要调用[PutInstanceWmi](putinstancewmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="eaf55-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="eaf55-132">返回`ppNewClass`的新对象将自动成为当前对象的子类。</span><span class="sxs-lookup"><span data-stu-id="eaf55-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="eaf55-133">无法重写此行为。</span><span class="sxs-lookup"><span data-stu-id="eaf55-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="eaf55-134">没有其他方法可以创建子类（派生类）。</span><span class="sxs-lookup"><span data-stu-id="eaf55-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="eaf55-135">要求</span><span class="sxs-lookup"><span data-stu-id="eaf55-135">Requirements</span></span>  
 <span data-ttu-id="eaf55-136">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eaf55-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf55-137">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="eaf55-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="eaf55-138">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf55-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf55-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eaf55-139">See also</span></span>

- [<span data-ttu-id="eaf55-140">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="eaf55-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
