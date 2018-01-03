---
title: "SetAssemblyFile2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetAssemblyFile2
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyFile2
helpviewer_keywords: SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 671fb857015a5babd388366066d282cb87462c18
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="29d0a-102">SetAssemblyFile2 方法</span><span class="sxs-lookup"><span data-stu-id="29d0a-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="29d0a-103">设置的名称和新的程序集的选项。</span><span class="sxs-lookup"><span data-stu-id="29d0a-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="29d0a-104">当生成未绑定的模块时，请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="29d0a-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29d0a-105">语法</span><span class="sxs-lookup"><span data-stu-id="29d0a-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29d0a-106">参数</span><span class="sxs-lookup"><span data-stu-id="29d0a-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="29d0a-107">清单文件的名称。</span><span class="sxs-lookup"><span data-stu-id="29d0a-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="29d0a-108">[IMetaDataEmit2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)此文件的接口。</span><span class="sxs-lookup"><span data-stu-id="29d0a-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="29d0a-109">所表示的选项[AssemblyFlags 枚举](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="29d0a-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="29d0a-110">接收的正在构造的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="29d0a-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29d0a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="29d0a-111">Return Value</span></span>  
 <span data-ttu-id="29d0a-112">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="29d0a-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29d0a-113">惠?</span><span class="sxs-lookup"><span data-stu-id="29d0a-113">Requirements</span></span>  
 <span data-ttu-id="29d0a-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="29d0a-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d0a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="29d0a-115">See Also</span></span>  
 [<span data-ttu-id="29d0a-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="29d0a-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="29d0a-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="29d0a-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="29d0a-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="29d0a-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
