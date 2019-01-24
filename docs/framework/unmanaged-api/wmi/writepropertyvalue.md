---
title: WritePropertyValue 函数 （非托管 API 参考）
description: WritePropertyValue 函数将字节写入到一个属性。
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5a2588023309867694f344041f62be53cab9c37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590115"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="7d060-103">WritePropertyValue 函数</span><span class="sxs-lookup"><span data-stu-id="7d060-103">WritePropertyValue function</span></span>
<span data-ttu-id="7d060-104">将指定数量的字节写入由属性句柄标识的属性。</span><span class="sxs-lookup"><span data-stu-id="7d060-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="7d060-105">语法</span><span class="sxs-lookup"><span data-stu-id="7d060-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="7d060-106">参数</span><span class="sxs-lookup"><span data-stu-id="7d060-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7d060-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="7d060-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7d060-108">[in]一个指向[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)实例。</span><span class="sxs-lookup"><span data-stu-id="7d060-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="7d060-109">[in]一个整数，包含标识此属性的句柄。</span><span class="sxs-lookup"><span data-stu-id="7d060-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="7d060-110">可以通过调用来检索该句柄[GetPropertyHandle](getpropertyhandle.md)函数。</span><span class="sxs-lookup"><span data-stu-id="7d060-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="7d060-111">[in]正在写入到的属性的字节数。</span><span class="sxs-lookup"><span data-stu-id="7d060-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="7d060-112">请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d060-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="7d060-113">[out]指向包含数据的字节数组的指针。</span><span class="sxs-lookup"><span data-stu-id="7d060-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="7d060-114">返回值</span><span class="sxs-lookup"><span data-stu-id="7d060-114">Return value</span></span>

<span data-ttu-id="7d060-115">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="7d060-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7d060-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="7d060-116">Constant</span></span>  |<span data-ttu-id="7d060-117">“值”</span><span class="sxs-lookup"><span data-stu-id="7d060-117">Value</span></span>  |<span data-ttu-id="7d060-118">描述</span><span class="sxs-lookup"><span data-stu-id="7d060-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7d060-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7d060-119">0x80041008</span></span> | <span data-ttu-id="7d060-120">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="7d060-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="7d060-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="7d060-121">0x80041005</span></span> | <span data-ttu-id="7d060-122">出现类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="7d060-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7d060-123">0</span><span class="sxs-lookup"><span data-stu-id="7d060-123">0</span></span> | <span data-ttu-id="7d060-124">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="7d060-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7d060-125">备注</span><span class="sxs-lookup"><span data-stu-id="7d060-125">Remarks</span></span>

<span data-ttu-id="7d060-126">此函数包装对的调用[IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue)方法。</span><span class="sxs-lookup"><span data-stu-id="7d060-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="7d060-127">使用此函数来设置字符串和所有其他非`DWORD`或非-`QWORD`数据。</span><span class="sxs-lookup"><span data-stu-id="7d060-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="7d060-128">对于非字符串属性值，`lNumBytes`必须是指定的属性类型的正确的数据大小。</span><span class="sxs-lookup"><span data-stu-id="7d060-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="7d060-129">有关字符串属性值，`lNumBytes`必须是长度以字节为单位，指定的字符串和字符串本身必须将甚至长度以字节为单位的并且后跟一个 null 终止字符。</span><span class="sxs-lookup"><span data-stu-id="7d060-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d060-130">要求</span><span class="sxs-lookup"><span data-stu-id="7d060-130">Requirements</span></span>  
<span data-ttu-id="7d060-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d060-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d060-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7d060-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7d060-133">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7d060-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d060-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d060-134">See also</span></span>
- [<span data-ttu-id="7d060-135">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="7d060-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
