---
title: Beginenumeration 函数（非托管 API 参考）
description: Beginenumeration 函数终止枚举。
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b9fd1f094c8fb56c94421a07437aa25a3549c487
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132047"
---
# <a name="endenumeration-function"></a><span data-ttu-id="d796f-103">EndEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="d796f-103">EndEnumeration function</span></span>

<span data-ttu-id="d796f-104">终止使用对[endenumeration 函数](beginenumeration.md)的调用启动的枚举序列。</span><span class="sxs-lookup"><span data-stu-id="d796f-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d796f-105">语法</span><span class="sxs-lookup"><span data-stu-id="d796f-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="d796f-106">参数</span><span class="sxs-lookup"><span data-stu-id="d796f-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="d796f-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="d796f-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="d796f-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="d796f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="d796f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d796f-109">Return value</span></span>

<span data-ttu-id="d796f-110">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="d796f-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d796f-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="d796f-111">Constant</span></span>  |<span data-ttu-id="d796f-112">“值”</span><span class="sxs-lookup"><span data-stu-id="d796f-112">Value</span></span>  |<span data-ttu-id="d796f-113">描述</span><span class="sxs-lookup"><span data-stu-id="d796f-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="d796f-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d796f-114">0x80041001</span></span> | <span data-ttu-id="d796f-115">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="d796f-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d796f-116">0</span><span class="sxs-lookup"><span data-stu-id="d796f-116">0</span></span> | <span data-ttu-id="d796f-117">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="d796f-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="d796f-118">备注</span><span class="sxs-lookup"><span data-stu-id="d796f-118">Remarks</span></span>

<span data-ttu-id="d796f-119">此函数包装对[IWbemClassObject：： beginenumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="d796f-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="d796f-120">不需要调用 `EndEnumeration` 函数，但建议使用，因为它释放与枚举关联的资源。</span><span class="sxs-lookup"><span data-stu-id="d796f-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="d796f-121">但是，在启动下一个枚举或释放该对象时，将自动释放资源。</span><span class="sxs-lookup"><span data-stu-id="d796f-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="d796f-122">要求</span><span class="sxs-lookup"><span data-stu-id="d796f-122">Requirements</span></span>

<span data-ttu-id="d796f-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d796f-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d796f-124">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="d796f-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d796f-125">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d796f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d796f-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d796f-126">See also</span></span>

- [<span data-ttu-id="d796f-127">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="d796f-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
