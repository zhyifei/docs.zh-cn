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
ms.openlocfilehash: 91dc4cb7d64d49d1e95c0c8eb79a29736559d842
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742080"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="c0907-102">EmitManifest 方法</span><span class="sxs-lookup"><span data-stu-id="c0907-102">EmitManifest Method</span></span>
<span data-ttu-id="c0907-103">发出最终清单。</span><span class="sxs-lookup"><span data-stu-id="c0907-103">Emits the final manifest.</span></span> <span data-ttu-id="c0907-104">导入的所有其他文件和设置所有选项之后调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c0907-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="c0907-105">请勿对未绑定模块调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c0907-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0907-106">语法</span><span class="sxs-lookup"><span data-stu-id="c0907-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0907-107">参数</span><span class="sxs-lookup"><span data-stu-id="c0907-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c0907-108">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="c0907-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="c0907-109">接收要保留在程序集文件中，从检索到的大小[StrongNameSignatureSize 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)。</span><span class="sxs-lookup"><span data-stu-id="c0907-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="c0907-110">可选择性地接收的程序集清单标记。</span><span class="sxs-lookup"><span data-stu-id="c0907-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0907-111">返回值</span><span class="sxs-lookup"><span data-stu-id="c0907-111">Return Value</span></span>  
 <span data-ttu-id="c0907-112">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="c0907-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0907-113">要求</span><span class="sxs-lookup"><span data-stu-id="c0907-113">Requirements</span></span>  
 <span data-ttu-id="c0907-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="c0907-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0907-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0907-115">See also</span></span>

- [<span data-ttu-id="c0907-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="c0907-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c0907-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="c0907-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c0907-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="c0907-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
