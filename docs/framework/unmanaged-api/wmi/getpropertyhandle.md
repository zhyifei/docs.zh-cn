---
title: GetPropertyHandle 函数（非托管 API 参考）
description: GetPropertyHandle 函数返回标识属性的唯一句柄。
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d72b0da43971a74a08a249b19dfc0d446eeb5e6a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798536"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="ad213-103">GetPropertyHandle 函数</span><span class="sxs-lookup"><span data-stu-id="ad213-103">GetPropertyHandle function</span></span>

<span data-ttu-id="ad213-104">返回标识属性的唯一句柄。</span><span class="sxs-lookup"><span data-stu-id="ad213-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ad213-105">语法</span><span class="sxs-lookup"><span data-stu-id="ad213-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="ad213-106">参数</span><span class="sxs-lookup"><span data-stu-id="ad213-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="ad213-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="ad213-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="ad213-108">中指向[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="ad213-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="ad213-109">中以 null 结尾的 UTF16 编码字符的字符串，其中包含属性名称。</span><span class="sxs-lookup"><span data-stu-id="ad213-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="ad213-110">弄一个指针，指向[`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration)表示属性的 CIM 类型的枚举成员。</span><span class="sxs-lookup"><span data-stu-id="ad213-110">[out] A pointer to a [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="ad213-111">弄指向包含属性句柄的整数的指针。</span><span class="sxs-lookup"><span data-stu-id="ad213-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="ad213-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ad213-112">Return value</span></span>

<span data-ttu-id="ad213-113">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="ad213-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ad213-114">返回的常量</span><span class="sxs-lookup"><span data-stu-id="ad213-114">Constant</span></span>  |<span data-ttu-id="ad213-115">值</span><span class="sxs-lookup"><span data-stu-id="ad213-115">Value</span></span>  |<span data-ttu-id="ad213-116">描述</span><span class="sxs-lookup"><span data-stu-id="ad213-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="ad213-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ad213-117">0x80041002</span></span> | <span data-ttu-id="ad213-118">找不到指定的属性名。</span><span class="sxs-lookup"><span data-stu-id="ad213-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ad213-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ad213-119">0x80041008</span></span> | <span data-ttu-id="ad213-120">参数无效。</span><span class="sxs-lookup"><span data-stu-id="ad213-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="ad213-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="ad213-121">0x8004100c</span></span> | <span data-ttu-id="ad213-122">请求的属性的类型`CIM_OBJECT`为或。 `CIM_ARRAY`</span><span class="sxs-lookup"><span data-stu-id="ad213-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ad213-123">0</span><span class="sxs-lookup"><span data-stu-id="ad213-123">0</span></span> | <span data-ttu-id="ad213-124">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="ad213-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ad213-125">备注</span><span class="sxs-lookup"><span data-stu-id="ad213-125">Remarks</span></span>

<span data-ttu-id="ad213-126">此函数包装对[IWbemClassObject：： GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="ad213-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="ad213-127">使用[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)方法读取或写入属性值时，可以使用此句柄来确定属性。</span><span class="sxs-lookup"><span data-stu-id="ad213-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="ad213-128">对于除`CIM_OBJECT`和`CIM_ARRAY`之外的所有数据类型的属性，可以检索句柄。</span><span class="sxs-lookup"><span data-stu-id="ad213-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="ad213-129">返回的句柄在类的所有实例中工作。</span><span class="sxs-lookup"><span data-stu-id="ad213-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad213-130">要求</span><span class="sxs-lookup"><span data-stu-id="ad213-130">Requirements</span></span>

<span data-ttu-id="ad213-131">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad213-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ad213-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ad213-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ad213-133">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ad213-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ad213-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad213-134">See also</span></span>

- [<span data-ttu-id="ad213-135">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="ad213-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
