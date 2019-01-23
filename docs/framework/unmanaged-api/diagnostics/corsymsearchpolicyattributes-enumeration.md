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
ms.openlocfilehash: 5ed868febb5eb82cf73cfc5b0633d86bf4e1315c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561616"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="84b8c-102">CorSymSearchPolicyAttributes 枚举</span><span class="sxs-lookup"><span data-stu-id="84b8c-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="84b8c-103">指定要执行的符号读取器的搜索时使用的策略。</span><span class="sxs-lookup"><span data-stu-id="84b8c-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="84b8c-104">通过使用这些常量[ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)并[ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="84b8c-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="84b8c-105">它是从受信任的源打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="84b8c-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b8c-106">语法</span><span class="sxs-lookup"><span data-stu-id="84b8c-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="84b8c-107">成员</span><span class="sxs-lookup"><span data-stu-id="84b8c-107">Members</span></span>  
  
|<span data-ttu-id="84b8c-108">成员</span><span class="sxs-lookup"><span data-stu-id="84b8c-108">Member</span></span>|<span data-ttu-id="84b8c-109">描述</span><span class="sxs-lookup"><span data-stu-id="84b8c-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="84b8c-110">查询符号搜索路径的注册表。</span><span class="sxs-lookup"><span data-stu-id="84b8c-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="84b8c-111">访问符号服务器。</span><span class="sxs-lookup"><span data-stu-id="84b8c-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="84b8c-112">搜索中的调试目录指定的路径。</span><span class="sxs-lookup"><span data-stu-id="84b8c-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="84b8c-113">搜索 PDB 中的.exe 文件所在的位置。</span><span class="sxs-lookup"><span data-stu-id="84b8c-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84b8c-114">要求</span><span class="sxs-lookup"><span data-stu-id="84b8c-114">Requirements</span></span>  
 <span data-ttu-id="84b8c-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="84b8c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b8c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="84b8c-116">See also</span></span>
- [<span data-ttu-id="84b8c-117">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="84b8c-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
