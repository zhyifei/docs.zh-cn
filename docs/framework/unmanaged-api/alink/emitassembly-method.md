---
title: EmitAssembly 方法
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b0e6250987997b8d1c833b7b33a985900510fb03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742133"
---
# <a name="emitassembly-method"></a><span data-ttu-id="cdef1-102">EmitAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="cdef1-102">EmitAssembly Method</span></span>
<span data-ttu-id="cdef1-103">创建程序集。</span><span class="sxs-lookup"><span data-stu-id="cdef1-103">Creates the assembly.</span></span> <span data-ttu-id="cdef1-104">所有其他文件关闭除程序集文件后，请调用此方法。</span><span class="sxs-lookup"><span data-stu-id="cdef1-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="cdef1-105">生成未绑定的模块时，请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="cdef1-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdef1-106">语法</span><span class="sxs-lookup"><span data-stu-id="cdef1-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdef1-107">参数</span><span class="sxs-lookup"><span data-stu-id="cdef1-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cdef1-108">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="cdef1-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdef1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="cdef1-109">Return Value</span></span>  
 <span data-ttu-id="cdef1-110">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="cdef1-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdef1-111">要求</span><span class="sxs-lookup"><span data-stu-id="cdef1-111">Requirements</span></span>  
 <span data-ttu-id="cdef1-112">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="cdef1-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdef1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdef1-113">See also</span></span>

- [<span data-ttu-id="cdef1-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="cdef1-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="cdef1-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="cdef1-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="cdef1-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="cdef1-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
