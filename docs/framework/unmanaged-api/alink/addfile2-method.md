---
title: AddFile2 方法
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
ms.openlocfilehash: 8dadf9ec8f896b03e4918b21f5153c1b747010fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446663"
---
# <a name="addfile2-method"></a><span data-ttu-id="28762-102">AddFile2 方法</span><span class="sxs-lookup"><span data-stu-id="28762-102">AddFile2 Method</span></span>
<span data-ttu-id="28762-103">将文件添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="28762-103">Adds files to the assembly.</span></span> <span data-ttu-id="28762-104">还可用于创建未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="28762-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28762-105">语法</span><span class="sxs-lookup"><span data-stu-id="28762-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="28762-106">参数</span><span class="sxs-lookup"><span data-stu-id="28762-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="28762-107">向其中添加文件的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="28762-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="28762-108">要添加的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="28762-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="28762-109">COM + `FileDef` 标志，如 `ffContainsNoMetaData` 和 `ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="28762-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="28762-110">`dwFlags` 传递给[DefineFile 方法](../metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="28762-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="28762-111">[IMetaDataEmit2 接口](../metadata/imetadataemit2-interface.md)接口的接口。</span><span class="sxs-lookup"><span data-stu-id="28762-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="28762-112">接收要添加的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="28762-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28762-113">返回值</span><span class="sxs-lookup"><span data-stu-id="28762-113">Return Value</span></span>  
 <span data-ttu-id="28762-114">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="28762-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28762-115">要求</span><span class="sxs-lookup"><span data-stu-id="28762-115">Requirements</span></span>  
 <span data-ttu-id="28762-116">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="28762-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28762-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28762-117">See also</span></span>

- [<span data-ttu-id="28762-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="28762-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="28762-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="28762-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="28762-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="28762-120">ALink API</span></span>](index.md)
