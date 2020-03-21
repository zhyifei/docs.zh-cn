---
title: 克隆功能（非托管 API 引用）
description: Clone 函数返回一个新对象，该对象是当前对象的完整克隆。
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176846"
---
# <a name="clone-function"></a><span data-ttu-id="5f4f0-103">Clone 函数</span><span class="sxs-lookup"><span data-stu-id="5f4f0-103">Clone function</span></span>
<span data-ttu-id="5f4f0-104">返回一个新对象，该对象是当前对象的完整克隆。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-104">Returns a new object that is a complete clone of the current object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5f4f0-105">语法</span><span class="sxs-lookup"><span data-stu-id="5f4f0-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a><span data-ttu-id="5f4f0-106">parameters</span><span class="sxs-lookup"><span data-stu-id="5f4f0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5f4f0-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5f4f0-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="5f4f0-109">[出]一个新对象，它是 完全孤独的`ptr`。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="5f4f0-110">`null`如果此参数收到当前对象的副本，则不能。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="5f4f0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="5f4f0-111">Return value</span></span>

<span data-ttu-id="5f4f0-112">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="5f4f0-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5f4f0-113">一直</span><span class="sxs-lookup"><span data-stu-id="5f4f0-113">Constant</span></span>  |<span data-ttu-id="5f4f0-114">值</span><span class="sxs-lookup"><span data-stu-id="5f4f0-114">Value</span></span>  |<span data-ttu-id="5f4f0-115">说明</span><span class="sxs-lookup"><span data-stu-id="5f4f0-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="5f4f0-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="5f4f0-116">0x80041001</span></span> | <span data-ttu-id="5f4f0-117">出现了一个普遍的失败。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5f4f0-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5f4f0-118">0x80041008</span></span> | <span data-ttu-id="5f4f0-119">`null`被指定为参数，在此用法中不合法。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5f4f0-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5f4f0-120">0x80041006</span></span> | <span data-ttu-id="5f4f0-121">没有足够的内存可用于克隆对象。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5f4f0-122">0</span><span class="sxs-lookup"><span data-stu-id="5f4f0-122">0</span></span> | <span data-ttu-id="5f4f0-123">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5f4f0-124">备注</span><span class="sxs-lookup"><span data-stu-id="5f4f0-124">Remarks</span></span>

<span data-ttu-id="5f4f0-125">此函数包装对[IWbem ClassObject：：克隆](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="5f4f0-126">克隆的对象是引用计数为 1 的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="5f4f0-127">要求</span><span class="sxs-lookup"><span data-stu-id="5f4f0-127">Requirements</span></span>  
 <span data-ttu-id="5f4f0-128">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f4f0-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f4f0-129">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5f4f0-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5f4f0-130">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5f4f0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f4f0-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f4f0-131">See also</span></span>

- [<span data-ttu-id="5f4f0-132">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="5f4f0-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
