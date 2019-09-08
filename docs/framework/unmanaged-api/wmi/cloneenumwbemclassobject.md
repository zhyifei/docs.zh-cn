---
title: CloneEnumWbemClassObject 函数（非托管 API 参考）
description: CloneEnumWbemClassObject 函数生成枚举器的逻辑副本。
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1605314f94fd82d2a2cd7be105dde9e273f607bc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798695"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="2814e-103">CloneEnumWbemClassObject 函数</span><span class="sxs-lookup"><span data-stu-id="2814e-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="2814e-104">制作枚举器的逻辑副本，并保留其在枚举中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="2814e-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="2814e-105">语法</span><span class="sxs-lookup"><span data-stu-id="2814e-105">Syntax</span></span>

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```

## <a name="parameters"></a><span data-ttu-id="2814e-106">参数</span><span class="sxs-lookup"><span data-stu-id="2814e-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="2814e-107">弄接收指向新[IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="2814e-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="2814e-108">中授权级别。</span><span class="sxs-lookup"><span data-stu-id="2814e-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="2814e-109">中模拟级别。</span><span class="sxs-lookup"><span data-stu-id="2814e-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="2814e-110">弄指向要克隆的[IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="2814e-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="2814e-111">中用户名。</span><span class="sxs-lookup"><span data-stu-id="2814e-111">[in] The user name.</span></span> <span data-ttu-id="2814e-112">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2814e-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="2814e-113">中密码。</span><span class="sxs-lookup"><span data-stu-id="2814e-113">[in] The password.</span></span> <span data-ttu-id="2814e-114">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2814e-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="2814e-115">`strAuthority`\ [in] 用户的域名。</span><span class="sxs-lookup"><span data-stu-id="2814e-115">`strAuthority`\ [in] The domain name of the user.</span></span> <span data-ttu-id="2814e-116">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2814e-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="2814e-117">返回值</span><span class="sxs-lookup"><span data-stu-id="2814e-117">Return value</span></span>

<span data-ttu-id="2814e-118">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="2814e-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2814e-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="2814e-119">Constant</span></span>  |<span data-ttu-id="2814e-120">值</span><span class="sxs-lookup"><span data-stu-id="2814e-120">Value</span></span>  |<span data-ttu-id="2814e-121">描述</span><span class="sxs-lookup"><span data-stu-id="2814e-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="2814e-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="2814e-122">0x80041001</span></span> | <span data-ttu-id="2814e-123">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="2814e-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2814e-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="2814e-124">0x80041008</span></span> | <span data-ttu-id="2814e-125">参数无效。</span><span class="sxs-lookup"><span data-stu-id="2814e-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2814e-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="2814e-126">0x80041006</span></span> | <span data-ttu-id="2814e-127">没有足够的可用内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="2814e-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="2814e-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="2814e-128">0x80041015</span></span> | <span data-ttu-id="2814e-129">当前进程与 WMI 之间的远程过程调用（RPC）链接失败。</span><span class="sxs-lookup"><span data-stu-id="2814e-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="2814e-130">0</span><span class="sxs-lookup"><span data-stu-id="2814e-130">0</span></span> | <span data-ttu-id="2814e-131">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="2814e-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="2814e-132">备注</span><span class="sxs-lookup"><span data-stu-id="2814e-132">Remarks</span></span>

<span data-ttu-id="2814e-133">此函数包装对[IEnumWbemClassObject：： Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="2814e-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="2814e-134">此方法仅进行 "最大努力" 复制。</span><span class="sxs-lookup"><span data-stu-id="2814e-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="2814e-135">由于很多 CIM 对象的动态性质，新枚举器可能不会枚举与源枚举器相同的一组对象。</span><span class="sxs-lookup"><span data-stu-id="2814e-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="2814e-136">如果函数调用失败，可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="2814e-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="2814e-137">示例</span><span class="sxs-lookup"><span data-stu-id="2814e-137">Example</span></span>

<span data-ttu-id="2814e-138">有关示例，请参阅[IEnumWbemClassObject：： Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)方法。</span><span class="sxs-lookup"><span data-stu-id="2814e-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2814e-139">要求</span><span class="sxs-lookup"><span data-stu-id="2814e-139">Requirements</span></span>
 <span data-ttu-id="2814e-140">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2814e-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="2814e-141">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2814e-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="2814e-142">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2814e-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2814e-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="2814e-143">See also</span></span>

- [<span data-ttu-id="2814e-144">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="2814e-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
