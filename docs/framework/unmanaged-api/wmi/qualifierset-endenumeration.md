---
title: QualifierSet_EndEnumeration函数（非托管 API 引用）
description: QualifierSet_EndEnumeration函数终止枚举。
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
ms.openlocfilehash: c606580ff2e02c5659c14b134b1a17a65651952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176742"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="8feef-103">QualifierSet_EndEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="8feef-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="8feef-104">终止从调用[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)函数开始的枚举。</span><span class="sxs-lookup"><span data-stu-id="8feef-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8feef-105">语法</span><span class="sxs-lookup"><span data-stu-id="8feef-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="8feef-106">parameters</span><span class="sxs-lookup"><span data-stu-id="8feef-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8feef-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="8feef-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="8feef-108">`ptr`[在]指向[IWbem 限定符集实例的](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)指针。</span><span class="sxs-lookup"><span data-stu-id="8feef-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="8feef-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8feef-109">Return value</span></span>

<span data-ttu-id="8feef-110">此函数返回的以下值在*WbemCli.h*标头文件中定义，也可以将其定义为代码中的常量：</span><span class="sxs-lookup"><span data-stu-id="8feef-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="8feef-111">一直</span><span class="sxs-lookup"><span data-stu-id="8feef-111">Constant</span></span>  |<span data-ttu-id="8feef-112">值</span><span class="sxs-lookup"><span data-stu-id="8feef-112">Value</span></span>  |<span data-ttu-id="8feef-113">说明</span><span class="sxs-lookup"><span data-stu-id="8feef-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8feef-114">0</span><span class="sxs-lookup"><span data-stu-id="8feef-114">0</span></span> | <span data-ttu-id="8feef-115">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="8feef-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8feef-116">备注</span><span class="sxs-lookup"><span data-stu-id="8feef-116">Remarks</span></span>

<span data-ttu-id="8feef-117">此函数包装对[IWbem 限定符集：：结束枚举方法的](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration)调用。</span><span class="sxs-lookup"><span data-stu-id="8feef-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="8feef-118">建议使用此调用，但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="8feef-118">This call is recommended, but not required.</span></span> <span data-ttu-id="8feef-119">它立即释放与枚举关联的资源。</span><span class="sxs-lookup"><span data-stu-id="8feef-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="8feef-120">要求</span><span class="sxs-lookup"><span data-stu-id="8feef-120">Requirements</span></span>  

<span data-ttu-id="8feef-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8feef-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="8feef-122">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8feef-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="8feef-123">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8feef-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8feef-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8feef-124">See also</span></span>

- [<span data-ttu-id="8feef-125">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="8feef-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
