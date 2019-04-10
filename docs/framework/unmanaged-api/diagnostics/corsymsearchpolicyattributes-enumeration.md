---
title: CorSymSearchPolicyAttributes 枚举
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a9b0f085820bac12638c0310ab23b2eafacb23b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186168"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="b245d-102">CorSymSearchPolicyAttributes 枚举</span><span class="sxs-lookup"><span data-stu-id="b245d-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="b245d-103">指定要执行的符号读取器的搜索时使用的策略。</span><span class="sxs-lookup"><span data-stu-id="b245d-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="b245d-104">通过使用这些常量[ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)并[ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b245d-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b245d-105">它是从受信任的源打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="b245d-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b245d-106">语法</span><span class="sxs-lookup"><span data-stu-id="b245d-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="b245d-107">成员</span><span class="sxs-lookup"><span data-stu-id="b245d-107">Members</span></span>  
  
|<span data-ttu-id="b245d-108">成员</span><span class="sxs-lookup"><span data-stu-id="b245d-108">Member</span></span>|<span data-ttu-id="b245d-109">描述</span><span class="sxs-lookup"><span data-stu-id="b245d-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="b245d-110">查询符号搜索路径的注册表。</span><span class="sxs-lookup"><span data-stu-id="b245d-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="b245d-111">访问符号服务器。</span><span class="sxs-lookup"><span data-stu-id="b245d-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="b245d-112">搜索中的调试目录指定的路径。</span><span class="sxs-lookup"><span data-stu-id="b245d-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="b245d-113">搜索 PDB 中的.exe 文件所在的位置。</span><span class="sxs-lookup"><span data-stu-id="b245d-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b245d-114">要求</span><span class="sxs-lookup"><span data-stu-id="b245d-114">Requirements</span></span>  
 <span data-ttu-id="b245d-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b245d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b245d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b245d-116">See also</span></span>

- [<span data-ttu-id="b245d-117">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="b245d-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
