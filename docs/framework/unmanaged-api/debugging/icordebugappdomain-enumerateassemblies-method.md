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
ms.openlocfilehash: 573b08fcf2ce0fa5ce3187df6ae6a1c2cc385f52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134006"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="5ff7a-102">ICorDebugAppDomain::EnumerateAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="5ff7a-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="5ff7a-103">获取应用程序域中的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="5ff7a-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff7a-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ff7a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ff7a-105">参数</span><span class="sxs-lookup"><span data-stu-id="5ff7a-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="5ff7a-106">弄指向 ICorDebugAssemblyEnum 对象地址的指针，该对象是应用程序域中的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="5ff7a-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff7a-107">要求</span><span class="sxs-lookup"><span data-stu-id="5ff7a-107">Requirements</span></span>  
 <span data-ttu-id="5ff7a-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5ff7a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff7a-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ff7a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ff7a-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ff7a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ff7a-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ff7a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
