---
title: EmitManifest 方法
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28be714a70229b8a4628db2efff0dc2d890e231b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485494"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="45d42-102">EmitManifest 方法</span><span class="sxs-lookup"><span data-stu-id="45d42-102">EmitManifest Method</span></span>
<span data-ttu-id="45d42-103">发出最终清单。</span><span class="sxs-lookup"><span data-stu-id="45d42-103">Emits the final manifest.</span></span> <span data-ttu-id="45d42-104">导入的所有其他文件和设置所有选项之后调用此方法。</span><span class="sxs-lookup"><span data-stu-id="45d42-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="45d42-105">请勿对未绑定模块调用此方法。</span><span class="sxs-lookup"><span data-stu-id="45d42-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d42-106">语法</span><span class="sxs-lookup"><span data-stu-id="45d42-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="45d42-107">参数</span><span class="sxs-lookup"><span data-stu-id="45d42-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="45d42-108">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="45d42-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="45d42-109">接收要保留在程序集文件中，从检索到的大小[StrongNameSignatureSize 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)。</span><span class="sxs-lookup"><span data-stu-id="45d42-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="45d42-110">可选择性地接收的程序集清单标记。</span><span class="sxs-lookup"><span data-stu-id="45d42-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45d42-111">返回值</span><span class="sxs-lookup"><span data-stu-id="45d42-111">Return Value</span></span>  
 <span data-ttu-id="45d42-112">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="45d42-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45d42-113">要求</span><span class="sxs-lookup"><span data-stu-id="45d42-113">Requirements</span></span>  
 <span data-ttu-id="45d42-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="45d42-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d42-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="45d42-115">See also</span></span>
- [<span data-ttu-id="45d42-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="45d42-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="45d42-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="45d42-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="45d42-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="45d42-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
