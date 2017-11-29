---
title: "CREATE_ASM_NAME_OBJ_FLAGS 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CREATE_ASM_NAME_OBJ_FLAGS
api_location: fusion.dll
api_type: COM
f1_keywords: CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords: CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4982b33643d855be4b8cace59f1c5cac4201d5ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="61f20-102">CREATE_ASM_NAME_OBJ_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="61f20-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="61f20-103">指定的属性[IAssemblyName 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象时其构建方式是[CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="61f20-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f20-104">语法</span><span class="sxs-lookup"><span data-stu-id="61f20-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="61f20-105">成员</span><span class="sxs-lookup"><span data-stu-id="61f20-105">Members</span></span>  
  
|<span data-ttu-id="61f20-106">成员</span><span class="sxs-lookup"><span data-stu-id="61f20-106">Member</span></span>|<span data-ttu-id="61f20-107">描述</span><span class="sxs-lookup"><span data-stu-id="61f20-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="61f20-108">指示传递的参数为文本的标识。</span><span class="sxs-lookup"><span data-stu-id="61f20-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="61f20-109">设置了几个默认值。</span><span class="sxs-lookup"><span data-stu-id="61f20-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="61f20-110">验证友元程序集的规则 （仅限名称和公钥）。</span><span class="sxs-lookup"><span data-stu-id="61f20-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="61f20-111">此成员是仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="61f20-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="61f20-112">组合`CANOF_PARSE_DISPLAY_NAME`和`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`标志。</span><span class="sxs-lookup"><span data-stu-id="61f20-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="61f20-113">此成员是仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="61f20-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61f20-114">要求</span><span class="sxs-lookup"><span data-stu-id="61f20-114">Requirements</span></span>  
 <span data-ttu-id="61f20-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61f20-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61f20-116">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="61f20-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="61f20-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61f20-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f20-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61f20-118">See Also</span></span>  
 [<span data-ttu-id="61f20-119">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="61f20-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="61f20-120">CreateAssemblyNameObject 函数</span><span class="sxs-lookup"><span data-stu-id="61f20-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 [<span data-ttu-id="61f20-121">合成枚举</span><span class="sxs-lookup"><span data-stu-id="61f20-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
