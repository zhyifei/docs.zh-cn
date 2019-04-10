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
ms.openlocfilehash: 4a5f06b3f79fed5dac5a6f07650e4fabd0aa5867
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142163"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="184e5-102">CVStruct 结构</span><span class="sxs-lookup"><span data-stu-id="184e5-102">CVStruct Structure</span></span>
<span data-ttu-id="184e5-103">包含在安装模块或复合图像时所使用的信息。</span><span class="sxs-lookup"><span data-stu-id="184e5-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="184e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="184e5-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="184e5-105">成员</span><span class="sxs-lookup"><span data-stu-id="184e5-105">Members</span></span>  
  
|<span data-ttu-id="184e5-106">成员</span><span class="sxs-lookup"><span data-stu-id="184e5-106">Member</span></span>|<span data-ttu-id="184e5-107">描述</span><span class="sxs-lookup"><span data-stu-id="184e5-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="184e5-108">主要</span><span class="sxs-lookup"><span data-stu-id="184e5-108">Major</span></span>|<span data-ttu-id="184e5-109">主要版本的内部版本号。</span><span class="sxs-lookup"><span data-stu-id="184e5-109">Major version build number.</span></span>|  
|<span data-ttu-id="184e5-110">次要</span><span class="sxs-lookup"><span data-stu-id="184e5-110">Minor</span></span>|<span data-ttu-id="184e5-111">次要版本生成号。</span><span class="sxs-lookup"><span data-stu-id="184e5-111">Minor version build number.</span></span>|  
|<span data-ttu-id="184e5-112">Sub</span><span class="sxs-lookup"><span data-stu-id="184e5-112">Sub</span></span>|<span data-ttu-id="184e5-113">二次内部版本号。</span><span class="sxs-lookup"><span data-stu-id="184e5-113">Sub-build number.</span></span>|  
|<span data-ttu-id="184e5-114">Build</span><span class="sxs-lookup"><span data-stu-id="184e5-114">Build</span></span>|<span data-ttu-id="184e5-115">生成号。</span><span class="sxs-lookup"><span data-stu-id="184e5-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="184e5-116">要求</span><span class="sxs-lookup"><span data-stu-id="184e5-116">Requirements</span></span>  
 <span data-ttu-id="184e5-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="184e5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="184e5-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="184e5-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="184e5-119">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="184e5-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="184e5-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="184e5-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="184e5-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="184e5-121">See also</span></span>

- [<span data-ttu-id="184e5-122">元数据结构</span><span class="sxs-lookup"><span data-stu-id="184e5-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
