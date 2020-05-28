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
ms.openlocfilehash: 84791eba7c95d3278bd4650bd7d660e98fcb79d8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008908"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="bb3bb-102">CVStruct 结构</span><span class="sxs-lookup"><span data-stu-id="bb3bb-102">CVStruct Structure</span></span>
<span data-ttu-id="bb3bb-103">包含在安装模块或复合图像时所使用的信息。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb3bb-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="bb3bb-105">成员</span><span class="sxs-lookup"><span data-stu-id="bb3bb-105">Members</span></span>  
  
|<span data-ttu-id="bb3bb-106">成员</span><span class="sxs-lookup"><span data-stu-id="bb3bb-106">Member</span></span>|<span data-ttu-id="bb3bb-107">描述</span><span class="sxs-lookup"><span data-stu-id="bb3bb-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bb3bb-108">主要</span><span class="sxs-lookup"><span data-stu-id="bb3bb-108">Major</span></span>|<span data-ttu-id="bb3bb-109">主版本的内部版本号。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-109">Major version build number.</span></span>|  
|<span data-ttu-id="bb3bb-110">Minor</span><span class="sxs-lookup"><span data-stu-id="bb3bb-110">Minor</span></span>|<span data-ttu-id="bb3bb-111">次版本号。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-111">Minor version build number.</span></span>|  
|<span data-ttu-id="bb3bb-112">Sub</span><span class="sxs-lookup"><span data-stu-id="bb3bb-112">Sub</span></span>|<span data-ttu-id="bb3bb-113">子生成号。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-113">Sub-build number.</span></span>|  
|<span data-ttu-id="bb3bb-114">构建</span><span class="sxs-lookup"><span data-stu-id="bb3bb-114">Build</span></span>|<span data-ttu-id="bb3bb-115">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb3bb-116">要求</span><span class="sxs-lookup"><span data-stu-id="bb3bb-116">Requirements</span></span>  
 <span data-ttu-id="bb3bb-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb3bb-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb3bb-118">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="bb3bb-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb3bb-119">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bb3bb-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb3bb-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb3bb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3bb-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb3bb-121">See also</span></span>

- [<span data-ttu-id="bb3bb-122">元数据结构</span><span class="sxs-lookup"><span data-stu-id="bb3bb-122">Metadata Structures</span></span>](metadata-structures.md)
