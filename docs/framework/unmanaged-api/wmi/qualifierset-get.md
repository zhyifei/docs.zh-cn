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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 751694985248346187eff016ef7a4a8054cb1212
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798314"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="3f59e-103">QualifierSet_Get 函数</span><span class="sxs-lookup"><span data-stu-id="3f59e-103">QualifierSet_Get function</span></span>
<span data-ttu-id="3f59e-104">获取指定的命名限定符。</span><span class="sxs-lookup"><span data-stu-id="3f59e-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3f59e-105">语法</span><span class="sxs-lookup"><span data-stu-id="3f59e-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="3f59e-106">参数</span><span class="sxs-lookup"><span data-stu-id="3f59e-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="3f59e-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="3f59e-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="3f59e-108">中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="3f59e-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="3f59e-109">中请求其值的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="3f59e-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="3f59e-110">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="3f59e-110">[in] Reserved.</span></span> <span data-ttu-id="3f59e-111">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="3f59e-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="3f59e-112">弄如果成功，则为限定符的正确类型和值。</span><span class="sxs-lookup"><span data-stu-id="3f59e-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="3f59e-113">如果函数失败， `VARIANT`则不会修改指向的。 `pVal`</span><span class="sxs-lookup"><span data-stu-id="3f59e-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="3f59e-114">如果此参数为`null`，则忽略参数。</span><span class="sxs-lookup"><span data-stu-id="3f59e-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="3f59e-115">弄一个指向 LONG 的指针，它接收所请求限定符的限定符风格位。</span><span class="sxs-lookup"><span data-stu-id="3f59e-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="3f59e-116">如果不需要口味信息，此参数可以为`null`。</span><span class="sxs-lookup"><span data-stu-id="3f59e-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="3f59e-117">返回值</span><span class="sxs-lookup"><span data-stu-id="3f59e-117">Return value</span></span>

<span data-ttu-id="3f59e-118">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="3f59e-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3f59e-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="3f59e-119">Constant</span></span>  |<span data-ttu-id="3f59e-120">值</span><span class="sxs-lookup"><span data-stu-id="3f59e-120">Value</span></span>  |<span data-ttu-id="3f59e-121">描述</span><span class="sxs-lookup"><span data-stu-id="3f59e-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3f59e-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3f59e-122">0x80041008</span></span> | <span data-ttu-id="3f59e-123">参数无效。</span><span class="sxs-lookup"><span data-stu-id="3f59e-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="3f59e-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3f59e-124">0x80041002</span></span> | <span data-ttu-id="3f59e-125">指定的限定符不存在。</span><span class="sxs-lookup"><span data-stu-id="3f59e-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3f59e-126">0</span><span class="sxs-lookup"><span data-stu-id="3f59e-126">0</span></span> | <span data-ttu-id="3f59e-127">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="3f59e-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3f59e-128">备注</span><span class="sxs-lookup"><span data-stu-id="3f59e-128">Remarks</span></span>

<span data-ttu-id="3f59e-129">此函数包装对[IWbemQualifierSet：： Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="3f59e-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3f59e-130">要求</span><span class="sxs-lookup"><span data-stu-id="3f59e-130">Requirements</span></span>  
 <span data-ttu-id="3f59e-131">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f59e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f59e-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3f59e-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3f59e-133">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3f59e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f59e-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f59e-134">See also</span></span>

- [<span data-ttu-id="3f59e-135">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="3f59e-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
