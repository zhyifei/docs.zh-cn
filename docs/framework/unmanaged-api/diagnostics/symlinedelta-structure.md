---
title: SYMLINEDELTA 结构
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d534ae381e0dc105731cf0a537f81afe80d87e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732734"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="5765a-102">SYMLINEDELTA 结构</span><span class="sxs-lookup"><span data-stu-id="5765a-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="5765a-103">提供到符号处理程序已由于编辑而移动的方法有关的信息。</span><span class="sxs-lookup"><span data-stu-id="5765a-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5765a-104">语法</span><span class="sxs-lookup"><span data-stu-id="5765a-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="5765a-105">成员</span><span class="sxs-lookup"><span data-stu-id="5765a-105">Members</span></span>  
  
|<span data-ttu-id="5765a-106">成员</span><span class="sxs-lookup"><span data-stu-id="5765a-106">Member</span></span>|<span data-ttu-id="5765a-107">描述</span><span class="sxs-lookup"><span data-stu-id="5765a-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="5765a-108">该方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="5765a-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="5765a-109">该方法被移动的行数。</span><span class="sxs-lookup"><span data-stu-id="5765a-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5765a-110">要求</span><span class="sxs-lookup"><span data-stu-id="5765a-110">Requirements</span></span>  
 <span data-ttu-id="5765a-111">**标头：** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="5765a-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5765a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5765a-112">See also</span></span>
- [<span data-ttu-id="5765a-113">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="5765a-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
