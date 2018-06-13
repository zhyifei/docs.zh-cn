---
title: GetPropertyHandle 函数 （非托管 API 参考）
description: GetPropertyHandle 函数返回一个唯一的句柄该 identies 属性。
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
ms.openlocfilehash: 103e81dfa0e455157cfce5914b711347b15b578d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460578"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="655ac-103">GetPropertyHandle 函数</span><span class="sxs-lookup"><span data-stu-id="655ac-103">GetPropertyHandle function</span></span>
<span data-ttu-id="655ac-104">返回一个唯一的句柄，标识属性。</span><span class="sxs-lookup"><span data-stu-id="655ac-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="655ac-105">语法</span><span class="sxs-lookup"><span data-stu-id="655ac-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="655ac-106">参数</span><span class="sxs-lookup"><span data-stu-id="655ac-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="655ac-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="655ac-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="655ac-108">[in]指向的指针[IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="655ac-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="655ac-109">[in]包含属性名称的 UTF16 编码 characaters 的以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="655ac-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="655ac-110">[out]指向的指针[ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx)表示属性的 CIM 类型的枚举成员。</span><span class="sxs-lookup"><span data-stu-id="655ac-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="655ac-111">[out]指向一个包含属性句柄整数的指针。</span><span class="sxs-lookup"><span data-stu-id="655ac-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="655ac-112">返回值</span><span class="sxs-lookup"><span data-stu-id="655ac-112">Return value</span></span>

<span data-ttu-id="655ac-113">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="655ac-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="655ac-114">返回的常量</span><span class="sxs-lookup"><span data-stu-id="655ac-114">Constant</span></span>  |<span data-ttu-id="655ac-115">值</span><span class="sxs-lookup"><span data-stu-id="655ac-115">Value</span></span>  |<span data-ttu-id="655ac-116">描述</span><span class="sxs-lookup"><span data-stu-id="655ac-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="655ac-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="655ac-117">0x80041002</span></span> | <span data-ttu-id="655ac-118">找不到指定的属性名称。</span><span class="sxs-lookup"><span data-stu-id="655ac-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="655ac-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="655ac-119">0x80041008</span></span> | <span data-ttu-id="655ac-120">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="655ac-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="655ac-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="655ac-121">0x8004100c</span></span> | <span data-ttu-id="655ac-122">请求的属性属于类型是`CIM_OBJECT`或`CIM_ARRAY`。</span><span class="sxs-lookup"><span data-stu-id="655ac-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="655ac-123">0</span><span class="sxs-lookup"><span data-stu-id="655ac-123">0</span></span> | <span data-ttu-id="655ac-124">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="655ac-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="655ac-125">备注</span><span class="sxs-lookup"><span data-stu-id="655ac-125">Remarks</span></span>

<span data-ttu-id="655ac-126">此函数包装对的调用[IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="655ac-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="655ac-127">你可以使用此句柄来标识属性，使用时[IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx)方法读取或写入属性值。</span><span class="sxs-lookup"><span data-stu-id="655ac-127">You can use this handle to identify properties when using  [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) methods to read or write property values.</span></span>

<span data-ttu-id="655ac-128">句柄可以检索的属性的所有数据类型以外`CIM_OBJECT`和`CIM_ARRAY`。</span><span class="sxs-lookup"><span data-stu-id="655ac-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="655ac-129">返回在类的所有实例的句柄的工作。</span><span class="sxs-lookup"><span data-stu-id="655ac-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="655ac-130">要求</span><span class="sxs-lookup"><span data-stu-id="655ac-130">Requirements</span></span>  
<span data-ttu-id="655ac-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="655ac-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="655ac-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="655ac-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="655ac-133">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="655ac-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655ac-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="655ac-134">See also</span></span>  
[<span data-ttu-id="655ac-135">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="655ac-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
