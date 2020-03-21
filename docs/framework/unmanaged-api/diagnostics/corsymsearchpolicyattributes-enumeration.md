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
ms.openlocfilehash: 786e53d43ecde0bc3a97fadb77184d25d41430bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178351"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="5a466-102">CorSymSearchPolicyAttributes 枚举</span><span class="sxs-lookup"><span data-stu-id="5a466-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="5a466-103">指定在搜索符号读取器时要使用的策略。</span><span class="sxs-lookup"><span data-stu-id="5a466-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="5a466-104">这些常量由[ISymUn 托管 Binder2：：getReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)和[ISymUn托管 Binder3：：getReader 来自回调](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)方法使用。</span><span class="sxs-lookup"><span data-stu-id="5a466-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5a466-105">从不受信任的源打开程序数据库 （PDB） 文件存在安全风险。</span><span class="sxs-lookup"><span data-stu-id="5a466-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a466-106">语法</span><span class="sxs-lookup"><span data-stu-id="5a466-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="5a466-107">成员</span><span class="sxs-lookup"><span data-stu-id="5a466-107">Members</span></span>  
  
|<span data-ttu-id="5a466-108">成员</span><span class="sxs-lookup"><span data-stu-id="5a466-108">Member</span></span>|<span data-ttu-id="5a466-109">说明</span><span class="sxs-lookup"><span data-stu-id="5a466-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="5a466-110">查询符号搜索路径的注册表。</span><span class="sxs-lookup"><span data-stu-id="5a466-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="5a466-111">访问符号服务器。</span><span class="sxs-lookup"><span data-stu-id="5a466-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="5a466-112">搜索调试目录中指定的路径。</span><span class="sxs-lookup"><span data-stu-id="5a466-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="5a466-113">在 .exe 文件所在的位置搜索 PDB。</span><span class="sxs-lookup"><span data-stu-id="5a466-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a466-114">要求</span><span class="sxs-lookup"><span data-stu-id="5a466-114">Requirements</span></span>  
 <span data-ttu-id="5a466-115">**标题：** 科西姆.伊德尔，科西姆.h</span><span class="sxs-lookup"><span data-stu-id="5a466-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a466-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a466-116">See also</span></span>

- [<span data-ttu-id="5a466-117">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="5a466-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
