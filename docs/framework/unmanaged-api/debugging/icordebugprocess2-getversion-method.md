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
ms.openlocfilehash: 391b848d3b3f66f6af6bf3adbefb6e94d526e748
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213499"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="4e3bc-102">ICorDebugProcess2::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="4e3bc-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="4e3bc-103">获取在此进程中运行的公共语言运行时（CLR）的版本号。</span><span class="sxs-lookup"><span data-stu-id="4e3bc-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e3bc-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e3bc-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="4e3bc-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e3bc-105">Parameters</span></span>

`version`\
<span data-ttu-id="4e3bc-106">弄指向存储运行时版本号的 COR_VERSION 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="4e3bc-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e3bc-107">备注</span><span class="sxs-lookup"><span data-stu-id="4e3bc-107">Remarks</span></span>

<span data-ttu-id="4e3bc-108">`GetVersion`如果进程中未加载运行时，则方法将返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="4e3bc-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e3bc-109">要求</span><span class="sxs-lookup"><span data-stu-id="4e3bc-109">Requirements</span></span>

<span data-ttu-id="4e3bc-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e3bc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="4e3bc-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e3bc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="4e3bc-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e3bc-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="4e3bc-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e3bc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
