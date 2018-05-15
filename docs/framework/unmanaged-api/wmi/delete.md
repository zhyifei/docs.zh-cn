---
title: 删除函数 （非托管 API 参考）
description: Delete 函数从 CIM 类定义中删除指定的属性和所有其限定符。
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7fcf5cff9f95b06a834d73df4090bd1edfca61b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="delete-function"></a><span data-ttu-id="f8942-103">删除函数</span><span class="sxs-lookup"><span data-stu-id="f8942-103">Delete function</span></span>
<span data-ttu-id="f8942-104">从 CIM 类定义中删除指定的属性和所有其限定符。</span><span class="sxs-lookup"><span data-stu-id="f8942-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f8942-105">语法</span><span class="sxs-lookup"><span data-stu-id="f8942-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="f8942-106">参数</span><span class="sxs-lookup"><span data-stu-id="f8942-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f8942-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="f8942-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f8942-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="f8942-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="f8942-109">[in]要删除的属性名称。</span><span class="sxs-lookup"><span data-stu-id="f8942-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="f8942-110">`wszName` 必须为有效的指针`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="f8942-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f8942-111">返回值</span><span class="sxs-lookup"><span data-stu-id="f8942-111">Return value</span></span>

<span data-ttu-id="f8942-112">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="f8942-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f8942-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="f8942-113">Constant</span></span>  |<span data-ttu-id="f8942-114">值</span><span class="sxs-lookup"><span data-stu-id="f8942-114">Value</span></span>  |<span data-ttu-id="f8942-115">描述</span><span class="sxs-lookup"><span data-stu-id="f8942-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="f8942-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f8942-116">0x80041001</span></span> | <span data-ttu-id="f8942-117">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="f8942-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="f8942-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="f8942-118">0x80041016</span></span> | <span data-ttu-id="f8942-119">无法删除属性。</span><span class="sxs-lookup"><span data-stu-id="f8942-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f8942-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f8942-120">0x80041008</span></span> | <span data-ttu-id="f8942-121">`wszzName` 无效。</span><span class="sxs-lookup"><span data-stu-id="f8942-121">`wszzName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="f8942-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f8942-122">0x80041002</span></span> | <span data-ttu-id="f8942-123">指定的属性不存在。</span><span class="sxs-lookup"><span data-stu-id="f8942-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f8942-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f8942-124">0x80041006</span></span> | <span data-ttu-id="f8942-125">没有足够的内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="f8942-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="f8942-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="f8942-126">0x8004101c</span></span> | <span data-ttu-id="f8942-127">从基类继承属性。</span><span class="sxs-lookup"><span data-stu-id="f8942-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="f8942-128">属性是系统属性。</span><span class="sxs-lookup"><span data-stu-id="f8942-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f8942-129">0</span><span class="sxs-lookup"><span data-stu-id="f8942-129">0</span></span> | <span data-ttu-id="f8942-130">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="f8942-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="f8942-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="f8942-131">0x80041030</span></span> | <span data-ttu-id="f8942-132">删除当前类的替代默认值的函数。</span><span class="sxs-lookup"><span data-stu-id="f8942-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="f8942-133">父类中此属性的默认值已被 reactiviated。</span><span class="sxs-lookup"><span data-stu-id="f8942-133">The default value for this property in the parent class has been reactiviated.</span></span> | 

## <a name="remarks"></a><span data-ttu-id="f8942-134">备注</span><span class="sxs-lookup"><span data-stu-id="f8942-134">Remarks</span></span>

<span data-ttu-id="f8942-135">此函数包装对的调用[IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="f8942-135">This function wraps a call to the [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f8942-136">要求</span><span class="sxs-lookup"><span data-stu-id="f8942-136">Requirements</span></span>  
 <span data-ttu-id="f8942-137">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8942-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8942-138">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f8942-138">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f8942-139">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f8942-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8942-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8942-140">See also</span></span>  
[<span data-ttu-id="f8942-141">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="f8942-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
