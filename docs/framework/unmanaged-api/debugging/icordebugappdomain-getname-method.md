---
title: "ICorDebugAppDomain::GetName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590bfb5d7d8cac8e322bddfe6258ad9bf377dad6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="d0247-102">ICorDebugAppDomain::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="d0247-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="d0247-103">获取应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="d0247-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0247-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0247-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0247-105">参数</span><span class="sxs-lookup"><span data-stu-id="d0247-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d0247-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="d0247-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="d0247-107">将此值设置为零，以将此方法放在查询模式。</span><span class="sxs-lookup"><span data-stu-id="d0247-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d0247-108">[out]名称或中实际返回的字符数的大小的指针`szName`。</span><span class="sxs-lookup"><span data-stu-id="d0247-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="d0247-109">在查询模式下，此值允许调用方知道多大的缓冲区分配的名称。</span><span class="sxs-lookup"><span data-stu-id="d0247-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="d0247-110">[out]存储应用程序域的名称数组。</span><span class="sxs-lookup"><span data-stu-id="d0247-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0247-111">备注</span><span class="sxs-lookup"><span data-stu-id="d0247-111">Remarks</span></span>  
 <span data-ttu-id="d0247-112">调试器将调用`GetName`方法一次，以获取名称所需的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="d0247-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="d0247-113">调试器分配缓冲区，，然后调用该方法的第二个时间以填充的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d0247-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="d0247-114">要获取的大小的名称，第一个调用被称为*查询模式*。</span><span class="sxs-lookup"><span data-stu-id="d0247-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0247-115">要求</span><span class="sxs-lookup"><span data-stu-id="d0247-115">Requirements</span></span>  
 <span data-ttu-id="d0247-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0247-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0247-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0247-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0247-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0247-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0247-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0247-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
