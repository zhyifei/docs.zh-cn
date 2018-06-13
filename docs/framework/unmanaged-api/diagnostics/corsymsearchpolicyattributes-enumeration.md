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
ms.openlocfilehash: a4c3aedea4cc8ce2d8fb8c0c0bf3fead727dcf64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425855"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="817d3-102">CorSymSearchPolicyAttributes 枚举</span><span class="sxs-lookup"><span data-stu-id="817d3-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="817d3-103">指定要执行搜索的符号读取器时使用的策略。</span><span class="sxs-lookup"><span data-stu-id="817d3-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="817d3-104">这些常量由[isymunmanagedbinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)和[isymunmanagedbinder3:: Getreaderfromcallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="817d3-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="817d3-105">它是从受信任的源中打开程序数据库 (PDB) 文件会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="817d3-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="817d3-106">语法</span><span class="sxs-lookup"><span data-stu-id="817d3-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="817d3-107">成员</span><span class="sxs-lookup"><span data-stu-id="817d3-107">Members</span></span>  
  
|<span data-ttu-id="817d3-108">成员</span><span class="sxs-lookup"><span data-stu-id="817d3-108">Member</span></span>|<span data-ttu-id="817d3-109">描述</span><span class="sxs-lookup"><span data-stu-id="817d3-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="817d3-110">查询符号搜索路径的注册表。</span><span class="sxs-lookup"><span data-stu-id="817d3-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="817d3-111">访问符号服务器。</span><span class="sxs-lookup"><span data-stu-id="817d3-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="817d3-112">搜索的调试目录中指定的路径。</span><span class="sxs-lookup"><span data-stu-id="817d3-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="817d3-113">搜索的.exe 文件所在的位置中的 PDB。</span><span class="sxs-lookup"><span data-stu-id="817d3-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="817d3-114">要求</span><span class="sxs-lookup"><span data-stu-id="817d3-114">Requirements</span></span>  
 <span data-ttu-id="817d3-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="817d3-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="817d3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="817d3-116">See Also</span></span>  
 [<span data-ttu-id="817d3-117">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="817d3-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
