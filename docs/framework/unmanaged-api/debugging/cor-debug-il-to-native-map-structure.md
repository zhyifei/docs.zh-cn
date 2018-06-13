---
title: COR_DEBUG_IL_TO_NATIVE_MAP 结构
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ea9a75ae9316c18439f6c2b728b47deacef9228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404725"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="0f5c6-102">COR_DEBUG_IL_TO_NATIVE_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="0f5c6-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="0f5c6-103">包含用于将 Microsoft 中间语言 (MSIL) 代码映射到本机代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="0f5c6-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f5c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="0f5c6-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="0f5c6-105">成员</span><span class="sxs-lookup"><span data-stu-id="0f5c6-105">Members</span></span>  
  
|<span data-ttu-id="0f5c6-106">成员</span><span class="sxs-lookup"><span data-stu-id="0f5c6-106">Member</span></span>|<span data-ttu-id="0f5c6-107">描述</span><span class="sxs-lookup"><span data-stu-id="0f5c6-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="0f5c6-108">MSIL 代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="0f5c6-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="0f5c6-109">本机代码开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="0f5c6-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="0f5c6-110">本机代码的结尾部分的偏移量。</span><span class="sxs-lookup"><span data-stu-id="0f5c6-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f5c6-111">要求</span><span class="sxs-lookup"><span data-stu-id="0f5c6-111">Requirements</span></span>  
 <span data-ttu-id="0f5c6-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f5c6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f5c6-113">**标头：** CorProf.idl、 CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="0f5c6-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="0f5c6-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f5c6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f5c6-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f5c6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f5c6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f5c6-116">See Also</span></span>  
 [<span data-ttu-id="0f5c6-117">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="0f5c6-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [<span data-ttu-id="0f5c6-118">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="0f5c6-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [<span data-ttu-id="0f5c6-119">调试结构</span><span class="sxs-lookup"><span data-stu-id="0f5c6-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="0f5c6-120">调试</span><span class="sxs-lookup"><span data-stu-id="0f5c6-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
