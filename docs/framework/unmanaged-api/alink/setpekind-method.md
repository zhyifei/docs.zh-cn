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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fc581904351443f4368a68a653fd39b3548999a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741425"
---
# <a name="setpekind-method"></a><span data-ttu-id="16c13-102">SetPEKind 方法</span><span class="sxs-lookup"><span data-stu-id="16c13-102">SetPEKind Method</span></span>
<span data-ttu-id="16c13-103">确定特定于计算机或计算机不可知的可移植可执行文件类型。</span><span class="sxs-lookup"><span data-stu-id="16c13-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16c13-104">语法</span><span class="sxs-lookup"><span data-stu-id="16c13-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="16c13-105">参数</span><span class="sxs-lookup"><span data-stu-id="16c13-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="16c13-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="16c13-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="16c13-107">PE 类型要为其设置的文件的令牌。</span><span class="sxs-lookup"><span data-stu-id="16c13-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="16c13-108">可以为 NULL，如果`AssemblyID`并不表示未绑定的 netmodule。</span><span class="sxs-lookup"><span data-stu-id="16c13-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="16c13-109">PE 所示的类型[CorPEKind 枚举](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="16c13-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="16c13-110">目标计算机体系结构，如 NT 标头中所示。</span><span class="sxs-lookup"><span data-stu-id="16c13-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16c13-111">返回值</span><span class="sxs-lookup"><span data-stu-id="16c13-111">Return Value</span></span>  
 <span data-ttu-id="16c13-112">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="16c13-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16c13-113">要求</span><span class="sxs-lookup"><span data-stu-id="16c13-113">Requirements</span></span>  
 <span data-ttu-id="16c13-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="16c13-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c13-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="16c13-115">See also</span></span>

- [<span data-ttu-id="16c13-116">GetPEKind 方法</span><span class="sxs-lookup"><span data-stu-id="16c13-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="16c13-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="16c13-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="16c13-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="16c13-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="16c13-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="16c13-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
