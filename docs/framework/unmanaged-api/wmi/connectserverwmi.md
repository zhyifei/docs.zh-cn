---
title: ConnectServerWmi 函数（非托管 API 参考）
description: ConnectServerWmi 函数使用 DCOM 创建到 WMI 命名空间的连接。
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ebb268dcee877f4e9aea0c88852333897030dd1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798751"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="b113a-103">ConnectServerWmi 函数</span><span class="sxs-lookup"><span data-stu-id="b113a-103">ConnectServerWmi function</span></span>

<span data-ttu-id="b113a-104">通过 DCOM 创建到指定计算机上的 WMI 命名空间的连接。</span><span class="sxs-lookup"><span data-stu-id="b113a-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b113a-105">语法</span><span class="sxs-lookup"><span data-stu-id="b113a-105">Syntax</span></span>

```cpp
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel,
   [in] DWORD              authLevel
);
```

## <a name="parameters"></a><span data-ttu-id="b113a-106">参数</span><span class="sxs-lookup"><span data-stu-id="b113a-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="b113a-107">中指向有效`BSTR`的的指针，该指针包含正确的 WMI 命名空间的对象路径。</span><span class="sxs-lookup"><span data-stu-id="b113a-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="b113a-108">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="b113a-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="b113a-109">中指向包含用户名的有效`BSTR`的指针。</span><span class="sxs-lookup"><span data-stu-id="b113a-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="b113a-110">`null`值指示当前安全上下文。</span><span class="sxs-lookup"><span data-stu-id="b113a-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="b113a-111">如果用户来自不同于当前域的域， `strUser`还可以包含用反斜杠分隔的域和用户名。</span><span class="sxs-lookup"><span data-stu-id="b113a-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="b113a-112">`strUser`也可以是用户主体名称（UPN）格式，例如`userName@domainName`。</span><span class="sxs-lookup"><span data-stu-id="b113a-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="b113a-113">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="b113a-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="b113a-114">中指向包含密码的有效`BSTR`的指针。</span><span class="sxs-lookup"><span data-stu-id="b113a-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="b113a-115">`null`指示当前安全上下文。</span><span class="sxs-lookup"><span data-stu-id="b113a-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="b113a-116">空字符串（""）表示有效的零长度密码。</span><span class="sxs-lookup"><span data-stu-id="b113a-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="b113a-117">中指向有效`BSTR`的指针，该指针指示信息检索的正确区域设置。</span><span class="sxs-lookup"><span data-stu-id="b113a-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="b113a-118">对于 Microsoft 区域设置标识符，字符串的格式为 "MS\_*xxx*"，其中*xxx*是十六进制格式的字符串，用于指示区域设置标识符（LCID）。</span><span class="sxs-lookup"><span data-stu-id="b113a-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="b113a-119">如果指定了无效的区域设置，则方法`WBEM_E_INVALID_PARAMETER`将返回，但 Windows 7 除外，此时将使用服务器的默认区域设置。</span><span class="sxs-lookup"><span data-stu-id="b113a-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="b113a-120">如果为 "null1"，则使用当前区域设置。</span><span class="sxs-lookup"><span data-stu-id="b113a-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="b113a-121">中要传递给方法的`ConnectServerWmi`标志。</span><span class="sxs-lookup"><span data-stu-id="b113a-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="b113a-122">如果此参数的值为零（0），则仅在建立`ConnectServerWmi`与服务器的连接后才调用返回。</span><span class="sxs-lookup"><span data-stu-id="b113a-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="b113a-123">如果服务器中断，这可能导致应用程序不会无限期地响应。</span><span class="sxs-lookup"><span data-stu-id="b113a-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="b113a-124">其他有效值为：</span><span class="sxs-lookup"><span data-stu-id="b113a-124">The other valid values are:</span></span>

| <span data-ttu-id="b113a-125">返回的常量</span><span class="sxs-lookup"><span data-stu-id="b113a-125">Constant</span></span>  | <span data-ttu-id="b113a-126">值</span><span class="sxs-lookup"><span data-stu-id="b113a-126">Value</span></span>  | <span data-ttu-id="b113a-127">描述</span><span class="sxs-lookup"><span data-stu-id="b113a-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="b113a-128">0x40</span><span class="sxs-lookup"><span data-stu-id="b113a-128">0x40</span></span> | <span data-ttu-id="b113a-129">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="b113a-129">Reserved for internal use.</span></span> <span data-ttu-id="b113a-130">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="b113a-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="b113a-131">0x80</span><span class="sxs-lookup"><span data-stu-id="b113a-131">0x80</span></span> | <span data-ttu-id="b113a-132">`ConnectServerWmi`返回两分钟或更少的时间。</span><span class="sxs-lookup"><span data-stu-id="b113a-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="b113a-133">中用户的域名。</span><span class="sxs-lookup"><span data-stu-id="b113a-133">[in] The domain name of the user.</span></span> <span data-ttu-id="b113a-134">可以有下列值：</span><span class="sxs-lookup"><span data-stu-id="b113a-134">It can have the following values:</span></span>

