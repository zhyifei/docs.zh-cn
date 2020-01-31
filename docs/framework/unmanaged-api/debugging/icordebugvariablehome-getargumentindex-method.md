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
ms.openlocfilehash: 12d4e63480f03bfad613f30362ddaeaf12b57a88
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791054"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="886b5-102">ICorDebugVariableHome：： GetArgumentIndex 方法</span><span class="sxs-lookup"><span data-stu-id="886b5-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="886b5-103">获取函数参数的索引。</span><span class="sxs-lookup"><span data-stu-id="886b5-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="886b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="886b5-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="886b5-105">参数</span><span class="sxs-lookup"><span data-stu-id="886b5-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="886b5-106">弄指向参数索引的指针。</span><span class="sxs-lookup"><span data-stu-id="886b5-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="886b5-107">返回值</span><span class="sxs-lookup"><span data-stu-id="886b5-107">Return Value</span></span>

<span data-ttu-id="886b5-108">方法返回以下值。</span><span class="sxs-lookup"><span data-stu-id="886b5-108">The method returns the following values.</span></span>

|<span data-ttu-id="886b5-109">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="886b5-109">Value</span></span>|<span data-ttu-id="886b5-110">描述</span><span class="sxs-lookup"><span data-stu-id="886b5-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="886b5-111">方法调用返回有效的参数索引。</span><span class="sxs-lookup"><span data-stu-id="886b5-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="886b5-112">当前[ICorDebugVariableHome](icordebugvariablehome-interface.md)实例表示局部变量。</span><span class="sxs-lookup"><span data-stu-id="886b5-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="886b5-113">备注</span><span class="sxs-lookup"><span data-stu-id="886b5-113">Remarks</span></span>

<span data-ttu-id="886b5-114">参数索引可用于检索此参数的元数据。</span><span class="sxs-lookup"><span data-stu-id="886b5-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="886b5-115">需求</span><span class="sxs-lookup"><span data-stu-id="886b5-115">Requirements</span></span>

<span data-ttu-id="886b5-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="886b5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="886b5-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="886b5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="886b5-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="886b5-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="886b5-119">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="886b5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="886b5-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="886b5-120">See also</span></span>

- [<span data-ttu-id="886b5-121">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="886b5-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
