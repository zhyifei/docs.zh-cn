---
title: "CVStruct 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CVStruct
api_location: mscoree.dll
api_type: COM
f1_keywords: CVStruct
helpviewer_keywords: CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 95c1aeb0cacef929e99e5121f29e2f69b320caec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cvstruct-structure"></a><span data-ttu-id="7ed4d-102">CVStruct 结构</span><span class="sxs-lookup"><span data-stu-id="7ed4d-102">CVStruct Structure</span></span>
<span data-ttu-id="7ed4d-103">包含在安装模块或复合图像时所使用的信息。</span><span class="sxs-lookup"><span data-stu-id="7ed4d-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ed4d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ed4d-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="7ed4d-105">成员</span><span class="sxs-lookup"><span data-stu-id="7ed4d-105">Members</span></span>  
  
|<span data-ttu-id="7ed4d-106">成员</span><span class="sxs-lookup"><span data-stu-id="7ed4d-106">Member</span></span>|<span data-ttu-id="7ed4d-107">描述</span><span class="sxs-lookup"><span data-stu-id="7ed4d-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7ed4d-108">主要</span><span class="sxs-lookup"><span data-stu-id="7ed4d-108">Major</span></span>|<span data-ttu-id="7ed4d-109">主要版本的内部版本号。</span><span class="sxs-lookup"><span data-stu-id="7ed4d-109">Major version build number.</span></span>|  
|<span data-ttu-id="7ed4d-110">次要</span><span class="sxs-lookup"><span data-stu-id="7ed4d-110">Minor</span></span>|<span data-ttu-id="7ed4d-111">次要版本生成号。</span><span class="sxs-lookup"><span data-stu-id="7ed4d-111">Minor version build number.</span></span>|  
|<span data-ttu-id="7ed4d-112">Sub</span><span class="sxs-lookup"><span data-stu-id="7ed4d-112">Sub</span></span>|<span data-ttu-id="7ed4d-113">子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="7ed4d-113">Sub-build number.</span></span>|  
|<span data-ttu-id="7ed4d-114">生成</span><span class="sxs-lookup"><span data-stu-id="7ed4d-114">Build</span></span>|<span data-ttu-id="7ed4d-115">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="7ed4d-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ed4d-116">要求</span><span class="sxs-lookup"><span data-stu-id="7ed4d-116">Requirements</span></span>  
 <span data-ttu-id="7ed4d-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ed4d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ed4d-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7ed4d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ed4d-119">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7ed4d-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ed4d-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ed4d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed4d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ed4d-121">See Also</span></span>  
 [<span data-ttu-id="7ed4d-122">元数据结构</span><span class="sxs-lookup"><span data-stu-id="7ed4d-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
