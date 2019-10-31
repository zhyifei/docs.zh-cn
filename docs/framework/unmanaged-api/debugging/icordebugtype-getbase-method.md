---
title: ICorDebugType::GetBase 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: cff527aa7cde6a13667d47d030a0ef7db96ad5ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122335"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="a59c7-102">ICorDebugType::GetBase 方法</span><span class="sxs-lookup"><span data-stu-id="a59c7-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="a59c7-103">获取一个指向 ICorDebugType 的接口指针，该指针表示此 `ICorDebugType`表示的类型的基类型（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="a59c7-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a59c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="a59c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a59c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="a59c7-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="a59c7-106">弄指向表示基类型的 `ICorDebugType` 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a59c7-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a59c7-107">备注</span><span class="sxs-lookup"><span data-stu-id="a59c7-107">Remarks</span></span>  
 <span data-ttu-id="a59c7-108">查找类型的基类型对于实现常见调试器功能非常有用，例如打印对象或其父类的所有字段。</span><span class="sxs-lookup"><span data-stu-id="a59c7-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a59c7-109">要求</span><span class="sxs-lookup"><span data-stu-id="a59c7-109">Requirements</span></span>  
 <span data-ttu-id="a59c7-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a59c7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a59c7-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a59c7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a59c7-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a59c7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a59c7-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a59c7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
