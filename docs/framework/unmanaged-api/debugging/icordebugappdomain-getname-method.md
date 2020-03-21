---
title: ICorDebugAppDomain::GetName 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 45d27fca888bdabedf197525c63dbd03af7ba1ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179092"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="dffbf-102">ICorDebugAppDomain::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="dffbf-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="dffbf-103">获取应用程序域的名称。</span><span class="sxs-lookup"><span data-stu-id="dffbf-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dffbf-104">语法</span><span class="sxs-lookup"><span data-stu-id="dffbf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dffbf-105">parameters</span><span class="sxs-lookup"><span data-stu-id="dffbf-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="dffbf-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="dffbf-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="dffbf-107">将此值设置为零，以将此方法置于查询模式。</span><span class="sxs-lookup"><span data-stu-id="dffbf-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="dffbf-108">[出]指向名称大小或 中`szName`实际返回的字符数的指针。</span><span class="sxs-lookup"><span data-stu-id="dffbf-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="dffbf-109">在查询模式下，此值允许调用方知道要为名称分配缓冲区有多大。</span><span class="sxs-lookup"><span data-stu-id="dffbf-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="dffbf-110">[出]存储应用程序域名称的数组。</span><span class="sxs-lookup"><span data-stu-id="dffbf-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dffbf-111">备注</span><span class="sxs-lookup"><span data-stu-id="dffbf-111">Remarks</span></span>  
 <span data-ttu-id="dffbf-112">调试器调用`GetName`该方法一次，以获得名称所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="dffbf-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="dffbf-113">调试器分配缓冲区，然后第二次调用 该方法以填充缓冲区。</span><span class="sxs-lookup"><span data-stu-id="dffbf-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="dffbf-114">第一个调用（获取名称的大小）称为*查询模式*。</span><span class="sxs-lookup"><span data-stu-id="dffbf-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dffbf-115">要求</span><span class="sxs-lookup"><span data-stu-id="dffbf-115">Requirements</span></span>  
 <span data-ttu-id="dffbf-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dffbf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dffbf-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dffbf-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dffbf-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dffbf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dffbf-119">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dffbf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
