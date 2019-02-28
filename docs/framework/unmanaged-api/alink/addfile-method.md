---
title: AddFile 方法
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c04bc008d0279601e90d13e6a57c52a458fca1d7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967875"
---
# <a name="addfile-method"></a><span data-ttu-id="6729e-102">AddFile 方法</span><span class="sxs-lookup"><span data-stu-id="6729e-102">AddFile Method</span></span>
<span data-ttu-id="6729e-103">将文件添加到该程序集。</span><span class="sxs-lookup"><span data-stu-id="6729e-103">Adds files to the assembly.</span></span> <span data-ttu-id="6729e-104">此外可以用于创建未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="6729e-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6729e-105">语法</span><span class="sxs-lookup"><span data-stu-id="6729e-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6729e-106">参数</span><span class="sxs-lookup"><span data-stu-id="6729e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6729e-107">要进行扩充的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="6729e-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="6729e-108">要添加的文件的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="6729e-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6729e-109">COM + FileDef 标志，如`ffContainsNoMetaData`和`ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="6729e-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="6729e-110">`dwFlags` 传递给[DefineFile 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="6729e-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="6729e-111">[IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)要用来发出元数据，如有必要的接口。</span><span class="sxs-lookup"><span data-stu-id="6729e-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="6729e-112">指向将存储添加的文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="6729e-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6729e-113">返回值</span><span class="sxs-lookup"><span data-stu-id="6729e-113">Return Value</span></span>  
 <span data-ttu-id="6729e-114">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="6729e-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6729e-115">要求</span><span class="sxs-lookup"><span data-stu-id="6729e-115">Requirements</span></span>  
 <span data-ttu-id="6729e-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="6729e-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6729e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6729e-117">See also</span></span>
- [<span data-ttu-id="6729e-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="6729e-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6729e-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="6729e-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6729e-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="6729e-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
