---
title: SetPEKind 方法
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179388"
---
# <a name="setpekind-method"></a><span data-ttu-id="fb63c-102">SetPEKind 方法</span><span class="sxs-lookup"><span data-stu-id="fb63c-102">SetPEKind Method</span></span>
<span data-ttu-id="fb63c-103">确定可移植可执行类型，无论是特定于机器还是与机器无关。</span><span class="sxs-lookup"><span data-stu-id="fb63c-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb63c-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb63c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="fb63c-105">parameters</span><span class="sxs-lookup"><span data-stu-id="fb63c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fb63c-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="fb63c-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="fb63c-107">要为其设置 PE 类型的文件令牌。</span><span class="sxs-lookup"><span data-stu-id="fb63c-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="fb63c-108">如果未`AssemblyID`指示未绑定网络模块，则可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fb63c-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="fb63c-109">PE 的类型，如[CorPEKind 枚举](../metadata/corpekind-enumeration.md)所示。</span><span class="sxs-lookup"><span data-stu-id="fb63c-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="fb63c-110">目标计算机体系结构，如 NT 标头中所示。</span><span class="sxs-lookup"><span data-stu-id="fb63c-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb63c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="fb63c-111">Return Value</span></span>  
 <span data-ttu-id="fb63c-112">如果方法成功，则返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="fb63c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb63c-113">要求</span><span class="sxs-lookup"><span data-stu-id="fb63c-113">Requirements</span></span>  
 <span data-ttu-id="fb63c-114">需要 alink.h.</span><span class="sxs-lookup"><span data-stu-id="fb63c-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb63c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb63c-115">See also</span></span>

- [<span data-ttu-id="fb63c-116">GetPEKind 方法</span><span class="sxs-lookup"><span data-stu-id="fb63c-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="fb63c-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="fb63c-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="fb63c-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="fb63c-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fb63c-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="fb63c-119">ALink API</span></span>](index.md)
