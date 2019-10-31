---
title: QualifierSet_Get 函数（非托管 API 参考）
description: QualifierSet_Get 函数获取命名限定符。
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: dc09cd30c43647fa00cccc1dc00da4f8de367e84
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127275"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="c4885-103">QualifierSet_Get 函数</span><span class="sxs-lookup"><span data-stu-id="c4885-103">QualifierSet_Get function</span></span>
<span data-ttu-id="c4885-104">获取指定的命名限定符。</span><span class="sxs-lookup"><span data-stu-id="c4885-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c4885-105">语法</span><span class="sxs-lookup"><span data-stu-id="c4885-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="c4885-106">参数</span><span class="sxs-lookup"><span data-stu-id="c4885-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="c4885-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="c4885-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="c4885-108">中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="c4885-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="c4885-109">中请求其值的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="c4885-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="c4885-110">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="c4885-110">[in] Reserved.</span></span> <span data-ttu-id="c4885-111">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="c4885-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="c4885-112">弄如果成功，则为限定符的正确类型和值。</span><span class="sxs-lookup"><span data-stu-id="c4885-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="c4885-113">如果函数失败，则不会修改 `pVal` 指向的 `VARIANT`。</span><span class="sxs-lookup"><span data-stu-id="c4885-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="c4885-114">如果 `null`此参数，则忽略参数。</span><span class="sxs-lookup"><span data-stu-id="c4885-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="c4885-115">弄一个指向 LONG 的指针，它接收所请求限定符的限定符风格位。</span><span class="sxs-lookup"><span data-stu-id="c4885-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="c4885-116">如果不需要口味信息，可以 `null`此参数。</span><span class="sxs-lookup"><span data-stu-id="c4885-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="c4885-117">返回值</span><span class="sxs-lookup"><span data-stu-id="c4885-117">Return value</span></span>

<span data-ttu-id="c4885-118">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="c4885-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c4885-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="c4885-119">Constant</span></span>  |<span data-ttu-id="c4885-120">“值”</span><span class="sxs-lookup"><span data-stu-id="c4885-120">Value</span></span>  |<span data-ttu-id="c4885-121">描述</span><span class="sxs-lookup"><span data-stu-id="c4885-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c4885-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c4885-122">0x80041008</span></span> | <span data-ttu-id="c4885-123">参数无效。</span><span class="sxs-lookup"><span data-stu-id="c4885-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c4885-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c4885-124">0x80041002</span></span> | <span data-ttu-id="c4885-125">指定的限定符不存在。</span><span class="sxs-lookup"><span data-stu-id="c4885-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c4885-126">0</span><span class="sxs-lookup"><span data-stu-id="c4885-126">0</span></span> | <span data-ttu-id="c4885-127">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="c4885-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c4885-128">备注</span><span class="sxs-lookup"><span data-stu-id="c4885-128">Remarks</span></span>

<span data-ttu-id="c4885-129">此函数包装对[IWbemQualifierSet：： Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="c4885-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4885-130">要求</span><span class="sxs-lookup"><span data-stu-id="c4885-130">Requirements</span></span>  
 <span data-ttu-id="c4885-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4885-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4885-132">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="c4885-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c4885-133">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c4885-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4885-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4885-134">See also</span></span>

- [<span data-ttu-id="c4885-135">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="c4885-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
