---
title: "CorRefToDefCheck 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRefToDefCheck
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRefToDefCheck
helpviewer_keywords: CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 366110eca3c4621866213b2c9fc4bcf99103d0a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="bfb5b-102">CorRefToDefCheck 枚举</span><span class="sxs-lookup"><span data-stu-id="bfb5b-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="bfb5b-103">指定用于控制将哪些引用项转换为相应定义以优化代码的标志。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfb5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="bfb5b-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="bfb5b-105">成员</span><span class="sxs-lookup"><span data-stu-id="bfb5b-105">Members</span></span>  
  
|<span data-ttu-id="bfb5b-106">成员</span><span class="sxs-lookup"><span data-stu-id="bfb5b-106">Member</span></span>|<span data-ttu-id="bfb5b-107">描述</span><span class="sxs-lookup"><span data-stu-id="bfb5b-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="bfb5b-108">指定类型引用和成员引用应转换为定义。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="bfb5b-109">这是默认值 (`MDTypeRefToDef` &#124;`MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="bfb5b-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="bfb5b-110">指定应将所有引用的项转换为定义。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="bfb5b-111">指定应将没有引用的项转换为定义。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="bfb5b-112">指定类型引用仅应将转换为类型定义。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="bfb5b-113">指定应将仅成员引用转换的定义。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="bfb5b-114">也就是说，成员引用应转换为方法的定义或字段定义。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfb5b-115">惠?</span><span class="sxs-lookup"><span data-stu-id="bfb5b-115">Requirements</span></span>  
 <span data-ttu-id="bfb5b-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bfb5b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfb5b-117">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="bfb5b-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bfb5b-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfb5b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb5b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfb5b-119">See Also</span></span>  
 [<span data-ttu-id="bfb5b-120">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="bfb5b-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
