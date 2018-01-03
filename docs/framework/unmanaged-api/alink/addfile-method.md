---
title: AddFile Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.AddFile
- AddFile
api_location: alink.dll
api_type: COM
f1_keywords: AddFile
helpviewer_keywords: AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 943ff2901ee0888860941e86d589060de729907d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="addfile-method1"></a><span data-ttu-id="74956-102">AddFile Method1</span><span class="sxs-lookup"><span data-stu-id="74956-102">AddFile Method1</span></span>
<span data-ttu-id="74956-103">将文件添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="74956-103">Adds files to the assembly.</span></span> <span data-ttu-id="74956-104">此外可以用于创建未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="74956-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74956-105">语法</span><span class="sxs-lookup"><span data-stu-id="74956-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74956-106">参数</span><span class="sxs-lookup"><span data-stu-id="74956-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="74956-107">要进行扩充的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="74956-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="74956-108">要添加的文件的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="74956-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="74956-109">COM + FileDef 标志，如`ffContainsNoMetaData`和`ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="74956-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="74956-110">`dwFlags`传递给[DefineFile 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="74956-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="74956-111">[IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口用于发出元数据，如有必要。</span><span class="sxs-lookup"><span data-stu-id="74956-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="74956-112">指向将存储添加的文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="74956-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74956-113">返回值</span><span class="sxs-lookup"><span data-stu-id="74956-113">Return Value</span></span>  
 <span data-ttu-id="74956-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="74956-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74956-115">惠?</span><span class="sxs-lookup"><span data-stu-id="74956-115">Requirements</span></span>  
 <span data-ttu-id="74956-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="74956-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74956-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="74956-117">See Also</span></span>  
 [<span data-ttu-id="74956-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="74956-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="74956-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="74956-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="74956-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="74956-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
