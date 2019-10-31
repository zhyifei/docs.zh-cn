---
title: BlessIWbemServicesObject 函数（非托管 API 参考）
description: BlessIWbemServicesObject 函数指示用户凭据是否允许访问 IWbemServices 对象
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f77ff394668a235dd63cf0cddf71ea418a28125b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141682"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="5806f-103">BlessIWbemServicesObject 函数</span><span class="sxs-lookup"><span data-stu-id="5806f-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="5806f-104">指示用户凭据是否允许访问指定的[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)对象。</span><span class="sxs-lookup"><span data-stu-id="5806f-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="5806f-105">语法</span><span class="sxs-lookup"><span data-stu-id="5806f-105">Syntax</span></span>

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="5806f-106">参数</span><span class="sxs-lookup"><span data-stu-id="5806f-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="5806f-107">中指向 WMI 服务对象的指针。</span><span class="sxs-lookup"><span data-stu-id="5806f-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="5806f-108">中用户名。</span><span class="sxs-lookup"><span data-stu-id="5806f-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="5806f-109">中与 `strUser`关联的密码。</span><span class="sxs-lookup"><span data-stu-id="5806f-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="5806f-110">中用户的域名。</span><span class="sxs-lookup"><span data-stu-id="5806f-110">[in] The domain name of the user.</span></span> <span data-ttu-id="5806f-111">有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。</span><span class="sxs-lookup"><span data-stu-id="5806f-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="5806f-112">中模拟级别。</span><span class="sxs-lookup"><span data-stu-id="5806f-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="5806f-113">中授权级别。</span><span class="sxs-lookup"><span data-stu-id="5806f-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="5806f-114">返回值</span><span class="sxs-lookup"><span data-stu-id="5806f-114">Return value</span></span>

<span data-ttu-id="5806f-115">此函数返回的以下值是在*winerror.h*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="5806f-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5806f-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="5806f-116">Constant</span></span>  |<span data-ttu-id="5806f-117">“值”</span><span class="sxs-lookup"><span data-stu-id="5806f-117">Value</span></span>  |<span data-ttu-id="5806f-118">描述</span><span class="sxs-lookup"><span data-stu-id="5806f-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="5806f-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="5806f-119">0x80070057</span></span> | <span data-ttu-id="5806f-120">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="5806f-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="5806f-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="5806f-121">0x80004003</span></span> | <span data-ttu-id="5806f-122">`pIWbemServices` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="5806f-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="5806f-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="5806f-123">0x80000008</span></span> | <span data-ttu-id="5806f-124">发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="5806f-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="5806f-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="5806f-125">0x80000002</span></span> | <span data-ttu-id="5806f-126">内存不足，无法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5806f-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="5806f-127">0</span><span class="sxs-lookup"><span data-stu-id="5806f-127">0</span></span> | <span data-ttu-id="5806f-128">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="5806f-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="5806f-129">要求</span><span class="sxs-lookup"><span data-stu-id="5806f-129">Requirements</span></span>

 <span data-ttu-id="5806f-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5806f-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="5806f-131">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="5806f-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="5806f-132">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5806f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5806f-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="5806f-133">See also</span></span>

- [<span data-ttu-id="5806f-134">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="5806f-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
