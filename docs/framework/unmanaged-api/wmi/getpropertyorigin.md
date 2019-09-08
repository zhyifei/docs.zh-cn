---
title: GetPropertyOrigin 函数（非托管 API 参考）
description: GetPropertyOrigin 函数确定声明属性的类。
ms.date: 11/06/2017
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c2d0f23f3dd2d52f73f09c32d4e3118a9ed5ea3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798496"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="660aa-103">GetPropertyOrigin 函数</span><span class="sxs-lookup"><span data-stu-id="660aa-103">GetPropertyOrigin function</span></span>

<span data-ttu-id="660aa-104">确定声明方法的类。</span><span class="sxs-lookup"><span data-stu-id="660aa-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="660aa-105">语法</span><span class="sxs-lookup"><span data-stu-id="660aa-105">Syntax</span></span>

```cpp
HRESULT GetPropertyOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```

## <a name="parameters"></a><span data-ttu-id="660aa-106">参数</span><span class="sxs-lookup"><span data-stu-id="660aa-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="660aa-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="660aa-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="660aa-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="660aa-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`\
<span data-ttu-id="660aa-109">中正在请求其所属类的对象的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="660aa-109">[in] The name of the property for the object whose owning class is being requested.</span></span>

`pstrClassName`\
<span data-ttu-id="660aa-110">弄接收拥有属性的类的名称。</span><span class="sxs-lookup"><span data-stu-id="660aa-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="660aa-111">返回值</span><span class="sxs-lookup"><span data-stu-id="660aa-111">Return value</span></span>

<span data-ttu-id="660aa-112">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="660aa-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="660aa-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="660aa-113">Constant</span></span>  |<span data-ttu-id="660aa-114">值</span><span class="sxs-lookup"><span data-stu-id="660aa-114">Value</span></span>  |<span data-ttu-id="660aa-115">描述</span><span class="sxs-lookup"><span data-stu-id="660aa-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="660aa-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="660aa-116">0x80041001</span></span> | <span data-ttu-id="660aa-117">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="660aa-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="660aa-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="660aa-118">0x80041002</span></span> | <span data-ttu-id="660aa-119">找不到指定的属性。</span><span class="sxs-lookup"><span data-stu-id="660aa-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="660aa-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="660aa-120">0x80041008</span></span> | <span data-ttu-id="660aa-121">参数无效。</span><span class="sxs-lookup"><span data-stu-id="660aa-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="660aa-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="660aa-122">0x80041006</span></span> | <span data-ttu-id="660aa-123">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="660aa-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="660aa-124">0</span><span class="sxs-lookup"><span data-stu-id="660aa-124">0</span></span> | <span data-ttu-id="660aa-125">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="660aa-125">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="660aa-126">备注</span><span class="sxs-lookup"><span data-stu-id="660aa-126">Remarks</span></span>

<span data-ttu-id="660aa-127">此函数包装对[IWbemClassObject：： GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="660aa-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="660aa-128">由于类可以从一个或多个基类继承属性，因此开发人员通常需要确定定义给定方法的属性。</span><span class="sxs-lookup"><span data-stu-id="660aa-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="660aa-129">在`pstrClassName`调用函数之前，参数必须指向`BSTR`有效的，因为这是一个`out`参数; 在函数返回后，不释放此指针。</span><span class="sxs-lookup"><span data-stu-id="660aa-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="660aa-130">要求</span><span class="sxs-lookup"><span data-stu-id="660aa-130">Requirements</span></span>

<span data-ttu-id="660aa-131">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="660aa-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="660aa-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="660aa-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="660aa-133">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="660aa-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="660aa-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="660aa-134">See also</span></span>

- [<span data-ttu-id="660aa-135">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="660aa-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
