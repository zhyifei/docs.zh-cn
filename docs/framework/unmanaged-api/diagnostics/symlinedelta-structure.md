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
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609295"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="24729-102">SYMLINEDELTA 结构</span><span class="sxs-lookup"><span data-stu-id="24729-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="24729-103">向符号处理程序提供有关因编辑而移动的方法的信息。</span><span class="sxs-lookup"><span data-stu-id="24729-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24729-104">语法</span><span class="sxs-lookup"><span data-stu-id="24729-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="24729-105">成员</span><span class="sxs-lookup"><span data-stu-id="24729-105">Members</span></span>  
  
|<span data-ttu-id="24729-106">成员</span><span class="sxs-lookup"><span data-stu-id="24729-106">Member</span></span>|<span data-ttu-id="24729-107">描述</span><span class="sxs-lookup"><span data-stu-id="24729-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="24729-108">方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="24729-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="24729-109">此方法已移动的行数。</span><span class="sxs-lookup"><span data-stu-id="24729-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24729-110">要求</span><span class="sxs-lookup"><span data-stu-id="24729-110">Requirements</span></span>  
 <span data-ttu-id="24729-111">**标头：** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="24729-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24729-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24729-112">See also</span></span>

- [<span data-ttu-id="24729-113">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="24729-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
