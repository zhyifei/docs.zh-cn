---
title: "WritePropertyValue 函数 （非托管 API 参考）"
description: "WritePropertyValue 函数将字节写入属性。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: WritePropertyValue
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: WritePropertyValue
helpviewer_keywords: WritePropertyValue function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7221c9e0f1cb49ab0e27130ce69c0527ba903148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="e3e63-103">WritePropertyValue 函数</span><span class="sxs-lookup"><span data-stu-id="e3e63-103">WritePropertyValue function</span></span>
<span data-ttu-id="e3e63-104">将指定的数目的字节写入由属性句柄识别的属性。</span><span class="sxs-lookup"><span data-stu-id="e3e63-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e3e63-105">语法</span><span class="sxs-lookup"><span data-stu-id="e3e63-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="e3e63-106">参数</span><span class="sxs-lookup"><span data-stu-id="e3e63-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e3e63-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="e3e63-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e3e63-108">[in]指向的指针[IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="e3e63-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`lHandle`  
<span data-ttu-id="e3e63-109">[in]一个整数，包含标识此属性的句柄。</span><span class="sxs-lookup"><span data-stu-id="e3e63-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="e3e63-110">可通过调用检索句柄[GetPropertyHandle](getpropertyhandle.md)函数。</span><span class="sxs-lookup"><span data-stu-id="e3e63-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="e3e63-111">[in]正在写入的属性的字节数。</span><span class="sxs-lookup"><span data-stu-id="e3e63-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="e3e63-112">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="e3e63-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="e3e63-113">[out]指向包含数据的字节数组的指针。</span><span class="sxs-lookup"><span data-stu-id="e3e63-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="e3e63-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e3e63-114">Return value</span></span>

<span data-ttu-id="e3e63-115">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="e3e63-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e3e63-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e3e63-116">Constant</span></span>  |<span data-ttu-id="e3e63-117">“值”</span><span class="sxs-lookup"><span data-stu-id="e3e63-117">Value</span></span>  |<span data-ttu-id="e3e63-118">描述</span><span class="sxs-lookup"><span data-stu-id="e3e63-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e3e63-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e3e63-119">0x80041008</span></span> | <span data-ttu-id="e3e63-120">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="e3e63-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="e3e63-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="e3e63-121">0x80041005</span></span> | <span data-ttu-id="e3e63-122">出现类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="e3e63-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e3e63-123">0</span><span class="sxs-lookup"><span data-stu-id="e3e63-123">0</span></span> | <span data-ttu-id="e3e63-124">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e3e63-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e3e63-125">备注</span><span class="sxs-lookup"><span data-stu-id="e3e63-125">Remarks</span></span>

<span data-ttu-id="e3e63-126">此函数包装对的调用[IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="e3e63-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="e3e63-127">使用此函数可设置字符串和所有其他非`DWORD`或非-`QWORD`数据。</span><span class="sxs-lookup"><span data-stu-id="e3e63-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="e3e63-128">对于非字符串属性值，`lNumBytes`必须是指定的属性类型的正确的数据大小。</span><span class="sxs-lookup"><span data-stu-id="e3e63-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="e3e63-129">字符串属性值，`lNumBytes`必须是长度以字节为单位，指定的字符串和字符串本身必须为偶数长度以字节为单位，以 null 终止字符开始便遵循。</span><span class="sxs-lookup"><span data-stu-id="e3e63-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="e3e63-130">惠?</span><span class="sxs-lookup"><span data-stu-id="e3e63-130">Requirements</span></span>  
<span data-ttu-id="e3e63-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3e63-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3e63-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e3e63-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e3e63-133">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e3e63-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3e63-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3e63-134">See also</span></span>  
[<span data-ttu-id="e3e63-135">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e3e63-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
