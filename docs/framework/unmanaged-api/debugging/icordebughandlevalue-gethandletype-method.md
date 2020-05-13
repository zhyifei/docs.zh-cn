---
title: ICorDebugHandleValue::GetHandleType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
ms.openlocfilehash: 6eb76ddd6ee8b2a00aac3af9ebf815338d29f194
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212160"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="1fd19-102">ICorDebugHandleValue::GetHandleType 方法</span><span class="sxs-lookup"><span data-stu-id="1fd19-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="1fd19-103">获取一个值，该值指示此 ICorDebugHandleValue 对象所引用的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="1fd19-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fd19-104">语法</span><span class="sxs-lookup"><span data-stu-id="1fd19-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fd19-105">参数</span><span class="sxs-lookup"><span data-stu-id="1fd19-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="1fd19-106">弄指向 CorDebugHandleType 枚举的值的指针，该枚举指示此句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="1fd19-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fd19-107">要求</span><span class="sxs-lookup"><span data-stu-id="1fd19-107">Requirements</span></span>  
 <span data-ttu-id="1fd19-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd19-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fd19-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fd19-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fd19-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fd19-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fd19-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fd19-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
