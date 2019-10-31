---
title: ICorDebugVariableHome：： GetArgumentIndex 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 86b2815c6f95c674c49bba7455e8497192bd8bac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125142"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="86f07-102">ICorDebugVariableHome：： GetArgumentIndex 方法</span><span class="sxs-lookup"><span data-stu-id="86f07-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="86f07-103">获取函数参数的索引。</span><span class="sxs-lookup"><span data-stu-id="86f07-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="86f07-104">语法</span><span class="sxs-lookup"><span data-stu-id="86f07-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="86f07-105">参数</span><span class="sxs-lookup"><span data-stu-id="86f07-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="86f07-106">弄指向参数索引的指针。</span><span class="sxs-lookup"><span data-stu-id="86f07-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="86f07-107">返回值</span><span class="sxs-lookup"><span data-stu-id="86f07-107">Return Value</span></span>

<span data-ttu-id="86f07-108">方法返回以下值。</span><span class="sxs-lookup"><span data-stu-id="86f07-108">The method returns the following values.</span></span>

|<span data-ttu-id="86f07-109">“值”</span><span class="sxs-lookup"><span data-stu-id="86f07-109">Value</span></span>|<span data-ttu-id="86f07-110">描述</span><span class="sxs-lookup"><span data-stu-id="86f07-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="86f07-111">方法调用返回有效的参数索引。</span><span class="sxs-lookup"><span data-stu-id="86f07-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="86f07-112">当前[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)实例表示局部变量。</span><span class="sxs-lookup"><span data-stu-id="86f07-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="86f07-113">备注</span><span class="sxs-lookup"><span data-stu-id="86f07-113">Remarks</span></span>

<span data-ttu-id="86f07-114">参数索引可用于检索此参数的元数据。</span><span class="sxs-lookup"><span data-stu-id="86f07-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="86f07-115">要求</span><span class="sxs-lookup"><span data-stu-id="86f07-115">Requirements</span></span>

<span data-ttu-id="86f07-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86f07-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="86f07-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86f07-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="86f07-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86f07-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="86f07-119">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86f07-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="86f07-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="86f07-120">See also</span></span>

- [<span data-ttu-id="86f07-121">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="86f07-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
