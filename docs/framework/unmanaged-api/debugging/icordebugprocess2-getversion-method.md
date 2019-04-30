---
title: ICorDebugProcess2::GetVersion 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f3be81431201a4bb6011ea9b8f973061d3d101
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948860"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="966b2-102">ICorDebugProcess2::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="966b2-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="966b2-103">获取此进程中运行公共语言运行时 (CLR) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="966b2-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="966b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="966b2-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="966b2-105">参数</span><span class="sxs-lookup"><span data-stu-id="966b2-105">Parameters</span></span>

`version`\
<span data-ttu-id="966b2-106">[out]指向存储在运行时的版本号的 COR_VERSION 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="966b2-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="966b2-107">备注</span><span class="sxs-lookup"><span data-stu-id="966b2-107">Remarks</span></span>

<span data-ttu-id="966b2-108">`GetVersion`方法返回的错误代码，如果没有运行时加载在进程中。</span><span class="sxs-lookup"><span data-stu-id="966b2-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="966b2-109">要求</span><span class="sxs-lookup"><span data-stu-id="966b2-109">Requirements</span></span>

<span data-ttu-id="966b2-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="966b2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="966b2-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="966b2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="966b2-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="966b2-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="966b2-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="966b2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
