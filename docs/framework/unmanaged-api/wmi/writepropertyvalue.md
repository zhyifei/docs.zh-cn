---
title: 写入属性值函数（非托管 API 引用）
description: WritePropertyValue 函数将字节写入属性。
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
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174831"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="4889a-103">WritePropertyValue 函数</span><span class="sxs-lookup"><span data-stu-id="4889a-103">WritePropertyValue function</span></span>
<span data-ttu-id="4889a-104">将指定数量的字节写入由属性句柄标识的属性。</span><span class="sxs-lookup"><span data-stu-id="4889a-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4889a-105">语法</span><span class="sxs-lookup"><span data-stu-id="4889a-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
);
```  

## <a name="parameters"></a><span data-ttu-id="4889a-106">parameters</span><span class="sxs-lookup"><span data-stu-id="4889a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4889a-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="4889a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4889a-108">[在]指向[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="4889a-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="4889a-109">[在]包含标识此属性的句柄的整数。</span><span class="sxs-lookup"><span data-stu-id="4889a-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="4889a-110">可以通过调用[GetPropertyHandle](getpropertyhandle.md)函数来检索句柄。</span><span class="sxs-lookup"><span data-stu-id="4889a-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>

`lNumBytes`  
<span data-ttu-id="4889a-111">[在]写入属性的字节数。</span><span class="sxs-lookup"><span data-stu-id="4889a-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="4889a-112">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="4889a-112">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="4889a-113">`pHandle`[出]指向包含数据的字节数组的指针。</span><span class="sxs-lookup"><span data-stu-id="4889a-113">`pHandle` [out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="4889a-114">返回值</span><span class="sxs-lookup"><span data-stu-id="4889a-114">Return value</span></span>

<span data-ttu-id="4889a-115">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="4889a-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4889a-116">一直</span><span class="sxs-lookup"><span data-stu-id="4889a-116">Constant</span></span>  |<span data-ttu-id="4889a-117">值</span><span class="sxs-lookup"><span data-stu-id="4889a-117">Value</span></span>  |<span data-ttu-id="4889a-118">说明</span><span class="sxs-lookup"><span data-stu-id="4889a-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4889a-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4889a-119">0x80041008</span></span> | <span data-ttu-id="4889a-120">参数无效。</span><span class="sxs-lookup"><span data-stu-id="4889a-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="4889a-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="4889a-121">0x80041005</span></span> | <span data-ttu-id="4889a-122">出现类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="4889a-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4889a-123">0</span><span class="sxs-lookup"><span data-stu-id="4889a-123">0</span></span> | <span data-ttu-id="4889a-124">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="4889a-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4889a-125">备注</span><span class="sxs-lookup"><span data-stu-id="4889a-125">Remarks</span></span>

<span data-ttu-id="4889a-126">此函数将调用包起来到[IWbemClassObject：：WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue)方法。</span><span class="sxs-lookup"><span data-stu-id="4889a-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="4889a-127">使用此函数可以设置字符串和所有其他非`DWORD`或非`QWORD`数据。</span><span class="sxs-lookup"><span data-stu-id="4889a-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="4889a-128">对于非字符串属性值，`lNumBytes`必须为指定的属性类型的正确数据大小。</span><span class="sxs-lookup"><span data-stu-id="4889a-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="4889a-129">对于字符串属性值，`lNumBytes`必须为指定字符串的长度（以字节为单位），并且字符串本身的长度（以字节为单位）并且后面必须使用 null 终止字符。</span><span class="sxs-lookup"><span data-stu-id="4889a-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="4889a-130">要求</span><span class="sxs-lookup"><span data-stu-id="4889a-130">Requirements</span></span>  
<span data-ttu-id="4889a-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4889a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4889a-132">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4889a-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4889a-133">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4889a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4889a-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4889a-134">See also</span></span>

- [<span data-ttu-id="4889a-135">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="4889a-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
