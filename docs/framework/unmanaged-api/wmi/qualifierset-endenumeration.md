---
title: QualifierSet_EndEnumeration 函数 （非托管 API 参考）
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
ms.openlocfilehash: be2dfd6bb521dee14afd3728bdd9c446cb779e85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598839"
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="74ba6-103">QualifierSet_EndEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="74ba6-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="74ba6-104">终止通过调用开始枚举[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)函数。</span><span class="sxs-lookup"><span data-stu-id="74ba6-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="74ba6-105">语法</span><span class="sxs-lookup"><span data-stu-id="74ba6-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="74ba6-106">参数</span><span class="sxs-lookup"><span data-stu-id="74ba6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="74ba6-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="74ba6-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="74ba6-108">[in]一个指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例。</span><span class="sxs-lookup"><span data-stu-id="74ba6-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="74ba6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="74ba6-109">Return value</span></span>

<span data-ttu-id="74ba6-110">此函数返回的以下值中定义*WbemCli.h*标头文件，也可以将其定义为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="74ba6-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="74ba6-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="74ba6-111">Constant</span></span>  |<span data-ttu-id="74ba6-112">“值”</span><span class="sxs-lookup"><span data-stu-id="74ba6-112">Value</span></span>  |<span data-ttu-id="74ba6-113">Description</span><span class="sxs-lookup"><span data-stu-id="74ba6-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="74ba6-114">0</span><span class="sxs-lookup"><span data-stu-id="74ba6-114">0</span></span> | <span data-ttu-id="74ba6-115">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="74ba6-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="74ba6-116">备注</span><span class="sxs-lookup"><span data-stu-id="74ba6-116">Remarks</span></span>

<span data-ttu-id="74ba6-117">此函数包装对的调用[IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration)方法。</span><span class="sxs-lookup"><span data-stu-id="74ba6-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="74ba6-118">此调用是建议这样做，但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="74ba6-118">This call is recommended, but not required.</span></span> <span data-ttu-id="74ba6-119">它立即释放与枚举关联的资源。</span><span class="sxs-lookup"><span data-stu-id="74ba6-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="74ba6-120">要求</span><span class="sxs-lookup"><span data-stu-id="74ba6-120">Requirements</span></span>  

<span data-ttu-id="74ba6-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74ba6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="74ba6-122">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="74ba6-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="74ba6-123">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="74ba6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ba6-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="74ba6-124">See also</span></span>

- [<span data-ttu-id="74ba6-125">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="74ba6-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
