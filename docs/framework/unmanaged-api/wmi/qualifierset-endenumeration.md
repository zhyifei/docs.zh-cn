---
title: QualifierSet_EndEnumeration 函数（非托管 API 参考）
description: QualifierSet_EndEnumeration 函数终止枚举。
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5a817174ec4c4e4407c19bb1d6d2d852d86dd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798317"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="00972-103">QualifierSet_EndEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="00972-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="00972-104">使用对[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)函数的调用终止已开始的枚举。</span><span class="sxs-lookup"><span data-stu-id="00972-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="00972-105">语法</span><span class="sxs-lookup"><span data-stu-id="00972-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="00972-106">参数</span><span class="sxs-lookup"><span data-stu-id="00972-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="00972-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="00972-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="00972-108">中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="00972-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="00972-109">返回值</span><span class="sxs-lookup"><span data-stu-id="00972-109">Return value</span></span>

<span data-ttu-id="00972-110">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将其定义为常量：</span><span class="sxs-lookup"><span data-stu-id="00972-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="00972-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="00972-111">Constant</span></span>  |<span data-ttu-id="00972-112">值</span><span class="sxs-lookup"><span data-stu-id="00972-112">Value</span></span>  |<span data-ttu-id="00972-113">Description</span><span class="sxs-lookup"><span data-stu-id="00972-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="00972-114">0</span><span class="sxs-lookup"><span data-stu-id="00972-114">0</span></span> | <span data-ttu-id="00972-115">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="00972-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="00972-116">备注</span><span class="sxs-lookup"><span data-stu-id="00972-116">Remarks</span></span>

<span data-ttu-id="00972-117">此函数包装对[IWbemQualifierSet：： beginenumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="00972-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="00972-118">此调用是推荐的，但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="00972-118">This call is recommended, but not required.</span></span> <span data-ttu-id="00972-119">它会立即释放与枚举关联的资源。</span><span class="sxs-lookup"><span data-stu-id="00972-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="00972-120">要求</span><span class="sxs-lookup"><span data-stu-id="00972-120">Requirements</span></span>  

<span data-ttu-id="00972-121">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00972-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="00972-122">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="00972-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="00972-123">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="00972-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00972-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="00972-124">See also</span></span>

- [<span data-ttu-id="00972-125">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="00972-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
