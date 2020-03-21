---
title: 祝福IWbem服务功能（非托管 API 引用）
description: 祝福IWbem服务功能指示用户凭据是否允许访问 IWbemServices 类。
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 4b15af840cc00b3ec261604db4f3625c6b975d3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176859"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="881c8-103">BlessIWbemServices 函数</span><span class="sxs-lookup"><span data-stu-id="881c8-103">BlessIWbemServices function</span></span>
<span data-ttu-id="881c8-104">指示用户凭据是否允许访问指定的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)类。</span><span class="sxs-lookup"><span data-stu-id="881c8-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="881c8-105">语法</span><span class="sxs-lookup"><span data-stu-id="881c8-105">Syntax</span></span>  
  
```cpp
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="881c8-106">parameters</span><span class="sxs-lookup"><span data-stu-id="881c8-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="881c8-107">[在]指向需要权限的[IWbem 服务](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="881c8-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`\
<span data-ttu-id="881c8-108">[在]用户名。</span><span class="sxs-lookup"><span data-stu-id="881c8-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="881c8-109">[在]与`strUser`关联的密码。</span><span class="sxs-lookup"><span data-stu-id="881c8-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="881c8-110">[在]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="881c8-110">[in] The domain name of the user.</span></span> <span data-ttu-id="881c8-111">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="881c8-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="881c8-112">[在]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="881c8-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="881c8-113">[在]授权级别。</span><span class="sxs-lookup"><span data-stu-id="881c8-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="881c8-114">返回值</span><span class="sxs-lookup"><span data-stu-id="881c8-114">Return value</span></span>

<span data-ttu-id="881c8-115">此函数返回的以下值在*WinError.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="881c8-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="881c8-116">一直</span><span class="sxs-lookup"><span data-stu-id="881c8-116">Constant</span></span>  |<span data-ttu-id="881c8-117">值</span><span class="sxs-lookup"><span data-stu-id="881c8-117">Value</span></span>  |<span data-ttu-id="881c8-118">说明</span><span class="sxs-lookup"><span data-stu-id="881c8-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="881c8-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="881c8-119">0x80070057</span></span> | <span data-ttu-id="881c8-120">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="881c8-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="881c8-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="881c8-121">0x80004003</span></span> | <span data-ttu-id="881c8-122">`pIWbemServices` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="881c8-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="881c8-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="881c8-123">0x80000008</span></span> | <span data-ttu-id="881c8-124">发生了未知错误。</span><span class="sxs-lookup"><span data-stu-id="881c8-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="881c8-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="881c8-125">0x80000002</span></span> | <span data-ttu-id="881c8-126">可用内存不足以执行操作。</span><span class="sxs-lookup"><span data-stu-id="881c8-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="881c8-127">0</span><span class="sxs-lookup"><span data-stu-id="881c8-127">0</span></span> | <span data-ttu-id="881c8-128">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="881c8-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="881c8-129">要求</span><span class="sxs-lookup"><span data-stu-id="881c8-129">Requirements</span></span>  

 <span data-ttu-id="881c8-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="881c8-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="881c8-131">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="881c8-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="881c8-132">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="881c8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="881c8-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="881c8-133">See also</span></span>

- [<span data-ttu-id="881c8-134">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="881c8-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
