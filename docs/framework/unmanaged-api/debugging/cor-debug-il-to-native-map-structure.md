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
ms.openlocfilehash: 03ce77dd7407db8289abfefba13d71a9af053e10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142046"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="8472c-102">COR_DEBUG_IL_TO_NATIVE_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="8472c-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="8472c-103">包含用于将 Microsoft 中间语言 (MSIL) 代码映射到本机代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="8472c-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8472c-104">语法</span><span class="sxs-lookup"><span data-stu-id="8472c-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="8472c-105">成员</span><span class="sxs-lookup"><span data-stu-id="8472c-105">Members</span></span>  
  
|<span data-ttu-id="8472c-106">成员</span><span class="sxs-lookup"><span data-stu-id="8472c-106">Member</span></span>|<span data-ttu-id="8472c-107">描述</span><span class="sxs-lookup"><span data-stu-id="8472c-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="8472c-108">MSIL 代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="8472c-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="8472c-109">本机代码开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="8472c-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="8472c-110">本机代码的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="8472c-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8472c-111">要求</span><span class="sxs-lookup"><span data-stu-id="8472c-111">Requirements</span></span>  
 <span data-ttu-id="8472c-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8472c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8472c-113">**标头：** CorProf.idl CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="8472c-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="8472c-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8472c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8472c-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8472c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8472c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8472c-116">See also</span></span>

- [<span data-ttu-id="8472c-117">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="8472c-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="8472c-118">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="8472c-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="8472c-119">调试结构</span><span class="sxs-lookup"><span data-stu-id="8472c-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="8472c-120">调试</span><span class="sxs-lookup"><span data-stu-id="8472c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
