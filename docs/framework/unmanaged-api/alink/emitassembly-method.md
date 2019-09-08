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
ms.openlocfilehash: a2adf53d1e29fda077cdcf7b79891f6271993109
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787577"
---
# <a name="emitassembly-method"></a><span data-ttu-id="0dab8-102">EmitAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="0dab8-102">EmitAssembly Method</span></span>
<span data-ttu-id="0dab8-103">创建程序集。</span><span class="sxs-lookup"><span data-stu-id="0dab8-103">Creates the assembly.</span></span> <span data-ttu-id="0dab8-104">除程序集文件以外的所有其他文件关闭后，调用此方法。</span><span class="sxs-lookup"><span data-stu-id="0dab8-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="0dab8-105">在生成未绑定的模块时不要调用此方法。</span><span class="sxs-lookup"><span data-stu-id="0dab8-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dab8-106">语法</span><span class="sxs-lookup"><span data-stu-id="0dab8-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dab8-107">参数</span><span class="sxs-lookup"><span data-stu-id="0dab8-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0dab8-108">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="0dab8-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0dab8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0dab8-109">Return Value</span></span>  
 <span data-ttu-id="0dab8-110">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0dab8-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dab8-111">要求</span><span class="sxs-lookup"><span data-stu-id="0dab8-111">Requirements</span></span>  
 <span data-ttu-id="0dab8-112">需要 alink</span><span class="sxs-lookup"><span data-stu-id="0dab8-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dab8-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0dab8-113">See also</span></span>

- [<span data-ttu-id="0dab8-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="0dab8-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0dab8-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="0dab8-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0dab8-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="0dab8-116">ALink API</span></span>](index.md)
