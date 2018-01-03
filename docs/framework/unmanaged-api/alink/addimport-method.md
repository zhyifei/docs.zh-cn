---
title: AddImport Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AddImport
- IALink.AddImport
api_location: alink.dll
api_type: COM
f1_keywords: AddImport
helpviewer_keywords: AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d8827821deaeda311a42855737ecf53ab635a02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="addimport-method1"></a><span data-ttu-id="ce7de-102">AddImport Method1</span><span class="sxs-lookup"><span data-stu-id="ce7de-102">AddImport Method1</span></span>
<span data-ttu-id="ce7de-103">将导入添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="ce7de-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7de-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce7de-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce7de-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce7de-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ce7de-106">要进行扩充程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ce7de-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="ce7de-107">从检索的唯一 ID， [ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)的要导入文件。</span><span class="sxs-lookup"><span data-stu-id="ce7de-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ce7de-108">COM + FileDef 标志，如`ffContainsNoMetaData`和`ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="ce7de-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="ce7de-109">`dwFlags`传递给[DefineFile 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ce7de-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="ce7de-110">指向接收生成的文件的 ID 的标记。</span><span class="sxs-lookup"><span data-stu-id="ce7de-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce7de-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ce7de-111">Return Value</span></span>  
 <span data-ttu-id="ce7de-112">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ce7de-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce7de-113">惠?</span><span class="sxs-lookup"><span data-stu-id="ce7de-113">Requirements</span></span>  
 <span data-ttu-id="ce7de-114">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="ce7de-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7de-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce7de-115">See Also</span></span>  
 [<span data-ttu-id="ce7de-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="ce7de-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ce7de-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="ce7de-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ce7de-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="ce7de-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
