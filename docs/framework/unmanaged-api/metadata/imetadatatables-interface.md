---
title: "IMetaDataTables 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables
helpviewer_keywords: IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c89d615fbeeff4a60eb386d58c573ee7905f538d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="3c5d3-102">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="3c5d3-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="3c5d3-103">提供存储和检索表中元数据信息的方法。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c5d3-104">方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-104">Methods</span></span>  
  
|<span data-ttu-id="3c5d3-105">方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-105">Method</span></span>|<span data-ttu-id="3c5d3-106">描述</span><span class="sxs-lookup"><span data-stu-id="3c5d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c5d3-107">GetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="3c5d3-108">获取一个指向二进制大型对象 (BLOB) 指定的列索引处。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="3c5d3-109">GetBlobHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="3c5d3-110">获取用字节表示，BLOB 堆的大小。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="3c5d3-111">GetCodedTokenInfo 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="3c5d3-112">获取一个指向与指定的行索引关联的标记数组。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="3c5d3-113">GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="3c5d3-114">获取一个指针指向处指定的列的索引，在指定的表索引的表中的列中包含的值。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="3c5d3-115">GetColumnInfo 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="3c5d3-116">指定表中获取有关指定列的数据。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="3c5d3-117">GetGuid 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="3c5d3-118">从指定索引处的行获取的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="3c5d3-119">GetGuidHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="3c5d3-120">获取用字节表示，GUID 堆的大小。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="3c5d3-121">GetNextBlob 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="3c5d3-122">获取表中的下一个 BLOB 的索引。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="3c5d3-123">GetNextGuid 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="3c5d3-124">获取当前的表列中的下一步的 GUID 值的索引。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="3c5d3-125">GetNextString 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="3c5d3-126">获取当前的表列中的下一步的字符串的索引。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="3c5d3-127">GetNextUserString 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="3c5d3-128">获取包含当前表列中的下一步的硬编码字符串的行的索引。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="3c5d3-129">GetNumTables 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="3c5d3-130">获取当前的作用域中的表数`IMetaDataTables`实例。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="3c5d3-131">GetRow 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="3c5d3-132">获取指定的行索引处，在指定的表索引的表中的一行。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="3c5d3-133">GetString 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="3c5d3-134">获取当前引用作用域中从表的列的指定索引处的字符串。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="3c5d3-135">GetStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="3c5d3-136">获取用字节表示，字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="3c5d3-137">GetTableIndex 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="3c5d3-138">获取指定标记所引用的表的索引。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="3c5d3-139">GetTableInfo 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="3c5d3-140">获取指定的表索引处的名称、 行大小、 的行数、 列数、 和的表的键列索引。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="3c5d3-141">GetUserString 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="3c5d3-142">获取当前范围中的字符串列中的指定索引处的硬编码字符串。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="3c5d3-143">GetUserStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="3c5d3-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="3c5d3-144">获取用字节表示，用户字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c5d3-145">要求</span><span class="sxs-lookup"><span data-stu-id="3c5d3-145">Requirements</span></span>  
 <span data-ttu-id="3c5d3-146">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c5d3-147">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c5d3-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c5d3-148">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3c5d3-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c5d3-149">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c5d3-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5d3-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c5d3-150">See Also</span></span>  
 [<span data-ttu-id="3c5d3-151">元数据接口</span><span class="sxs-lookup"><span data-stu-id="3c5d3-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="3c5d3-152">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="3c5d3-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
