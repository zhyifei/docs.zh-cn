---
title: 克隆EnumWbem类对象函数（非托管 API 引用）
description: CloneEnumWbemClassObject 函数创建枚举器的逻辑副本。
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
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175013"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="33cdc-103">CloneEnumWbemClassObject 函数</span><span class="sxs-lookup"><span data-stu-id="33cdc-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="33cdc-104">制作枚举器的逻辑副本，并保留其在枚举中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="33cdc-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="33cdc-105">语法</span><span class="sxs-lookup"><span data-stu-id="33cdc-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="33cdc-106">parameters</span><span class="sxs-lookup"><span data-stu-id="33cdc-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="33cdc-107">[出]接收指向新[IEnumWbem ClassObject 的指针](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)。</span><span class="sxs-lookup"><span data-stu-id="33cdc-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="33cdc-108">[在]授权级别。</span><span class="sxs-lookup"><span data-stu-id="33cdc-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="33cdc-109">[在]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="33cdc-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="33cdc-110">[出]指向要克隆的[IEnumWbemClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="33cdc-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="33cdc-111">[在]用户名。</span><span class="sxs-lookup"><span data-stu-id="33cdc-111">[in] The user name.</span></span> <span data-ttu-id="33cdc-112">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="33cdc-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="33cdc-113">[在]密码。</span><span class="sxs-lookup"><span data-stu-id="33cdc-113">[in] The password.</span></span> <span data-ttu-id="33cdc-114">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="33cdc-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="33cdc-115">[在]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="33cdc-115">[in] The domain name of the user.</span></span> <span data-ttu-id="33cdc-116">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="33cdc-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="33cdc-117">返回值</span><span class="sxs-lookup"><span data-stu-id="33cdc-117">Return value</span></span>

<span data-ttu-id="33cdc-118">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="33cdc-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="33cdc-119">一直</span><span class="sxs-lookup"><span data-stu-id="33cdc-119">Constant</span></span>  |<span data-ttu-id="33cdc-120">值</span><span class="sxs-lookup"><span data-stu-id="33cdc-120">Value</span></span>  |<span data-ttu-id="33cdc-121">说明</span><span class="sxs-lookup"><span data-stu-id="33cdc-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="33cdc-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="33cdc-122">0x80041001</span></span> | <span data-ttu-id="33cdc-123">出现了一个普遍的失败。</span><span class="sxs-lookup"><span data-stu-id="33cdc-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="33cdc-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="33cdc-124">0x80041008</span></span> | <span data-ttu-id="33cdc-125">参数无效。</span><span class="sxs-lookup"><span data-stu-id="33cdc-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="33cdc-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="33cdc-126">0x80041006</span></span> | <span data-ttu-id="33cdc-127">没有足够的内存可用于完成操作。</span><span class="sxs-lookup"><span data-stu-id="33cdc-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="33cdc-128">0 x80041015</span><span class="sxs-lookup"><span data-stu-id="33cdc-128">0x80041015</span></span> | <span data-ttu-id="33cdc-129">当前进程和 WMI 之间的远程过程调用 （RPC） 链路已失败。</span><span class="sxs-lookup"><span data-stu-id="33cdc-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="33cdc-130">0</span><span class="sxs-lookup"><span data-stu-id="33cdc-130">0</span></span> | <span data-ttu-id="33cdc-131">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="33cdc-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="33cdc-132">备注</span><span class="sxs-lookup"><span data-stu-id="33cdc-132">Remarks</span></span>

<span data-ttu-id="33cdc-133">此函数包装对[IEnumWbem ClassObject：：clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="33cdc-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="33cdc-134">此方法仅进行"尽力"复制。</span><span class="sxs-lookup"><span data-stu-id="33cdc-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="33cdc-135">由于许多 CIM 对象的动态性质，新的枚举器可能不会枚举与源枚举器相同的对象集。</span><span class="sxs-lookup"><span data-stu-id="33cdc-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="33cdc-136">如果函数调用失败，您可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="33cdc-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="33cdc-137">示例</span><span class="sxs-lookup"><span data-stu-id="33cdc-137">Example</span></span>

<span data-ttu-id="33cdc-138">例如，请参阅[IEnumWbem 类对象：：克隆](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)方法。</span><span class="sxs-lookup"><span data-stu-id="33cdc-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="33cdc-139">要求</span><span class="sxs-lookup"><span data-stu-id="33cdc-139">Requirements</span></span>
 <span data-ttu-id="33cdc-140">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33cdc-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="33cdc-141">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="33cdc-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="33cdc-142">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="33cdc-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="33cdc-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33cdc-143">See also</span></span>

- [<span data-ttu-id="33cdc-144">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="33cdc-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
