---
title: GetMethodOrigin 函数（非托管 API 参考）
description: GetMethodOrigin 函数确定声明方法的类。
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cea7251353dae093f64448c8d84157917fa74c5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798556"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="42a67-103">GetMethodOrigin 函数</span><span class="sxs-lookup"><span data-stu-id="42a67-103">GetMethodOrigin function</span></span>
<span data-ttu-id="42a67-104">确定声明方法的类。</span><span class="sxs-lookup"><span data-stu-id="42a67-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="42a67-105">语法</span><span class="sxs-lookup"><span data-stu-id="42a67-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="42a67-106">参数</span><span class="sxs-lookup"><span data-stu-id="42a67-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="42a67-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="42a67-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="42a67-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="42a67-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="42a67-109">中正在请求其所属类的对象的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="42a67-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="42a67-110">弄接收拥有方法的类的名称。</span><span class="sxs-lookup"><span data-stu-id="42a67-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="42a67-111">返回值</span><span class="sxs-lookup"><span data-stu-id="42a67-111">Return value</span></span>

<span data-ttu-id="42a67-112">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="42a67-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="42a67-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="42a67-113">Constant</span></span>  |<span data-ttu-id="42a67-114">值</span><span class="sxs-lookup"><span data-stu-id="42a67-114">Value</span></span>  |<span data-ttu-id="42a67-115">描述</span><span class="sxs-lookup"><span data-stu-id="42a67-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="42a67-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="42a67-116">0x80041002</span></span> | <span data-ttu-id="42a67-117">找不到指定的方法。</span><span class="sxs-lookup"><span data-stu-id="42a67-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="42a67-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="42a67-118">0x80041008</span></span> | <span data-ttu-id="42a67-119">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="42a67-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="42a67-120">0</span><span class="sxs-lookup"><span data-stu-id="42a67-120">0</span></span> | <span data-ttu-id="42a67-121">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="42a67-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="42a67-122">备注</span><span class="sxs-lookup"><span data-stu-id="42a67-122">Remarks</span></span>

<span data-ttu-id="42a67-123">此函数包装对[IWbemClassObject：： GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="42a67-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="42a67-124">由于类可以从一个或多个基类继承方法，因此开发人员通常需要确定定义给定方法的类。</span><span class="sxs-lookup"><span data-stu-id="42a67-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="42a67-125">在`pstrClassName`调用函数之前，参数必须指向`BSTR`有效的，因为这是一个`out`参数; 在函数返回后，不释放此指针。</span><span class="sxs-lookup"><span data-stu-id="42a67-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="42a67-126">要求</span><span class="sxs-lookup"><span data-stu-id="42a67-126">Requirements</span></span>  
<span data-ttu-id="42a67-127">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42a67-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a67-128">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="42a67-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="42a67-129">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42a67-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a67-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="42a67-130">See also</span></span>

- [<span data-ttu-id="42a67-131">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="42a67-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
