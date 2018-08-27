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
ms.openlocfilehash: 5cd87cb619ef2dc1e0548c7553585b7e51e94c4f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924770"
---
# <a name="clone-function"></a><span data-ttu-id="bbbed-103">Clone 函数</span><span class="sxs-lookup"><span data-stu-id="bbbed-103">Clone function</span></span>
<span data-ttu-id="bbbed-104">返回是当前对象的完整克隆一个新对象。</span><span class="sxs-lookup"><span data-stu-id="bbbed-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bbbed-105">语法</span><span class="sxs-lookup"><span data-stu-id="bbbed-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="bbbed-106">参数</span><span class="sxs-lookup"><span data-stu-id="bbbed-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="bbbed-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="bbbed-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="bbbed-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="bbbed-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="bbbed-109">[out]是一个完整的新对象的单个`ptr`。</span><span class="sxs-lookup"><span data-stu-id="bbbed-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="bbbed-110">此参数不能为`null`如果它收到的当前对象的副本。</span><span class="sxs-lookup"><span data-stu-id="bbbed-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="bbbed-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bbbed-111">Return value</span></span>

<span data-ttu-id="bbbed-112">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="bbbed-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bbbed-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="bbbed-113">Constant</span></span>  |<span data-ttu-id="bbbed-114">“值”</span><span class="sxs-lookup"><span data-stu-id="bbbed-114">Value</span></span>  |<span data-ttu-id="bbbed-115">描述</span><span class="sxs-lookup"><span data-stu-id="bbbed-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="bbbed-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="bbbed-116">0x80041001</span></span> | <span data-ttu-id="bbbed-117">已存在时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="bbbed-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bbbed-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bbbed-118">0x80041008</span></span> | <span data-ttu-id="bbbed-119">`null` 指定为参数，且是不合法在这种用法。</span><span class="sxs-lookup"><span data-stu-id="bbbed-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bbbed-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bbbed-120">0x80041006</span></span> | <span data-ttu-id="bbbed-121">可克隆该对象没有足够的内存。</span><span class="sxs-lookup"><span data-stu-id="bbbed-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="bbbed-122">0</span><span class="sxs-lookup"><span data-stu-id="bbbed-122">0</span></span> | <span data-ttu-id="bbbed-123">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="bbbed-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bbbed-124">备注</span><span class="sxs-lookup"><span data-stu-id="bbbed-124">Remarks</span></span>

<span data-ttu-id="bbbed-125">此函数包装对的调用[IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)方法。</span><span class="sxs-lookup"><span data-stu-id="bbbed-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="bbbed-126">克隆的对象是 COM 对象的引用计数为 1。</span><span class="sxs-lookup"><span data-stu-id="bbbed-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="bbbed-127">要求</span><span class="sxs-lookup"><span data-stu-id="bbbed-127">Requirements</span></span>  
 <span data-ttu-id="bbbed-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbbed-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbbed-129">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bbbed-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bbbed-130">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bbbed-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbed-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbbed-131">See also</span></span>  
[<span data-ttu-id="bbbed-132">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="bbbed-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
