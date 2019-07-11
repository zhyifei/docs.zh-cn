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
ms.openlocfilehash: d98ebed2eb853d5dc8177b0b044bf654c3978494
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744345"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="1a8cb-102">SYMLINEDELTA 结构</span><span class="sxs-lookup"><span data-stu-id="1a8cb-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="1a8cb-103">提供到符号处理程序已由于编辑而移动的方法有关的信息。</span><span class="sxs-lookup"><span data-stu-id="1a8cb-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a8cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a8cb-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="1a8cb-105">成员</span><span class="sxs-lookup"><span data-stu-id="1a8cb-105">Members</span></span>  
  
|<span data-ttu-id="1a8cb-106">成员</span><span class="sxs-lookup"><span data-stu-id="1a8cb-106">Member</span></span>|<span data-ttu-id="1a8cb-107">描述</span><span class="sxs-lookup"><span data-stu-id="1a8cb-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="1a8cb-108">该方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1a8cb-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="1a8cb-109">该方法被移动的行数。</span><span class="sxs-lookup"><span data-stu-id="1a8cb-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a8cb-110">要求</span><span class="sxs-lookup"><span data-stu-id="1a8cb-110">Requirements</span></span>  
 <span data-ttu-id="1a8cb-111">**标头：** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="1a8cb-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a8cb-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a8cb-112">See also</span></span>

- [<span data-ttu-id="1a8cb-113">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="1a8cb-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
