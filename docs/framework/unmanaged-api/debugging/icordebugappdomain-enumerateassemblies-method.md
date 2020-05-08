---
title: ICorDebugAppDomain::EnumerateAssemblies 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
ms.openlocfilehash: 880c234462ac369ead06578730f3c14532c466e9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895291"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="0473d-102">ICorDebugAppDomain::EnumerateAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="0473d-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="0473d-103">获取应用程序域中的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="0473d-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0473d-104">语法</span><span class="sxs-lookup"><span data-stu-id="0473d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0473d-105">参数</span><span class="sxs-lookup"><span data-stu-id="0473d-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="0473d-106">弄指向 ICorDebugAssemblyEnum 对象地址的指针，该对象是应用程序域中的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="0473d-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0473d-107">要求</span><span class="sxs-lookup"><span data-stu-id="0473d-107">Requirements</span></span>  
 <span data-ttu-id="0473d-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0473d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0473d-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0473d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0473d-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0473d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0473d-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0473d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
