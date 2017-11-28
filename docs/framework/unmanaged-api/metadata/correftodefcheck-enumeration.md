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
ms.openlocfilehash: 5144cd3ac261647c04ec7e3e27e28618c94fb439
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="9fce0-102">CorRefToDefCheck 枚举</span><span class="sxs-lookup"><span data-stu-id="9fce0-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="9fce0-103">指定用于控制将哪些引用项转换为相应定义以优化代码的标志。</span><span class="sxs-lookup"><span data-stu-id="9fce0-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fce0-104">语法</span><span class="sxs-lookup"><span data-stu-id="9fce0-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="9fce0-105">成员</span><span class="sxs-lookup"><span data-stu-id="9fce0-105">Members</span></span>  
  
|<span data-ttu-id="9fce0-106">成员</span><span class="sxs-lookup"><span data-stu-id="9fce0-106">Member</span></span>|<span data-ttu-id="9fce0-107">描述</span><span class="sxs-lookup"><span data-stu-id="9fce0-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="9fce0-108">指定类型引用和成员引用应转换为定义。</span><span class="sxs-lookup"><span data-stu-id="9fce0-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="9fce0-109">这是默认值 (`MDTypeRefToDef` &#124;`MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="9fce0-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="9fce0-110">指定应将所有引用的项转换为定义。</span><span class="sxs-lookup"><span data-stu-id="9fce0-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="9fce0-111">指定应将没有引用的项转换为定义。</span><span class="sxs-lookup"><span data-stu-id="9fce0-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="9fce0-112">指定类型引用仅应将转换为类型定义。</span><span class="sxs-lookup"><span data-stu-id="9fce0-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="9fce0-113">指定应将仅成员引用转换的定义。</span><span class="sxs-lookup"><span data-stu-id="9fce0-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="9fce0-114">也就是说，成员引用应转换为方法的定义或字段定义。</span><span class="sxs-lookup"><span data-stu-id="9fce0-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fce0-115">要求</span><span class="sxs-lookup"><span data-stu-id="9fce0-115">Requirements</span></span>  
 <span data-ttu-id="9fce0-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9fce0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fce0-117">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9fce0-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9fce0-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fce0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fce0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fce0-119">See Also</span></span>  
 [<span data-ttu-id="9fce0-120">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="9fce0-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
