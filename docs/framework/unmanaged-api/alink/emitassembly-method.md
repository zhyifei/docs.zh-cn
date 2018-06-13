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
ms.openlocfilehash: 1cd1c077a8f2a5fe3b2b46c2e1da2e92b5a797a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402052"
---
# <a name="emitassembly-method"></a><span data-ttu-id="1a804-102">EmitAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="1a804-102">EmitAssembly Method</span></span>
<span data-ttu-id="1a804-103">创建程序集。</span><span class="sxs-lookup"><span data-stu-id="1a804-103">Creates the assembly.</span></span> <span data-ttu-id="1a804-104">调用此方法后所有其他文件都将关闭的程序集文件除外。</span><span class="sxs-lookup"><span data-stu-id="1a804-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="1a804-105">当生成未绑定的模块时，请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="1a804-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a804-106">语法</span><span class="sxs-lookup"><span data-stu-id="1a804-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a804-107">参数</span><span class="sxs-lookup"><span data-stu-id="1a804-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1a804-108">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="1a804-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a804-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1a804-109">Return Value</span></span>  
 <span data-ttu-id="1a804-110">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="1a804-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a804-111">要求</span><span class="sxs-lookup"><span data-stu-id="1a804-111">Requirements</span></span>  
 <span data-ttu-id="1a804-112">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="1a804-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a804-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a804-113">See Also</span></span>  
 [<span data-ttu-id="1a804-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="1a804-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1a804-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="1a804-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1a804-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="1a804-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
