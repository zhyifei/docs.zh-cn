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
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446682"
---
# <a name="addfile-method"></a><span data-ttu-id="b5eb5-102">AddFile 方法</span><span class="sxs-lookup"><span data-stu-id="b5eb5-102">AddFile Method</span></span>
<span data-ttu-id="b5eb5-103">将文件添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-103">Adds files to the assembly.</span></span> <span data-ttu-id="b5eb5-104">还可用于创建未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5eb5-105">语法</span><span class="sxs-lookup"><span data-stu-id="b5eb5-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5eb5-106">参数</span><span class="sxs-lookup"><span data-stu-id="b5eb5-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b5eb5-107">要扩充的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="b5eb5-108">要添加的文件的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b5eb5-109">COM + FileDef 标志，如 `ffContainsNoMetaData` 和 `ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="b5eb5-110">`dwFlags` 传递给[DefineFile 方法](../metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="b5eb5-111">要用于发出元数据的[IMetaDataEmit 接口](../metadata/imetadataemit-interface.md)接口（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="b5eb5-112">一个指针，指向将存储所添加文件的唯一 ID 的位置。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5eb5-113">返回值</span><span class="sxs-lookup"><span data-stu-id="b5eb5-113">Return Value</span></span>  
 <span data-ttu-id="b5eb5-114">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5eb5-115">要求</span><span class="sxs-lookup"><span data-stu-id="b5eb5-115">Requirements</span></span>  
 <span data-ttu-id="b5eb5-116">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="b5eb5-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5eb5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5eb5-117">See also</span></span>

- [<span data-ttu-id="b5eb5-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="b5eb5-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b5eb5-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="b5eb5-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b5eb5-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="b5eb5-120">ALink API</span></span>](index.md)
