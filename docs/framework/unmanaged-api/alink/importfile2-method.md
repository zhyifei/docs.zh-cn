---
title: "ImportFile2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportFile2
api_location: alink.dll
api_type: COM
f1_keywords: ImportFile2
helpviewer_keywords: ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4d7e842152e84992124ec29cd551c3b5d50a6d61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="importfile2-method"></a><span data-ttu-id="8a678-102">ImportFile2 方法</span><span class="sxs-lookup"><span data-stu-id="8a678-102">ImportFile2 Method</span></span>
<span data-ttu-id="8a678-103">导入程序集和未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="8a678-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="8a678-104">此方法就像是[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)，但是如果即使正在导入的文件不存在磁盘上的工作。</span><span class="sxs-lookup"><span data-stu-id="8a678-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a678-105">语法</span><span class="sxs-lookup"><span data-stu-id="8a678-105">Syntax</span></span>  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a678-106">参数</span><span class="sxs-lookup"><span data-stu-id="8a678-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="8a678-107">要导入文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8a678-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="8a678-108">可用于重命名该文件并将其链接到程序集的可选的输出文件名称。</span><span class="sxs-lookup"><span data-stu-id="8a678-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="8a678-109">可选的作用域[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="8a678-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="8a678-110">如果为 TRUE，则使用 ImportTypes，必须手动执行否则导入。</span><span class="sxs-lookup"><span data-stu-id="8a678-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="8a678-111">接收的文件或程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="8a678-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="8a678-112">接收[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="8a678-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="8a678-113">如果文件不是程序集为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8a678-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="8a678-114">接收找到的文件和/或导入的作用域。</span><span class="sxs-lookup"><span data-stu-id="8a678-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a678-115">返回值</span><span class="sxs-lookup"><span data-stu-id="8a678-115">Return Value</span></span>  
 <span data-ttu-id="8a678-116">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="8a678-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a678-117">要求</span><span class="sxs-lookup"><span data-stu-id="8a678-117">Requirements</span></span>  
 <span data-ttu-id="8a678-118">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="8a678-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a678-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a678-119">See Also</span></span>  
 [<span data-ttu-id="8a678-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="8a678-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8a678-121">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="8a678-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8a678-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="8a678-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
