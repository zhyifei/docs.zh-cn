---
title: 克隆函数 （非托管 API 参考）
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
ms.openlocfilehash: c5841c89cf394502f68381dfed42593c9debdcb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457311"
---
# <a name="clone-function"></a><span data-ttu-id="a093f-103">克隆函数</span><span class="sxs-lookup"><span data-stu-id="a093f-103">Clone function</span></span>
<span data-ttu-id="a093f-104">返回是当前对象的完整克隆一个新对象。</span><span class="sxs-lookup"><span data-stu-id="a093f-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a093f-105">语法</span><span class="sxs-lookup"><span data-stu-id="a093f-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="a093f-106">参数</span><span class="sxs-lookup"><span data-stu-id="a093f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a093f-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="a093f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a093f-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="a093f-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppCopy`  
<span data-ttu-id="a093f-109">[out]是一个完整的新对象的唯一`ptr`。</span><span class="sxs-lookup"><span data-stu-id="a093f-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="a093f-110">此参数不能为`null`如果它收到当前对象的副本。</span><span class="sxs-lookup"><span data-stu-id="a093f-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="a093f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a093f-111">Return value</span></span>

<span data-ttu-id="a093f-112">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="a093f-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a093f-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="a093f-113">Constant</span></span>  |<span data-ttu-id="a093f-114">值</span><span class="sxs-lookup"><span data-stu-id="a093f-114">Value</span></span>  |<span data-ttu-id="a093f-115">描述</span><span class="sxs-lookup"><span data-stu-id="a093f-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="a093f-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a093f-116">0x80041001</span></span> | <span data-ttu-id="a093f-117">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="a093f-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a093f-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a093f-118">0x80041008</span></span> | <span data-ttu-id="a093f-119">`null` 已指定为参数，且它不是合法在这种用法。</span><span class="sxs-lookup"><span data-stu-id="a093f-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a093f-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a093f-120">0x80041006</span></span> | <span data-ttu-id="a093f-121">没有足够的内存可克隆对象。</span><span class="sxs-lookup"><span data-stu-id="a093f-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="a093f-122">0</span><span class="sxs-lookup"><span data-stu-id="a093f-122">0</span></span> | <span data-ttu-id="a093f-123">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="a093f-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a093f-124">备注</span><span class="sxs-lookup"><span data-stu-id="a093f-124">Remarks</span></span>

<span data-ttu-id="a093f-125">此函数包装对的调用[IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="a093f-125">This function wraps a call to the [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="a093f-126">克隆的对象是 COM 对象的引用计数为 1。</span><span class="sxs-lookup"><span data-stu-id="a093f-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="a093f-127">要求</span><span class="sxs-lookup"><span data-stu-id="a093f-127">Requirements</span></span>  
 <span data-ttu-id="a093f-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a093f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a093f-129">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a093f-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a093f-130">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a093f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a093f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a093f-131">See also</span></span>  
[<span data-ttu-id="a093f-132">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="a093f-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
