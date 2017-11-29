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
ms.openlocfilehash: 9463f2c41f56287ebfc4fb55aa8208c37522a57f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="addfile-method1"></a><span data-ttu-id="7e940-102">AddFile Method1</span><span class="sxs-lookup"><span data-stu-id="7e940-102">AddFile Method1</span></span>
<span data-ttu-id="7e940-103">将文件添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="7e940-103">Adds files to the assembly.</span></span> <span data-ttu-id="7e940-104">此外可以用于创建未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="7e940-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e940-105">语法</span><span class="sxs-lookup"><span data-stu-id="7e940-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e940-106">参数</span><span class="sxs-lookup"><span data-stu-id="7e940-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7e940-107">要进行扩充的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="7e940-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="7e940-108">要添加的文件的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="7e940-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7e940-109">COM + FileDef 标志，如`ffContainsNoMetaData`和`ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="7e940-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="7e940-110">`dwFlags`传递给[DefineFile 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7e940-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="7e940-111">[IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口用于发出元数据，如有必要。</span><span class="sxs-lookup"><span data-stu-id="7e940-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="7e940-112">指向将存储添加的文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="7e940-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e940-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7e940-113">Return Value</span></span>  
 <span data-ttu-id="7e940-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="7e940-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e940-115">要求</span><span class="sxs-lookup"><span data-stu-id="7e940-115">Requirements</span></span>  
 <span data-ttu-id="7e940-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="7e940-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e940-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e940-117">See Also</span></span>  
 [<span data-ttu-id="7e940-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="7e940-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="7e940-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="7e940-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="7e940-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="7e940-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
