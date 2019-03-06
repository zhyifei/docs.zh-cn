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
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361222"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="8047f-102">ICorDebugProcess2::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="8047f-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="8047f-103">获取此进程中运行公共语言运行时 (CLR) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="8047f-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="8047f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8047f-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="8047f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8047f-105">Parameters</span></span>

`version`\
<span data-ttu-id="8047f-106">[out]指向存储在运行时的版本号的 COR_VERSION 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="8047f-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="8047f-107">备注</span><span class="sxs-lookup"><span data-stu-id="8047f-107">Remarks</span></span>

<span data-ttu-id="8047f-108">`GetVersion`方法返回的错误代码，如果没有运行时加载在进程中。</span><span class="sxs-lookup"><span data-stu-id="8047f-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="8047f-109">要求</span><span class="sxs-lookup"><span data-stu-id="8047f-109">Requirements</span></span>

<span data-ttu-id="8047f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8047f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="8047f-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8047f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="8047f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8047f-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8047f-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8047f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
