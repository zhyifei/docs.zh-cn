---
title: CREATE_ASM_NAME_OBJ_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9897e396424b9076da8f30c61b5a14cfa9539690
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795419"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="69456-102">CREATE_ASM_NAME_OBJ_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="69456-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="69456-103">指定[IAssemblyName 接口](iassemblyname-interface.md)对象在由[CreateAssemblyNameObject](createassemblynameobject-function.md)函数构建时的特性。</span><span class="sxs-lookup"><span data-stu-id="69456-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69456-104">语法</span><span class="sxs-lookup"><span data-stu-id="69456-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="69456-105">成员</span><span class="sxs-lookup"><span data-stu-id="69456-105">Members</span></span>  
  
|<span data-ttu-id="69456-106">成员</span><span class="sxs-lookup"><span data-stu-id="69456-106">Member</span></span>|<span data-ttu-id="69456-107">描述</span><span class="sxs-lookup"><span data-stu-id="69456-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="69456-108">指示传递的参数是文本标识。</span><span class="sxs-lookup"><span data-stu-id="69456-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="69456-109">设置几个默认值。</span><span class="sxs-lookup"><span data-stu-id="69456-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="69456-110">验证友元程序集规则（仅名称和公钥）。</span><span class="sxs-lookup"><span data-stu-id="69456-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="69456-111">此成员仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="69456-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="69456-112">`CANOF_PARSE_DISPLAY_NAME` 和`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`标志的组合。</span><span class="sxs-lookup"><span data-stu-id="69456-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="69456-113">此成员仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="69456-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69456-114">要求</span><span class="sxs-lookup"><span data-stu-id="69456-114">Requirements</span></span>  
 <span data-ttu-id="69456-115">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="69456-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69456-116">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="69456-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="69456-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69456-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69456-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="69456-118">See also</span></span>

- [<span data-ttu-id="69456-119">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="69456-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="69456-120">CreateAssemblyNameObject 函数</span><span class="sxs-lookup"><span data-stu-id="69456-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="69456-121">合成枚举</span><span class="sxs-lookup"><span data-stu-id="69456-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
