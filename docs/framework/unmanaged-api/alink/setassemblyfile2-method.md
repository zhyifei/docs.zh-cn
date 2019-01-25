---
title: SetAssemblyFile2 方法
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3882998d3155b49251fbe091b72ef11022ebfd2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540203"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="faa2e-102">SetAssemblyFile2 方法</span><span class="sxs-lookup"><span data-stu-id="faa2e-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="faa2e-103">设置的名称和新的程序集的选项。</span><span class="sxs-lookup"><span data-stu-id="faa2e-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="faa2e-104">当生成未绑定的模块时，请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="faa2e-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faa2e-105">语法</span><span class="sxs-lookup"><span data-stu-id="faa2e-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="faa2e-106">参数</span><span class="sxs-lookup"><span data-stu-id="faa2e-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="faa2e-107">清单文件的名称。</span><span class="sxs-lookup"><span data-stu-id="faa2e-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="faa2e-108">[IMetaDataEmit2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)此文件的接口。</span><span class="sxs-lookup"><span data-stu-id="faa2e-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="faa2e-109">所表示的选项[AssemblyFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="faa2e-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="faa2e-110">接收有关正在构造的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="faa2e-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="faa2e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="faa2e-111">Return Value</span></span>  
 <span data-ttu-id="faa2e-112">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="faa2e-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faa2e-113">要求</span><span class="sxs-lookup"><span data-stu-id="faa2e-113">Requirements</span></span>  
 <span data-ttu-id="faa2e-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="faa2e-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa2e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="faa2e-115">See also</span></span>
- [<span data-ttu-id="faa2e-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="faa2e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="faa2e-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="faa2e-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="faa2e-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="faa2e-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
