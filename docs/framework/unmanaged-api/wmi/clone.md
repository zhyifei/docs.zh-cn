---
title: Clone 函数 （非托管 API 参考）
description: 克隆函数返回是当前的完整克隆一个新对象。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b027d26292b5d810d91932bac4ec8dee4b77661d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643281"
---
# <a name="clone-function"></a><span data-ttu-id="cc639-103">Clone 函数</span><span class="sxs-lookup"><span data-stu-id="cc639-103">Clone function</span></span>
<span data-ttu-id="cc639-104">返回一个新对象，该对象是当前对象的完整克隆。</span><span class="sxs-lookup"><span data-stu-id="cc639-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="cc639-105">语法</span><span class="sxs-lookup"><span data-stu-id="cc639-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="cc639-106">参数</span><span class="sxs-lookup"><span data-stu-id="cc639-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="cc639-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="cc639-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="cc639-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="cc639-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="cc639-109">[out]是一个完整的新对象的单个`ptr`。</span><span class="sxs-lookup"><span data-stu-id="cc639-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="cc639-110">此参数不能为`null`如果它收到的当前对象的副本。</span><span class="sxs-lookup"><span data-stu-id="cc639-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="cc639-111">返回值</span><span class="sxs-lookup"><span data-stu-id="cc639-111">Return value</span></span>

<span data-ttu-id="cc639-112">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="cc639-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cc639-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="cc639-113">Constant</span></span>  |<span data-ttu-id="cc639-114">“值”</span><span class="sxs-lookup"><span data-stu-id="cc639-114">Value</span></span>  |<span data-ttu-id="cc639-115">描述</span><span class="sxs-lookup"><span data-stu-id="cc639-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="cc639-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="cc639-116">0x80041001</span></span> | <span data-ttu-id="cc639-117">已存在时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="cc639-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cc639-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cc639-118">0x80041008</span></span> | <span data-ttu-id="cc639-119">`null` 指定为参数，且是不合法在这种用法。</span><span class="sxs-lookup"><span data-stu-id="cc639-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cc639-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cc639-120">0x80041006</span></span> | <span data-ttu-id="cc639-121">可克隆该对象没有足够的内存。</span><span class="sxs-lookup"><span data-stu-id="cc639-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="cc639-122">0</span><span class="sxs-lookup"><span data-stu-id="cc639-122">0</span></span> | <span data-ttu-id="cc639-123">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="cc639-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="cc639-124">备注</span><span class="sxs-lookup"><span data-stu-id="cc639-124">Remarks</span></span>

<span data-ttu-id="cc639-125">此函数包装对的调用[IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)方法。</span><span class="sxs-lookup"><span data-stu-id="cc639-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="cc639-126">克隆的对象是 COM 对象的引用计数为 1。</span><span class="sxs-lookup"><span data-stu-id="cc639-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc639-127">要求</span><span class="sxs-lookup"><span data-stu-id="cc639-127">Requirements</span></span>  
 <span data-ttu-id="cc639-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc639-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc639-129">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cc639-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="cc639-130">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cc639-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc639-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc639-131">See also</span></span>
- [<span data-ttu-id="cc639-132">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="cc639-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
