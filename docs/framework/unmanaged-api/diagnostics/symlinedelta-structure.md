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
ms.openlocfilehash: fabc8f77b12865d0d971b5934d7de27b52f3e813
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159479"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="cd0e9-102">SYMLINEDELTA 结构</span><span class="sxs-lookup"><span data-stu-id="cd0e9-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="cd0e9-103">提供到符号处理程序已由于编辑而移动的方法有关的信息。</span><span class="sxs-lookup"><span data-stu-id="cd0e9-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd0e9-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd0e9-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="cd0e9-105">成员</span><span class="sxs-lookup"><span data-stu-id="cd0e9-105">Members</span></span>  
  
|<span data-ttu-id="cd0e9-106">成员</span><span class="sxs-lookup"><span data-stu-id="cd0e9-106">Member</span></span>|<span data-ttu-id="cd0e9-107">描述</span><span class="sxs-lookup"><span data-stu-id="cd0e9-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="cd0e9-108">该方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="cd0e9-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="cd0e9-109">该方法被移动的行数。</span><span class="sxs-lookup"><span data-stu-id="cd0e9-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd0e9-110">要求</span><span class="sxs-lookup"><span data-stu-id="cd0e9-110">Requirements</span></span>  
 <span data-ttu-id="cd0e9-111">**标头：** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="cd0e9-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0e9-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd0e9-112">See also</span></span>

- [<span data-ttu-id="cd0e9-113">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="cd0e9-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
