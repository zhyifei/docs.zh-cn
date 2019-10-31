---
title: ICorDebugModule::GetName 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
ms.openlocfilehash: b27e7a2cdcbfc3a88a734230118d99c2dd5c700e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129539"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="f4834-102">ICorDebugModule::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="f4834-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="f4834-103">获取模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="f4834-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4834-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4834-104">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4834-105">参数</span><span class="sxs-lookup"><span data-stu-id="f4834-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="f4834-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="f4834-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f4834-107">中指向返回名称的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="f4834-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="f4834-108">弄存储返回的名称的数组。</span><span class="sxs-lookup"><span data-stu-id="f4834-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4834-109">备注</span><span class="sxs-lookup"><span data-stu-id="f4834-109">Remarks</span></span>  
 <span data-ttu-id="f4834-110">如果模块的文件名与磁盘上的名称相匹配，则 `GetName` 方法返回 S_OK HRESULT。</span><span class="sxs-lookup"><span data-stu-id="f4834-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="f4834-111">如果名称是虚构的，则 `GetName` 返回 S_FALSE HRESULT，如用于动态或内存中的模块。</span><span class="sxs-lookup"><span data-stu-id="f4834-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4834-112">要求</span><span class="sxs-lookup"><span data-stu-id="f4834-112">Requirements</span></span>  
 <span data-ttu-id="f4834-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4834-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4834-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4834-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4834-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4834-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4834-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4834-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4834-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4834-117">See also</span></span>
