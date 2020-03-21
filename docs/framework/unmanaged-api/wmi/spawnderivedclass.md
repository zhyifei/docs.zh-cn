---
title: 生成派生类函数（非托管 API 引用）
description: Spawn 派生类函数创建一个从对象派生的新对象。
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: e9784f8a024c788823dc702794b2b86eea1827bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174844"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="21730-103">SpawnDerivedClass 函数</span><span class="sxs-lookup"><span data-stu-id="21730-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="21730-104">从指定对象创建新派生的类对象。</span><span class="sxs-lookup"><span data-stu-id="21730-104">Creates a newly derived class object from a specified object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="21730-105">语法</span><span class="sxs-lookup"><span data-stu-id="21730-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a><span data-ttu-id="21730-106">parameters</span><span class="sxs-lookup"><span data-stu-id="21730-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="21730-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="21730-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="21730-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="21730-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="21730-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="21730-109">[in] Reserved.</span></span> <span data-ttu-id="21730-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="21730-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="21730-111">[出]接收指向新类定义对象的指针。</span><span class="sxs-lookup"><span data-stu-id="21730-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="21730-112">如果发生错误，则不会返回新对象，并且`ppNewClass`未修改。</span><span class="sxs-lookup"><span data-stu-id="21730-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="21730-113">其值不能为`null`。</span><span class="sxs-lookup"><span data-stu-id="21730-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="21730-114">返回值</span><span class="sxs-lookup"><span data-stu-id="21730-114">Return value</span></span>

<span data-ttu-id="21730-115">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="21730-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="21730-116">一直</span><span class="sxs-lookup"><span data-stu-id="21730-116">Constant</span></span>  |<span data-ttu-id="21730-117">值</span><span class="sxs-lookup"><span data-stu-id="21730-117">Value</span></span>  |<span data-ttu-id="21730-118">说明</span><span class="sxs-lookup"><span data-stu-id="21730-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="21730-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="21730-119">0x80041001</span></span> | <span data-ttu-id="21730-120">出现了一个普遍的失败。</span><span class="sxs-lookup"><span data-stu-id="21730-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="21730-121">0 x80041016</span><span class="sxs-lookup"><span data-stu-id="21730-121">0x80041016</span></span> | <span data-ttu-id="21730-122">请求无效操作，例如从实例生成类。</span><span class="sxs-lookup"><span data-stu-id="21730-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="21730-123">源类未完全定义或注册到 Windows 管理，因此不允许使用新的派生类。</span><span class="sxs-lookup"><span data-stu-id="21730-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="21730-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="21730-124">0x80041006</span></span> | <span data-ttu-id="21730-125">没有足够的可用内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="21730-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="21730-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="21730-126">0x80041008</span></span> | <span data-ttu-id="21730-127">`ppNewClass` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="21730-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="21730-128">0</span><span class="sxs-lookup"><span data-stu-id="21730-128">0</span></span> | <span data-ttu-id="21730-129">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="21730-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="21730-130">备注</span><span class="sxs-lookup"><span data-stu-id="21730-130">Remarks</span></span>

<span data-ttu-id="21730-131">此函数将调用包起来到[IWbem ClassObject：：spawn派生类](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)方法。</span><span class="sxs-lookup"><span data-stu-id="21730-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="21730-132">`ptr`必须是成为生成对象的父类的类定义。</span><span class="sxs-lookup"><span data-stu-id="21730-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="21730-133">返回的对象将成为当前对象的子类。</span><span class="sxs-lookup"><span data-stu-id="21730-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="21730-134">返回`ppNewClass`的新对象将自动成为当前对象的子类。</span><span class="sxs-lookup"><span data-stu-id="21730-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="21730-135">无法重写此行为。</span><span class="sxs-lookup"><span data-stu-id="21730-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="21730-136">没有其他方法可以创建子类（派生类）。</span><span class="sxs-lookup"><span data-stu-id="21730-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="21730-137">要求</span><span class="sxs-lookup"><span data-stu-id="21730-137">Requirements</span></span>  
 <span data-ttu-id="21730-138">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21730-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21730-139">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="21730-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="21730-140">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="21730-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21730-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21730-141">See also</span></span>

- [<span data-ttu-id="21730-142">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="21730-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
