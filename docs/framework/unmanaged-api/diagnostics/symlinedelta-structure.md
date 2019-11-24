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
ms.openlocfilehash: a1e83e4b8cb6603029f3b42b1a3b9ba4810c9039
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438011"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="01c94-102">SYMLINEDELTA 结构</span><span class="sxs-lookup"><span data-stu-id="01c94-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="01c94-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span><span class="sxs-lookup"><span data-stu-id="01c94-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c94-104">语法</span><span class="sxs-lookup"><span data-stu-id="01c94-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="01c94-105">Members</span><span class="sxs-lookup"><span data-stu-id="01c94-105">Members</span></span>  
  
|<span data-ttu-id="01c94-106">成员</span><span class="sxs-lookup"><span data-stu-id="01c94-106">Member</span></span>|<span data-ttu-id="01c94-107">描述</span><span class="sxs-lookup"><span data-stu-id="01c94-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="01c94-108">The method's metadata token.</span><span class="sxs-lookup"><span data-stu-id="01c94-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="01c94-109">The number of lines the method was moved.</span><span class="sxs-lookup"><span data-stu-id="01c94-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01c94-110">要求</span><span class="sxs-lookup"><span data-stu-id="01c94-110">Requirements</span></span>  
 <span data-ttu-id="01c94-111">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="01c94-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c94-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="01c94-112">See also</span></span>

- [<span data-ttu-id="01c94-113">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="01c94-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
