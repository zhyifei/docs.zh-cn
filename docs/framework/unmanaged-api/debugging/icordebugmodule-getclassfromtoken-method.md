---
title: ICorDebugModule::GetClassFromToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: f8a56dcf03748c6582bce07fc379113c5cdddd11
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212590"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="07d88-102">ICorDebugModule::GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="07d88-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="07d88-103">获取元数据标记指定的类。</span><span class="sxs-lookup"><span data-stu-id="07d88-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07d88-104">语法</span><span class="sxs-lookup"><span data-stu-id="07d88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07d88-105">参数</span><span class="sxs-lookup"><span data-stu-id="07d88-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="07d88-106">中`mdTypeDef`引用类的元数据的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="07d88-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="07d88-107">弄指向表示类的 ICorDebugClass 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="07d88-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07d88-108">要求</span><span class="sxs-lookup"><span data-stu-id="07d88-108">Requirements</span></span>  
 <span data-ttu-id="07d88-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07d88-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07d88-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07d88-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07d88-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07d88-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07d88-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07d88-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
