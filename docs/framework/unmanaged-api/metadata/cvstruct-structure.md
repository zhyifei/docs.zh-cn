---
title: CVStruct 结构
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 195f311d58f2169d715bb33986ee6e591622f377
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445038"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="e62a6-102">CVStruct 结构</span><span class="sxs-lookup"><span data-stu-id="e62a6-102">CVStruct Structure</span></span>
<span data-ttu-id="e62a6-103">包含在安装模块或复合图像时所使用的信息。</span><span class="sxs-lookup"><span data-stu-id="e62a6-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e62a6-104">语法</span><span class="sxs-lookup"><span data-stu-id="e62a6-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="e62a6-105">成员</span><span class="sxs-lookup"><span data-stu-id="e62a6-105">Members</span></span>  
  
|<span data-ttu-id="e62a6-106">成员</span><span class="sxs-lookup"><span data-stu-id="e62a6-106">Member</span></span>|<span data-ttu-id="e62a6-107">描述</span><span class="sxs-lookup"><span data-stu-id="e62a6-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e62a6-108">主要</span><span class="sxs-lookup"><span data-stu-id="e62a6-108">Major</span></span>|<span data-ttu-id="e62a6-109">主要版本的内部版本号。</span><span class="sxs-lookup"><span data-stu-id="e62a6-109">Major version build number.</span></span>|  
|<span data-ttu-id="e62a6-110">次要</span><span class="sxs-lookup"><span data-stu-id="e62a6-110">Minor</span></span>|<span data-ttu-id="e62a6-111">次要版本生成号。</span><span class="sxs-lookup"><span data-stu-id="e62a6-111">Minor version build number.</span></span>|  
|<span data-ttu-id="e62a6-112">Sub</span><span class="sxs-lookup"><span data-stu-id="e62a6-112">Sub</span></span>|<span data-ttu-id="e62a6-113">子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="e62a6-113">Sub-build number.</span></span>|  
|<span data-ttu-id="e62a6-114">生成</span><span class="sxs-lookup"><span data-stu-id="e62a6-114">Build</span></span>|<span data-ttu-id="e62a6-115">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="e62a6-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e62a6-116">要求</span><span class="sxs-lookup"><span data-stu-id="e62a6-116">Requirements</span></span>  
 <span data-ttu-id="e62a6-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e62a6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e62a6-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e62a6-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e62a6-119">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e62a6-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e62a6-120">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e62a6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62a6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e62a6-121">See Also</span></span>  
 [<span data-ttu-id="e62a6-122">元数据结构</span><span class="sxs-lookup"><span data-stu-id="e62a6-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
