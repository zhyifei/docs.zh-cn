---
title: IMetaDataTables 接口
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b2298e2d67e8a50e11d53d864f0e78f3b549e45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645172"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="3e0df-102">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="3e0df-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="3e0df-103">提供存储和检索表中元数据信息的方法。</span><span class="sxs-lookup"><span data-stu-id="3e0df-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e0df-104">方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-104">Methods</span></span>  
  
|<span data-ttu-id="3e0df-105">方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-105">Method</span></span>|<span data-ttu-id="3e0df-106">描述</span><span class="sxs-lookup"><span data-stu-id="3e0df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e0df-107">GetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="3e0df-108">获取一个指向二进制大型对象 (BLOB) 中的指定的列索引处。</span><span class="sxs-lookup"><span data-stu-id="3e0df-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="3e0df-109">GetBlobHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="3e0df-110">获取以字节为单位，在 BLOB 堆的大小。</span><span class="sxs-lookup"><span data-stu-id="3e0df-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="3e0df-111">GetCodedTokenInfo 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="3e0df-112">获取与指定的行索引相关联的标记数组的指针。</span><span class="sxs-lookup"><span data-stu-id="3e0df-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="3e0df-113">GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="3e0df-114">获取一个指针指向包含在指定的列索引，在指定的表索引的表中的列中的值。</span><span class="sxs-lookup"><span data-stu-id="3e0df-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="3e0df-115">GetColumnInfo 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="3e0df-116">指定表中获取有关指定的列的数据。</span><span class="sxs-lookup"><span data-stu-id="3e0df-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="3e0df-117">GetGuid 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="3e0df-118">获取从指定索引处的行的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3e0df-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="3e0df-119">GetGuidHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="3e0df-120">获取以字节为单位，GUID 堆的大小。</span><span class="sxs-lookup"><span data-stu-id="3e0df-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="3e0df-121">GetNextBlob 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="3e0df-122">获取表中的下一个 BLOB 的索引。</span><span class="sxs-lookup"><span data-stu-id="3e0df-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="3e0df-123">GetNextGuid 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="3e0df-124">获取当前表的列中的下一步的 GUID 值的索引。</span><span class="sxs-lookup"><span data-stu-id="3e0df-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="3e0df-125">GetNextString 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="3e0df-126">获取当前表的列中的下一个字符串的索引。</span><span class="sxs-lookup"><span data-stu-id="3e0df-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="3e0df-127">GetNextUserString 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="3e0df-128">获取包含在当前表列中的下一步的硬编码字符串的行的索引。</span><span class="sxs-lookup"><span data-stu-id="3e0df-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="3e0df-129">GetNumTables 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="3e0df-130">获取在当前作用域中的表数`IMetaDataTables`实例。</span><span class="sxs-lookup"><span data-stu-id="3e0df-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="3e0df-131">GetRow 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="3e0df-132">获取指定的行索引处，在指定的表索引的表中的行。</span><span class="sxs-lookup"><span data-stu-id="3e0df-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="3e0df-133">GetString 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="3e0df-134">获取当前引用作用域中从表的列的指定索引处的字符串。</span><span class="sxs-lookup"><span data-stu-id="3e0df-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="3e0df-135">GetStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="3e0df-136">获取以字节为单位的字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="3e0df-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="3e0df-137">GetTableIndex 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="3e0df-138">获取指定的标记所引用的表的索引。</span><span class="sxs-lookup"><span data-stu-id="3e0df-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="3e0df-139">GetTableInfo 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="3e0df-140">获取指定的表索引处的名称、 行大小、 行数、 列数和表的键列索引。</span><span class="sxs-lookup"><span data-stu-id="3e0df-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="3e0df-141">GetUserString 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="3e0df-142">获取在当前作用域中的字符串列中的指定索引处的硬编码的字符串。</span><span class="sxs-lookup"><span data-stu-id="3e0df-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="3e0df-143">GetUserStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="3e0df-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="3e0df-144">获取以字节为单位的用户字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="3e0df-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e0df-145">要求</span><span class="sxs-lookup"><span data-stu-id="3e0df-145">Requirements</span></span>  
 <span data-ttu-id="3e0df-146">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e0df-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e0df-147">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3e0df-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e0df-148">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3e0df-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e0df-149">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e0df-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e0df-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e0df-150">See also</span></span>

- [<span data-ttu-id="3e0df-151">元数据接口</span><span class="sxs-lookup"><span data-stu-id="3e0df-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="3e0df-152">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="3e0df-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
