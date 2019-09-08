---
title: ImportFile 方法
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7fee7a91de99e2db69609cbc7c73e22d85d045f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777071"
---
# <a name="importfile-method"></a><span data-ttu-id="4b39b-102">ImportFile 方法</span><span class="sxs-lookup"><span data-stu-id="4b39b-102">ImportFile Method</span></span>
<span data-ttu-id="4b39b-103">导入程序集和未绑定模块。</span><span class="sxs-lookup"><span data-stu-id="4b39b-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b39b-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b39b-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b39b-105">参数</span><span class="sxs-lookup"><span data-stu-id="4b39b-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="4b39b-106">要导入的文件的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="4b39b-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="4b39b-107">可选输出文件名，可用于在文件链接到程序集时对其进行重命名。</span><span class="sxs-lookup"><span data-stu-id="4b39b-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="4b39b-108">如果为 TRUE，则使用 ImportTypes，否则必须手动执行导入。</span><span class="sxs-lookup"><span data-stu-id="4b39b-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="4b39b-109">指向将存储唯一文件 ID 的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="4b39b-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="4b39b-110">该文件可以是程序集或文件。</span><span class="sxs-lookup"><span data-stu-id="4b39b-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="4b39b-111">接收指向[IMetaDataAssemblyImport 接口](../metadata/imetadataassemblyimport-interface.md)的指针。</span><span class="sxs-lookup"><span data-stu-id="4b39b-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="4b39b-112">如果文件不是程序集，则可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4b39b-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="4b39b-113">一个指针，指向已导入的文件和/或范围的计数。</span><span class="sxs-lookup"><span data-stu-id="4b39b-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b39b-114">返回值</span><span class="sxs-lookup"><span data-stu-id="4b39b-114">Return Value</span></span>  
 <span data-ttu-id="4b39b-115">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="4b39b-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b39b-116">要求</span><span class="sxs-lookup"><span data-stu-id="4b39b-116">Requirements</span></span>  
 <span data-ttu-id="4b39b-117">需要 alink</span><span class="sxs-lookup"><span data-stu-id="4b39b-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b39b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b39b-118">See also</span></span>

- [<span data-ttu-id="4b39b-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="4b39b-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4b39b-120">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="4b39b-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4b39b-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="4b39b-121">ALink API</span></span>](index.md)
