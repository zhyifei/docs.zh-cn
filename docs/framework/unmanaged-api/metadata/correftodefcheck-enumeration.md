---
title: CorRefToDefCheck 枚举
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82abeb0ce3db075d794787bb1fcd5bc18321bef2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093886"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="4bdb4-102">CorRefToDefCheck 枚举</span><span class="sxs-lookup"><span data-stu-id="4bdb4-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="4bdb4-103">指定用于控制将哪些引用项转换为相应定义以优化代码的标志。</span><span class="sxs-lookup"><span data-stu-id="4bdb4-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bdb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="4bdb4-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="4bdb4-105">成员</span><span class="sxs-lookup"><span data-stu-id="4bdb4-105">Members</span></span>  
  
|<span data-ttu-id="4bdb4-106">成员</span><span class="sxs-lookup"><span data-stu-id="4bdb4-106">Member</span></span>|<span data-ttu-id="4bdb4-107">描述</span><span class="sxs-lookup"><span data-stu-id="4bdb4-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="4bdb4-108">指定类型的引用和成员引用应转换为定义。</span><span class="sxs-lookup"><span data-stu-id="4bdb4-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="4bdb4-109">这是默认值 (`MDTypeRefToDef` &#124; `MDMemberRefToDef`)。</span><span class="sxs-lookup"><span data-stu-id="4bdb4-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="4bdb4-110">指定应将所有被引用的项转换为定义。</span><span class="sxs-lookup"><span data-stu-id="4bdb4-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="4bdb4-111">指定应将任何被引用的项转换为定义。</span><span class="sxs-lookup"><span data-stu-id="4bdb4-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="4bdb4-112">指定类型引用仅应将转换为类型定义。</span><span class="sxs-lookup"><span data-stu-id="4bdb4-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="4bdb4-113">指定成员引用仅应转换为定义。</span><span class="sxs-lookup"><span data-stu-id="4bdb4-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="4bdb4-114">也就是说，成员引用应转换为方法定义或字段定义。</span><span class="sxs-lookup"><span data-stu-id="4bdb4-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4bdb4-115">要求</span><span class="sxs-lookup"><span data-stu-id="4bdb4-115">Requirements</span></span>  
 <span data-ttu-id="4bdb4-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4bdb4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bdb4-117">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4bdb4-117">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="4bdb4-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="4bdb4-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4bdb4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bdb4-119">See also</span></span>

- [<span data-ttu-id="4bdb4-120">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="4bdb4-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
