---
title: QualifierSet_Get函数（非托管 API 引用）
description: QualifierSet_Get函数获取命名的限定符。
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
ms.openlocfilehash: 2f4e2d4518e01f3415b8f17ce5778dd98b2a45c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174883"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="579da-103">QualifierSet_Get 函数</span><span class="sxs-lookup"><span data-stu-id="579da-103">QualifierSet_Get function</span></span>
<span data-ttu-id="579da-104">获取指定的命名限定符。</span><span class="sxs-lookup"><span data-stu-id="579da-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="579da-105">语法</span><span class="sxs-lookup"><span data-stu-id="579da-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="579da-106">parameters</span><span class="sxs-lookup"><span data-stu-id="579da-106">Parameters</span></span>

<span data-ttu-id="579da-107">`vFunc`[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="579da-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="579da-108">`ptr`[在]指向[IWbem 限定符集实例的](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)指针。</span><span class="sxs-lookup"><span data-stu-id="579da-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="579da-109">`wszName`[在]请求其值的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="579da-109">`wszName` [in] The name of the qualifier whose value is requested.</span></span>

<span data-ttu-id="579da-110">`lFlags`[在]保留。</span><span class="sxs-lookup"><span data-stu-id="579da-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="579da-111">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="579da-111">This parameter must be 0.</span></span>

<span data-ttu-id="579da-112">`pVal`[出]成功后，限定符的正确类型和值。</span><span class="sxs-lookup"><span data-stu-id="579da-112">`pVal` [out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="579da-113">如果函数失败，`VARIANT`则 不修改`pVal`指向 的 。</span><span class="sxs-lookup"><span data-stu-id="579da-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="579da-114">如果此参数为`null`，则忽略该参数。</span><span class="sxs-lookup"><span data-stu-id="579da-114">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="579da-115">`plFlavor`[出]指向 LONG 的指针，该指针接收请求的限定符的限定符的限定符风味位。</span><span class="sxs-lookup"><span data-stu-id="579da-115">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="579da-116">如果不需要风味信息，则此参数可以是`null`。</span><span class="sxs-lookup"><span data-stu-id="579da-116">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="579da-117">返回值</span><span class="sxs-lookup"><span data-stu-id="579da-117">Return value</span></span>

<span data-ttu-id="579da-118">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="579da-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="579da-119">一直</span><span class="sxs-lookup"><span data-stu-id="579da-119">Constant</span></span>  |<span data-ttu-id="579da-120">值</span><span class="sxs-lookup"><span data-stu-id="579da-120">Value</span></span>  |<span data-ttu-id="579da-121">说明</span><span class="sxs-lookup"><span data-stu-id="579da-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="579da-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="579da-122">0x80041008</span></span> | <span data-ttu-id="579da-123">参数无效。</span><span class="sxs-lookup"><span data-stu-id="579da-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="579da-124">0 x80041002</span><span class="sxs-lookup"><span data-stu-id="579da-124">0x80041002</span></span> | <span data-ttu-id="579da-125">指定的限定符不存在。</span><span class="sxs-lookup"><span data-stu-id="579da-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="579da-126">0</span><span class="sxs-lookup"><span data-stu-id="579da-126">0</span></span> | <span data-ttu-id="579da-127">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="579da-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="579da-128">备注</span><span class="sxs-lookup"><span data-stu-id="579da-128">Remarks</span></span>

<span data-ttu-id="579da-129">此函数包装对[IWbem 限定符集的调用：：get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)方法。</span><span class="sxs-lookup"><span data-stu-id="579da-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="579da-130">要求</span><span class="sxs-lookup"><span data-stu-id="579da-130">Requirements</span></span>  
 <span data-ttu-id="579da-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="579da-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="579da-132">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="579da-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="579da-133">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="579da-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="579da-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="579da-134">See also</span></span>

- [<span data-ttu-id="579da-135">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="579da-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
