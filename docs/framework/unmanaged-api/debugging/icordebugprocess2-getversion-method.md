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
ms.openlocfilehash: 5f618f6779f6931785bba18f70fb1ac9baf46753
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137195"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="2df8f-102">ICorDebugProcess2::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="2df8f-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="2df8f-103">获取在此进程中运行的公共语言运行时（CLR）的版本号。</span><span class="sxs-lookup"><span data-stu-id="2df8f-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="2df8f-104">语法</span><span class="sxs-lookup"><span data-stu-id="2df8f-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="2df8f-105">参数</span><span class="sxs-lookup"><span data-stu-id="2df8f-105">Parameters</span></span>

`version`\
<span data-ttu-id="2df8f-106">弄指向 COR_VERSION 结构的指针，该结构存储运行时的版本号。</span><span class="sxs-lookup"><span data-stu-id="2df8f-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="2df8f-107">备注</span><span class="sxs-lookup"><span data-stu-id="2df8f-107">Remarks</span></span>

<span data-ttu-id="2df8f-108">如果进程中没有加载运行时，则 `GetVersion` 方法返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="2df8f-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="2df8f-109">要求</span><span class="sxs-lookup"><span data-stu-id="2df8f-109">Requirements</span></span>

<span data-ttu-id="2df8f-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2df8f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="2df8f-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2df8f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="2df8f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2df8f-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2df8f-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2df8f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