| <span data-ttu-id="b113a-135">值</span><span class="sxs-lookup"><span data-stu-id="b113a-135">Value</span></span> | <span data-ttu-id="b113a-136">描述</span><span class="sxs-lookup"><span data-stu-id="b113a-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="b113a-137">空白</span><span class="sxs-lookup"><span data-stu-id="b113a-137">blank</span></span> | <span data-ttu-id="b113a-138">使用 NTLM 身份验证，并使用当前用户的 NTLM 域。</span><span class="sxs-lookup"><span data-stu-id="b113a-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="b113a-139">如果`strUser`指定域（建议位置），则不得在此处指定。</span><span class="sxs-lookup"><span data-stu-id="b113a-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="b113a-140">如果在这`WBEM_E_INVALID_PARAMETER`两个参数中指定了域，则该函数返回。</span><span class="sxs-lookup"><span data-stu-id="b113a-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="b113a-141">Kerberos：*主体名称*</span><span class="sxs-lookup"><span data-stu-id="b113a-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="b113a-142">使用 kerberos 身份验证，并且此参数包含 Kerberos 主体名称。</span><span class="sxs-lookup"><span data-stu-id="b113a-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="b113a-143">NTLMDOMAIN：*域名*</span><span class="sxs-lookup"><span data-stu-id="b113a-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="b113a-144">使用 NT LAN 管理器身份验证，此参数包含 NTLM 域名。</span><span class="sxs-lookup"><span data-stu-id="b113a-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="b113a-145">中此参数通常为`null`。</span><span class="sxs-lookup"><span data-stu-id="b113a-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="b113a-146">否则，它是指向一个或多个动态类提供程序所需的[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b113a-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="b113a-147">弄当函数返回时，将接收指向绑定到指定命名空间的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b113a-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="b113a-148">`null`如果出现错误，则将其设置为指向。</span><span class="sxs-lookup"><span data-stu-id="b113a-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="b113a-149">中模拟级别。</span><span class="sxs-lookup"><span data-stu-id="b113a-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="b113a-150">中授权级别。</span><span class="sxs-lookup"><span data-stu-id="b113a-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="b113a-151">返回值</span><span class="sxs-lookup"><span data-stu-id="b113a-151">Return value</span></span>

<span data-ttu-id="b113a-152">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="b113a-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b113a-153">返回的常量</span><span class="sxs-lookup"><span data-stu-id="b113a-153">Constant</span></span>  |<span data-ttu-id="b113a-154">值</span><span class="sxs-lookup"><span data-stu-id="b113a-154">Value</span></span>  |<span data-ttu-id="b113a-155">描述</span><span class="sxs-lookup"><span data-stu-id="b113a-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="b113a-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b113a-156">0x80041001</span></span> | <span data-ttu-id="b113a-157">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="b113a-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b113a-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b113a-158">0x80041008</span></span> | <span data-ttu-id="b113a-159">参数无效。</span><span class="sxs-lookup"><span data-stu-id="b113a-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b113a-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b113a-160">0x80041006</span></span> | <span data-ttu-id="b113a-161">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="b113a-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b113a-162">0</span><span class="sxs-lookup"><span data-stu-id="b113a-162">0</span></span> | <span data-ttu-id="b113a-163">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="b113a-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b113a-164">备注</span><span class="sxs-lookup"><span data-stu-id="b113a-164">Remarks</span></span>

<span data-ttu-id="b113a-165">此函数包装对[IWbemLocator：： ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="b113a-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="b113a-166">对于对默认命名空间的本地访问`strNetworkResource` ，可以是一个简单的对象路径： "root\default"\\或 ".\root\default"。</span><span class="sxs-lookup"><span data-stu-id="b113a-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="b113a-167">若要使用 COM 或 Microsoft 兼容的网络访问远程计算机上的默认命名空间，请包含计算机名称： "\\myserver\root\default"。</span><span class="sxs-lookup"><span data-stu-id="b113a-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="b113a-168">计算机名称也可以是 DNS 名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b113a-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="b113a-169">此`ConnectServerWmi`函数还可以使用 ipv6 地址与运行 ipv6 的计算机连接。</span><span class="sxs-lookup"><span data-stu-id="b113a-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="b113a-170">`strUser`不能为空字符串。</span><span class="sxs-lookup"><span data-stu-id="b113a-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="b113a-171">如果在中`strAuthority`指定了域，则它也不能包含在`strUser`中，或者该函数`WBEM_E_INVALID_PARAMETER`返回。</span><span class="sxs-lookup"><span data-stu-id="b113a-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="b113a-172">要求</span><span class="sxs-lookup"><span data-stu-id="b113a-172">Requirements</span></span>

 <span data-ttu-id="b113a-173">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b113a-173">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="b113a-174">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b113a-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="b113a-175">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b113a-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b113a-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="b113a-176">See also</span></span>

- [<span data-ttu-id="b113a-177">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="b113a-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
