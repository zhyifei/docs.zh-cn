---
title: "OLE DB 架构集合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e120ea532b6da455e31ce7345b6c4b2be1ec975f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="9c0b5-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="9c0b5-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="9c0b5-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="9c0b5-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="9c0b5-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="9c0b5-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="9c0b5-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="9c0b5-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9c0b5-106">表</span><span class="sxs-lookup"><span data-stu-id="9c0b5-106">Tables</span></span>  
  
-   <span data-ttu-id="9c0b5-107">Columns</span><span class="sxs-lookup"><span data-stu-id="9c0b5-107">Columns</span></span>  
  
-   <span data-ttu-id="9c0b5-108">过程</span><span class="sxs-lookup"><span data-stu-id="9c0b5-108">Procedures</span></span>  
  
-   <span data-ttu-id="9c0b5-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9c0b5-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9c0b5-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="9c0b5-110">Catalog</span></span>  
  
-   <span data-ttu-id="9c0b5-111">索引</span><span class="sxs-lookup"><span data-stu-id="9c0b5-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9c0b5-112">表</span><span class="sxs-lookup"><span data-stu-id="9c0b5-112">Tables</span></span>  
  
|<span data-ttu-id="9c0b5-113">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-113">ColumnName</span></span>|<span data-ttu-id="9c0b5-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-115">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-116">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-116">String</span></span>|  
|<span data-ttu-id="9c0b5-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-118">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-118">String</span></span>|  
|<span data-ttu-id="9c0b5-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-119">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-120">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-120">String</span></span>|  
|<span data-ttu-id="9c0b5-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-121">TABLE_TYPE</span></span>|<span data-ttu-id="9c0b5-122">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-122">String</span></span>|  
|<span data-ttu-id="9c0b5-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-123">TABLE_GUID</span></span>|<span data-ttu-id="9c0b5-124">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-124">Guid</span></span>|  
|<span data-ttu-id="9c0b5-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-125">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-126">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-126">String</span></span>|  
|<span data-ttu-id="9c0b5-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-127">TABLE_PROPID</span></span>|<span data-ttu-id="9c0b5-128">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-128">Int64</span></span>|  
|<span data-ttu-id="9c0b5-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-129">DATE_CREATED</span></span>|<span data-ttu-id="9c0b5-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-130">DateTime</span></span>|  
|<span data-ttu-id="9c0b5-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-131">DATE_MODIFIED</span></span>|<span data-ttu-id="9c0b5-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9c0b5-133">Columns</span><span class="sxs-lookup"><span data-stu-id="9c0b5-133">Columns</span></span>  
  
|<span data-ttu-id="9c0b5-134">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-134">ColumnName</span></span>|<span data-ttu-id="9c0b5-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-136">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-137">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-137">String</span></span>|  
|<span data-ttu-id="9c0b5-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-139">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-139">String</span></span>|  
|<span data-ttu-id="9c0b5-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-140">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-141">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-141">String</span></span>|  
|<span data-ttu-id="9c0b5-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-142">COLUMN_NAME</span></span>|<span data-ttu-id="9c0b5-143">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-143">String</span></span>|  
|<span data-ttu-id="9c0b5-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-144">COLUMN_GUID</span></span>|<span data-ttu-id="9c0b5-145">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-145">Guid</span></span>|  
|<span data-ttu-id="9c0b5-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-146">COLUMN_PROPID</span></span>|<span data-ttu-id="9c0b5-147">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-147">Int64</span></span>|  
|<span data-ttu-id="9c0b5-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="9c0b5-149">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-149">Int64</span></span>|  
|<span data-ttu-id="9c0b5-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9c0b5-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9c0b5-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-151">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9c0b5-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9c0b5-153">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-153">String</span></span>|  
|<span data-ttu-id="9c0b5-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="9c0b5-155">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-155">Int64</span></span>|  
|<span data-ttu-id="9c0b5-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-156">IS_NULLABLE</span></span>|<span data-ttu-id="9c0b5-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-157">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-158">DATA_TYPE</span></span>|<span data-ttu-id="9c0b5-159">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-159">Int32</span></span>|  
|<span data-ttu-id="9c0b5-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-160">TYPE_GUID</span></span>|<span data-ttu-id="9c0b5-161">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-161">Guid</span></span>|  
|<span data-ttu-id="9c0b5-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9c0b5-163">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-163">Int64</span></span>|  
|<span data-ttu-id="9c0b5-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9c0b5-165">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-165">Int64</span></span>|  
|<span data-ttu-id="9c0b5-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9c0b5-167">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-167">Int32</span></span>|  
|<span data-ttu-id="9c0b5-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="9c0b5-169">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-169">Int16</span></span>|  
|<span data-ttu-id="9c0b5-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="9c0b5-171">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-171">Int64</span></span>|  
|<span data-ttu-id="9c0b5-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9c0b5-173">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-173">String</span></span>|  
|<span data-ttu-id="9c0b5-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9c0b5-175">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-175">String</span></span>|  
|<span data-ttu-id="9c0b5-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9c0b5-177">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-177">String</span></span>|  
|<span data-ttu-id="9c0b5-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="9c0b5-179">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-179">String</span></span>|  
|<span data-ttu-id="9c0b5-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9c0b5-181">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-181">String</span></span>|  
|<span data-ttu-id="9c0b5-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-182">COLLATION_NAME</span></span>|<span data-ttu-id="9c0b5-183">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-183">String</span></span>|  
|<span data-ttu-id="9c0b5-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9c0b5-185">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-185">String</span></span>|  
|<span data-ttu-id="9c0b5-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9c0b5-187">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-187">String</span></span>|  
|<span data-ttu-id="9c0b5-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-188">DOMAIN_NAME</span></span>|<span data-ttu-id="9c0b5-189">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-189">String</span></span>|  
|<span data-ttu-id="9c0b5-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-190">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-191">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-191">String</span></span>|  
|<span data-ttu-id="9c0b5-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-192">COLUMN_LCID</span></span>|<span data-ttu-id="9c0b5-193">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-193">Int32</span></span>|  
|<span data-ttu-id="9c0b5-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="9c0b5-195">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-195">Int32</span></span>|  
|<span data-ttu-id="9c0b5-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-196">COLUMN_SORTID</span></span>|<span data-ttu-id="9c0b5-197">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-197">Int32</span></span>|  
|<span data-ttu-id="9c0b5-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="9c0b5-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="9c0b5-199">Byte[]</span></span>|  
|<span data-ttu-id="9c0b5-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-200">IS_COMPUTED</span></span>|<span data-ttu-id="9c0b5-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9c0b5-202">过程</span><span class="sxs-lookup"><span data-stu-id="9c0b5-202">Procedures</span></span>  
  
|<span data-ttu-id="9c0b5-203">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-203">ColumnName</span></span>|<span data-ttu-id="9c0b5-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9c0b5-206">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-206">String</span></span>|  
|<span data-ttu-id="9c0b5-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-208">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-208">String</span></span>|  
|<span data-ttu-id="9c0b5-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="9c0b5-210">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-210">String</span></span>|  
|<span data-ttu-id="9c0b5-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9c0b5-212">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-212">Int16</span></span>|  
|<span data-ttu-id="9c0b5-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9c0b5-214">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-214">String</span></span>|  
|<span data-ttu-id="9c0b5-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-215">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-216">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-216">String</span></span>|  
|<span data-ttu-id="9c0b5-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-217">DATE_CREATED</span></span>|<span data-ttu-id="9c0b5-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-218">DateTime</span></span>|  
|<span data-ttu-id="9c0b5-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-219">DATE_MODIFIED</span></span>|<span data-ttu-id="9c0b5-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9c0b5-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9c0b5-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9c0b5-222">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-222">ColumnName</span></span>|<span data-ttu-id="9c0b5-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9c0b5-225">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-225">String</span></span>|  
|<span data-ttu-id="9c0b5-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-227">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-227">String</span></span>|  
|<span data-ttu-id="9c0b5-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="9c0b5-229">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-229">String</span></span>|  
|<span data-ttu-id="9c0b5-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-230">PARAMETER_NAME</span></span>|<span data-ttu-id="9c0b5-231">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-231">String</span></span>|  
|<span data-ttu-id="9c0b5-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="9c0b5-233">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-233">Int32</span></span>|  
|<span data-ttu-id="9c0b5-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="9c0b5-235">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-235">Int32</span></span>|  
|<span data-ttu-id="9c0b5-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9c0b5-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="9c0b5-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-237">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9c0b5-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="9c0b5-239">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-239">String</span></span>|  
|<span data-ttu-id="9c0b5-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-240">IS_NULLABLE</span></span>|<span data-ttu-id="9c0b5-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-241">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-242">DATA_TYPE</span></span>|<span data-ttu-id="9c0b5-243">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-243">Int32</span></span>|  
|<span data-ttu-id="9c0b5-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9c0b5-245">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-245">Int64</span></span>|  
|<span data-ttu-id="9c0b5-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9c0b5-247">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-247">Int64</span></span>|  
|<span data-ttu-id="9c0b5-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9c0b5-249">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-249">Int32</span></span>|  
|<span data-ttu-id="9c0b5-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="9c0b5-251">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-251">Int16</span></span>|  
|<span data-ttu-id="9c0b5-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-252">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-253">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-253">String</span></span>|  
|<span data-ttu-id="9c0b5-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-254">TYPE_NAME</span></span>|<span data-ttu-id="9c0b5-255">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-255">String</span></span>|  
|<span data-ttu-id="9c0b5-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="9c0b5-257">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="9c0b5-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="9c0b5-258">Catalog</span></span>  
  
|<span data-ttu-id="9c0b5-259">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-259">ColumnName</span></span>|<span data-ttu-id="9c0b5-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-261">CATALOG_NAME</span></span>|<span data-ttu-id="9c0b5-262">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-262">String</span></span>|  
|<span data-ttu-id="9c0b5-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-263">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-264">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9c0b5-265">索引</span><span class="sxs-lookup"><span data-stu-id="9c0b5-265">Indexes</span></span>  
  
|<span data-ttu-id="9c0b5-266">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-266">ColumnName</span></span>|<span data-ttu-id="9c0b5-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-268">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-269">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-269">String</span></span>|  
|<span data-ttu-id="9c0b5-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-271">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-271">String</span></span>|  
|<span data-ttu-id="9c0b5-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-272">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-273">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-273">String</span></span>|  
|<span data-ttu-id="9c0b5-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-274">INDEX_CATALOG</span></span>|<span data-ttu-id="9c0b5-275">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-275">String</span></span>|  
|<span data-ttu-id="9c0b5-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="9c0b5-277">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-277">String</span></span>|  
|<span data-ttu-id="9c0b5-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-278">INDEX_NAME</span></span>|<span data-ttu-id="9c0b5-279">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-279">String</span></span>|  
|<span data-ttu-id="9c0b5-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9c0b5-280">PRIMARY_KEY</span></span>|<span data-ttu-id="9c0b5-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-281">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-282">UNIQUE</span></span>|<span data-ttu-id="9c0b5-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-283">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-284">CLUSTERED</span></span>|<span data-ttu-id="9c0b5-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-285">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-286">TYPE</span></span>|<span data-ttu-id="9c0b5-287">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-287">Int32</span></span>|  
|<span data-ttu-id="9c0b5-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9c0b5-288">FILL_FACTOR</span></span>|<span data-ttu-id="9c0b5-289">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-289">Int32</span></span>|  
|<span data-ttu-id="9c0b5-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-290">INITIAL_SIZE</span></span>|<span data-ttu-id="9c0b5-291">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-291">Int32</span></span>|  
|<span data-ttu-id="9c0b5-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-292">NULLS</span></span>|<span data-ttu-id="9c0b5-293">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-293">Int32</span></span>|  
|<span data-ttu-id="9c0b5-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9c0b5-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-295">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-296">AUTO_UPDATE</span></span>|<span data-ttu-id="9c0b5-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-297">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-298">NULL_COLLATION</span></span>|<span data-ttu-id="9c0b5-299">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-299">Int32</span></span>|  
|<span data-ttu-id="9c0b5-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="9c0b5-301">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-301">Int64</span></span>|  
|<span data-ttu-id="9c0b5-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-302">COLUMN_NAME</span></span>|<span data-ttu-id="9c0b5-303">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-303">String</span></span>|  
|<span data-ttu-id="9c0b5-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-304">COLUMN_GUID</span></span>|<span data-ttu-id="9c0b5-305">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-305">Guid</span></span>|  
|<span data-ttu-id="9c0b5-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-306">COLUMN_PROPID</span></span>|<span data-ttu-id="9c0b5-307">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-307">Int64</span></span>|  
|<span data-ttu-id="9c0b5-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-308">COLLATION</span></span>|<span data-ttu-id="9c0b5-309">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-309">Int16</span></span>|  
|<span data-ttu-id="9c0b5-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9c0b5-310">CARDINALITY</span></span>|<span data-ttu-id="9c0b5-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="9c0b5-311">Decimal</span></span>|  
|<span data-ttu-id="9c0b5-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="9c0b5-312">PAGES</span></span>|<span data-ttu-id="9c0b5-313">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-313">Int32</span></span>|  
|<span data-ttu-id="9c0b5-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-314">FILTER_CONDITION</span></span>|<span data-ttu-id="9c0b5-315">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-315">String</span></span>|  
|<span data-ttu-id="9c0b5-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-316">INTEGRATED</span></span>|<span data-ttu-id="9c0b5-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="9c0b5-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="9c0b5-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="9c0b5-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="9c0b5-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9c0b5-320">表</span><span class="sxs-lookup"><span data-stu-id="9c0b5-320">Tables</span></span>  
  
-   <span data-ttu-id="9c0b5-321">Columns</span><span class="sxs-lookup"><span data-stu-id="9c0b5-321">Columns</span></span>  
  
-   <span data-ttu-id="9c0b5-322">过程</span><span class="sxs-lookup"><span data-stu-id="9c0b5-322">Procedures</span></span>  
  
-   <span data-ttu-id="9c0b5-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9c0b5-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9c0b5-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9c0b5-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9c0b5-325">视图</span><span class="sxs-lookup"><span data-stu-id="9c0b5-325">Views</span></span>  
  
-   <span data-ttu-id="9c0b5-326">索引</span><span class="sxs-lookup"><span data-stu-id="9c0b5-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9c0b5-327">表</span><span class="sxs-lookup"><span data-stu-id="9c0b5-327">Tables</span></span>  
  
|<span data-ttu-id="9c0b5-328">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-328">ColumnName</span></span>|<span data-ttu-id="9c0b5-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-330">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-331">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-331">String</span></span>|  
|<span data-ttu-id="9c0b5-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-333">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-333">String</span></span>|  
|<span data-ttu-id="9c0b5-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-334">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-335">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-335">String</span></span>|  
|<span data-ttu-id="9c0b5-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-336">TABLE_TYPE</span></span>|<span data-ttu-id="9c0b5-337">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-337">String</span></span>|  
|<span data-ttu-id="9c0b5-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-338">TABLE_GUID</span></span>|<span data-ttu-id="9c0b5-339">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-339">Guid</span></span>|  
|<span data-ttu-id="9c0b5-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-340">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-341">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-341">String</span></span>|  
|<span data-ttu-id="9c0b5-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-342">TABLE_PROPID</span></span>|<span data-ttu-id="9c0b5-343">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-343">Int64</span></span>|  
|<span data-ttu-id="9c0b5-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-344">DATE_CREATED</span></span>|<span data-ttu-id="9c0b5-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-345">DateTime</span></span>|  
|<span data-ttu-id="9c0b5-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-346">DATE_MODIFIED</span></span>|<span data-ttu-id="9c0b5-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9c0b5-348">Columns</span><span class="sxs-lookup"><span data-stu-id="9c0b5-348">Columns</span></span>  
  
|<span data-ttu-id="9c0b5-349">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-349">ColumnName</span></span>|<span data-ttu-id="9c0b5-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-351">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-352">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-352">String</span></span>|  
|<span data-ttu-id="9c0b5-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-354">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-354">String</span></span>|  
|<span data-ttu-id="9c0b5-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-355">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-356">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-356">String</span></span>|  
|<span data-ttu-id="9c0b5-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-357">COLUMN_NAME</span></span>|<span data-ttu-id="9c0b5-358">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-358">String</span></span>|  
|<span data-ttu-id="9c0b5-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-359">COLUMN_GUID</span></span>|<span data-ttu-id="9c0b5-360">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-360">Guid</span></span>|  
|<span data-ttu-id="9c0b5-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-361">COLUMN_PROPID</span></span>|<span data-ttu-id="9c0b5-362">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-362">Int64</span></span>|  
|<span data-ttu-id="9c0b5-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="9c0b5-364">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-364">Int64</span></span>|  
|<span data-ttu-id="9c0b5-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9c0b5-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9c0b5-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-366">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9c0b5-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9c0b5-368">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-368">String</span></span>|  
|<span data-ttu-id="9c0b5-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="9c0b5-370">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-370">Int64</span></span>|  
|<span data-ttu-id="9c0b5-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-371">IS_NULLABLE</span></span>|<span data-ttu-id="9c0b5-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-372">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-373">DATA_TYPE</span></span>|<span data-ttu-id="9c0b5-374">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-374">Int32</span></span>|  
|<span data-ttu-id="9c0b5-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-375">TYPE_GUID</span></span>|<span data-ttu-id="9c0b5-376">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-376">Guid</span></span>|  
|<span data-ttu-id="9c0b5-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9c0b5-378">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-378">Int64</span></span>|  
|<span data-ttu-id="9c0b5-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9c0b5-380">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-380">Int64</span></span>|  
|<span data-ttu-id="9c0b5-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9c0b5-382">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-382">Int32</span></span>|  
|<span data-ttu-id="9c0b5-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="9c0b5-384">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-384">Int16</span></span>|  
|<span data-ttu-id="9c0b5-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="9c0b5-386">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-386">Int64</span></span>|  
|<span data-ttu-id="9c0b5-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9c0b5-388">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-388">String</span></span>|  
|<span data-ttu-id="9c0b5-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9c0b5-390">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-390">String</span></span>|  
|<span data-ttu-id="9c0b5-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9c0b5-392">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-392">String</span></span>|  
|<span data-ttu-id="9c0b5-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="9c0b5-394">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-394">String</span></span>|  
|<span data-ttu-id="9c0b5-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9c0b5-396">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-396">String</span></span>|  
|<span data-ttu-id="9c0b5-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-397">COLLATION_NAME</span></span>|<span data-ttu-id="9c0b5-398">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-398">String</span></span>|  
|<span data-ttu-id="9c0b5-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9c0b5-400">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-400">String</span></span>|  
|<span data-ttu-id="9c0b5-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9c0b5-402">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-402">String</span></span>|  
|<span data-ttu-id="9c0b5-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-403">DOMAIN_NAME</span></span>|<span data-ttu-id="9c0b5-404">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-404">String</span></span>|  
|<span data-ttu-id="9c0b5-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-405">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-406">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9c0b5-407">过程</span><span class="sxs-lookup"><span data-stu-id="9c0b5-407">Procedures</span></span>  
  
|<span data-ttu-id="9c0b5-408">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-408">ColumnName</span></span>|<span data-ttu-id="9c0b5-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9c0b5-411">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-411">String</span></span>|  
|<span data-ttu-id="9c0b5-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-413">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-413">String</span></span>|  
|<span data-ttu-id="9c0b5-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="9c0b5-415">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-415">String</span></span>|  
|<span data-ttu-id="9c0b5-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9c0b5-417">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-417">Int16</span></span>|  
|<span data-ttu-id="9c0b5-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9c0b5-419">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-419">String</span></span>|  
|<span data-ttu-id="9c0b5-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-420">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-421">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-421">String</span></span>|  
|<span data-ttu-id="9c0b5-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-422">DATE_CREATED</span></span>|<span data-ttu-id="9c0b5-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-423">DateTime</span></span>|  
|<span data-ttu-id="9c0b5-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-424">DATE_MODIFIED</span></span>|<span data-ttu-id="9c0b5-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9c0b5-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9c0b5-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9c0b5-427">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-427">ColumnName</span></span>|<span data-ttu-id="9c0b5-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9c0b5-430">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-430">String</span></span>|  
|<span data-ttu-id="9c0b5-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-432">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-432">String</span></span>|  
|<span data-ttu-id="9c0b5-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="9c0b5-434">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-434">String</span></span>|  
|<span data-ttu-id="9c0b5-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-435">COLUMN_NAME</span></span>|<span data-ttu-id="9c0b5-436">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-436">String</span></span>|  
|<span data-ttu-id="9c0b5-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-437">COLUMN_GUID</span></span>|<span data-ttu-id="9c0b5-438">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-438">Guid</span></span>|  
|<span data-ttu-id="9c0b5-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-439">COLUMN_PROPID</span></span>|<span data-ttu-id="9c0b5-440">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-440">Int64</span></span>|  
|<span data-ttu-id="9c0b5-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="9c0b5-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="9c0b5-442">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-442">Int64</span></span>|  
|<span data-ttu-id="9c0b5-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="9c0b5-444">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-444">Int64</span></span>|  
|<span data-ttu-id="9c0b5-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-445">IS_NULLABLE</span></span>|<span data-ttu-id="9c0b5-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-446">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-447">DATA_TYPE</span></span>|<span data-ttu-id="9c0b5-448">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-448">Int32</span></span>|  
|<span data-ttu-id="9c0b5-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-449">TYPE_GUID</span></span>|<span data-ttu-id="9c0b5-450">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-450">Guid</span></span>|  
|<span data-ttu-id="9c0b5-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9c0b5-452">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-452">Int64</span></span>|  
|<span data-ttu-id="9c0b5-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9c0b5-454">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-454">Int64</span></span>|  
|<span data-ttu-id="9c0b5-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9c0b5-456">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-456">Int32</span></span>|  
|<span data-ttu-id="9c0b5-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="9c0b5-458">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-458">Int16</span></span>|  
|<span data-ttu-id="9c0b5-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-459">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-460">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-460">String</span></span>|  
|<span data-ttu-id="9c0b5-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9c0b5-461">OVERLOAD</span></span>|<span data-ttu-id="9c0b5-462">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9c0b5-463">视图</span><span class="sxs-lookup"><span data-stu-id="9c0b5-463">Views</span></span>  
  
|<span data-ttu-id="9c0b5-464">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-464">ColumnName</span></span>|<span data-ttu-id="9c0b5-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-466">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-467">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-467">String</span></span>|  
|<span data-ttu-id="9c0b5-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-469">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-469">String</span></span>|  
|<span data-ttu-id="9c0b5-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-470">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-471">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-471">String</span></span>|  
|<span data-ttu-id="9c0b5-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="9c0b5-473">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-473">String</span></span>|  
|<span data-ttu-id="9c0b5-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-474">CHECK_OPTION</span></span>|<span data-ttu-id="9c0b5-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-475">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-476">IS_UPDATABLE</span></span>|<span data-ttu-id="9c0b5-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-477">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-478">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-479">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-479">String</span></span>|  
|<span data-ttu-id="9c0b5-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-480">DATE_CREATED</span></span>|<span data-ttu-id="9c0b5-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-481">DateTime</span></span>|  
|<span data-ttu-id="9c0b5-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-482">DATE_MODIFIED</span></span>|<span data-ttu-id="9c0b5-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9c0b5-484">索引</span><span class="sxs-lookup"><span data-stu-id="9c0b5-484">Indexes</span></span>  
  
|<span data-ttu-id="9c0b5-485">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-485">ColumnName</span></span>|<span data-ttu-id="9c0b5-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-487">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-488">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-488">String</span></span>|  
|<span data-ttu-id="9c0b5-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-490">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-490">String</span></span>|  
|<span data-ttu-id="9c0b5-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-491">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-492">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-492">String</span></span>|  
|<span data-ttu-id="9c0b5-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-493">INDEX_CATALOG</span></span>|<span data-ttu-id="9c0b5-494">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-494">String</span></span>|  
|<span data-ttu-id="9c0b5-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="9c0b5-496">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-496">String</span></span>|  
|<span data-ttu-id="9c0b5-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-497">INDEX_NAME</span></span>|<span data-ttu-id="9c0b5-498">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-498">String</span></span>|  
|<span data-ttu-id="9c0b5-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9c0b5-499">PRIMARY_KEY</span></span>|<span data-ttu-id="9c0b5-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-500">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-501">UNIQUE</span></span>|<span data-ttu-id="9c0b5-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-502">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-503">CLUSTERED</span></span>|<span data-ttu-id="9c0b5-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-504">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-505">TYPE</span></span>|<span data-ttu-id="9c0b5-506">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-506">Int32</span></span>|  
|<span data-ttu-id="9c0b5-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9c0b5-507">FILL_FACTOR</span></span>|<span data-ttu-id="9c0b5-508">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-508">Int32</span></span>|  
|<span data-ttu-id="9c0b5-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-509">INITIAL_SIZE</span></span>|<span data-ttu-id="9c0b5-510">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-510">Int32</span></span>|  
|<span data-ttu-id="9c0b5-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-511">NULLS</span></span>|<span data-ttu-id="9c0b5-512">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-512">Int32</span></span>|  
|<span data-ttu-id="9c0b5-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9c0b5-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-514">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-515">AUTO_UPDATE</span></span>|<span data-ttu-id="9c0b5-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-516">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-517">NULL_COLLATION</span></span>|<span data-ttu-id="9c0b5-518">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-518">Int32</span></span>|  
|<span data-ttu-id="9c0b5-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="9c0b5-520">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-520">Int64</span></span>|  
|<span data-ttu-id="9c0b5-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-521">COLUMN_NAME</span></span>|<span data-ttu-id="9c0b5-522">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-522">String</span></span>|  
|<span data-ttu-id="9c0b5-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-523">COLUMN_GUID</span></span>|<span data-ttu-id="9c0b5-524">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-524">Guid</span></span>|  
|<span data-ttu-id="9c0b5-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-525">COLUMN_PROPID</span></span>|<span data-ttu-id="9c0b5-526">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-526">Int64</span></span>|  
|<span data-ttu-id="9c0b5-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-527">COLLATION</span></span>|<span data-ttu-id="9c0b5-528">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-528">Int16</span></span>|  
|<span data-ttu-id="9c0b5-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9c0b5-529">CARDINALITY</span></span>|<span data-ttu-id="9c0b5-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="9c0b5-530">Decimal</span></span>|  
|<span data-ttu-id="9c0b5-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="9c0b5-531">PAGES</span></span>|<span data-ttu-id="9c0b5-532">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-532">Int32</span></span>|  
|<span data-ttu-id="9c0b5-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-533">FILTER_CONDITION</span></span>|<span data-ttu-id="9c0b5-534">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-534">String</span></span>|  
|<span data-ttu-id="9c0b5-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-535">INTEGRATED</span></span>|<span data-ttu-id="9c0b5-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="9c0b5-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="9c0b5-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="9c0b5-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="9c0b5-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9c0b5-539">表</span><span class="sxs-lookup"><span data-stu-id="9c0b5-539">Tables</span></span>  
  
-   <span data-ttu-id="9c0b5-540">Columns</span><span class="sxs-lookup"><span data-stu-id="9c0b5-540">Columns</span></span>  
  
-   <span data-ttu-id="9c0b5-541">过程</span><span class="sxs-lookup"><span data-stu-id="9c0b5-541">Procedures</span></span>  
  
-   <span data-ttu-id="9c0b5-542">视图</span><span class="sxs-lookup"><span data-stu-id="9c0b5-542">Views</span></span>  
  
-   <span data-ttu-id="9c0b5-543">索引</span><span class="sxs-lookup"><span data-stu-id="9c0b5-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9c0b5-544">表</span><span class="sxs-lookup"><span data-stu-id="9c0b5-544">Tables</span></span>  
  
|<span data-ttu-id="9c0b5-545">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-545">ColumnName</span></span>|<span data-ttu-id="9c0b5-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-547">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-548">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-548">String</span></span>|  
|<span data-ttu-id="9c0b5-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-550">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-550">String</span></span>|  
|<span data-ttu-id="9c0b5-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-551">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-552">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-552">String</span></span>|  
|<span data-ttu-id="9c0b5-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-553">TABLE_TYPE</span></span>|<span data-ttu-id="9c0b5-554">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-554">String</span></span>|  
|<span data-ttu-id="9c0b5-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-555">TABLE_GUID</span></span>|<span data-ttu-id="9c0b5-556">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-556">Guid</span></span>|  
|<span data-ttu-id="9c0b5-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-557">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-558">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-558">String</span></span>|  
|<span data-ttu-id="9c0b5-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-559">TABLE_PROPID</span></span>|<span data-ttu-id="9c0b5-560">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-560">Int64</span></span>|  
|<span data-ttu-id="9c0b5-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-561">DATE_CREATED</span></span>|<span data-ttu-id="9c0b5-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-562">DateTime</span></span>|  
|<span data-ttu-id="9c0b5-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-563">DATE_MODIFIED</span></span>|<span data-ttu-id="9c0b5-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9c0b5-565">Columns</span><span class="sxs-lookup"><span data-stu-id="9c0b5-565">Columns</span></span>  
  
|<span data-ttu-id="9c0b5-566">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-566">ColumnName</span></span>|<span data-ttu-id="9c0b5-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-568">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-569">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-569">String</span></span>|  
|<span data-ttu-id="9c0b5-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-571">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-571">String</span></span>|  
|<span data-ttu-id="9c0b5-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-572">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-573">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-573">String</span></span>|  
|<span data-ttu-id="9c0b5-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-574">COLUMN_NAME</span></span>|<span data-ttu-id="9c0b5-575">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-575">String</span></span>|  
|<span data-ttu-id="9c0b5-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-576">COLUMN_GUID</span></span>|<span data-ttu-id="9c0b5-577">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-577">Guid</span></span>|  
|<span data-ttu-id="9c0b5-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-578">COLUMN_PROPID</span></span>|<span data-ttu-id="9c0b5-579">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-579">Int64</span></span>|  
|<span data-ttu-id="9c0b5-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="9c0b5-581">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-581">Int64</span></span>|  
|<span data-ttu-id="9c0b5-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9c0b5-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9c0b5-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-583">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9c0b5-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9c0b5-585">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-585">String</span></span>|  
|<span data-ttu-id="9c0b5-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="9c0b5-587">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-587">Int64</span></span>|  
|<span data-ttu-id="9c0b5-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-588">IS_NULLABLE</span></span>|<span data-ttu-id="9c0b5-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-589">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-590">DATA_TYPE</span></span>|<span data-ttu-id="9c0b5-591">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-591">Int32</span></span>|  
|<span data-ttu-id="9c0b5-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-592">TYPE_GUID</span></span>|<span data-ttu-id="9c0b5-593">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-593">Guid</span></span>|  
|<span data-ttu-id="9c0b5-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9c0b5-595">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-595">Int64</span></span>|  
|<span data-ttu-id="9c0b5-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9c0b5-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9c0b5-597">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-597">Int64</span></span>|  
|<span data-ttu-id="9c0b5-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9c0b5-599">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-599">Int32</span></span>|  
|<span data-ttu-id="9c0b5-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="9c0b5-601">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-601">Int16</span></span>|  
|<span data-ttu-id="9c0b5-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="9c0b5-603">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-603">Int64</span></span>|  
|<span data-ttu-id="9c0b5-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9c0b5-605">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-605">String</span></span>|  
|<span data-ttu-id="9c0b5-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9c0b5-607">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-607">String</span></span>|  
|<span data-ttu-id="9c0b5-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9c0b5-609">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-609">String</span></span>|  
|<span data-ttu-id="9c0b5-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="9c0b5-611">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-611">String</span></span>|  
|<span data-ttu-id="9c0b5-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9c0b5-613">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-613">String</span></span>|  
|<span data-ttu-id="9c0b5-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-614">COLLATION_NAME</span></span>|<span data-ttu-id="9c0b5-615">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-615">String</span></span>|  
|<span data-ttu-id="9c0b5-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9c0b5-617">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-617">String</span></span>|  
|<span data-ttu-id="9c0b5-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9c0b5-619">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-619">String</span></span>|  
|<span data-ttu-id="9c0b5-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-620">DOMAIN_NAME</span></span>|<span data-ttu-id="9c0b5-621">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-621">String</span></span>|  
|<span data-ttu-id="9c0b5-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-622">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-623">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9c0b5-624">过程</span><span class="sxs-lookup"><span data-stu-id="9c0b5-624">Procedures</span></span>  
  
|<span data-ttu-id="9c0b5-625">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-625">ColumnName</span></span>|<span data-ttu-id="9c0b5-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9c0b5-628">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-628">String</span></span>|  
|<span data-ttu-id="9c0b5-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-630">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-630">String</span></span>|  
|<span data-ttu-id="9c0b5-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="9c0b5-632">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-632">String</span></span>|  
|<span data-ttu-id="9c0b5-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9c0b5-634">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-634">Int16</span></span>|  
|<span data-ttu-id="9c0b5-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9c0b5-636">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-636">String</span></span>|  
|<span data-ttu-id="9c0b5-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-637">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-638">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-638">String</span></span>|  
|<span data-ttu-id="9c0b5-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-639">DATE_CREATED</span></span>|<span data-ttu-id="9c0b5-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-640">DateTime</span></span>|  
|<span data-ttu-id="9c0b5-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-641">DATE_MODIFIED</span></span>|<span data-ttu-id="9c0b5-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9c0b5-643">视图</span><span class="sxs-lookup"><span data-stu-id="9c0b5-643">Views</span></span>  
  
|<span data-ttu-id="9c0b5-644">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-644">ColumnName</span></span>|<span data-ttu-id="9c0b5-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-646">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-647">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-647">String</span></span>|  
|<span data-ttu-id="9c0b5-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-649">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-649">String</span></span>|  
|<span data-ttu-id="9c0b5-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-650">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-651">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-651">String</span></span>|  
|<span data-ttu-id="9c0b5-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="9c0b5-653">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-653">String</span></span>|  
|<span data-ttu-id="9c0b5-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-654">CHECK_OPTION</span></span>|<span data-ttu-id="9c0b5-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-655">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-656">IS_UPDATABLE</span></span>|<span data-ttu-id="9c0b5-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-657">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-658">DESCRIPTION</span></span>|<span data-ttu-id="9c0b5-659">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-659">String</span></span>|  
|<span data-ttu-id="9c0b5-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-660">DATE_CREATED</span></span>|<span data-ttu-id="9c0b5-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-661">DateTime</span></span>|  
|<span data-ttu-id="9c0b5-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-662">DATE_MODIFIED</span></span>|<span data-ttu-id="9c0b5-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c0b5-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9c0b5-664">索引</span><span class="sxs-lookup"><span data-stu-id="9c0b5-664">Indexes</span></span>  
  
|<span data-ttu-id="9c0b5-665">列名</span><span class="sxs-lookup"><span data-stu-id="9c0b5-665">ColumnName</span></span>|<span data-ttu-id="9c0b5-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0b5-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9c0b5-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-667">TABLE_CATALOG</span></span>|<span data-ttu-id="9c0b5-668">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-668">String</span></span>|  
|<span data-ttu-id="9c0b5-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="9c0b5-670">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-670">String</span></span>|  
|<span data-ttu-id="9c0b5-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-671">TABLE_NAME</span></span>|<span data-ttu-id="9c0b5-672">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-672">String</span></span>|  
|<span data-ttu-id="9c0b5-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9c0b5-673">INDEX_CATALOG</span></span>|<span data-ttu-id="9c0b5-674">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-674">String</span></span>|  
|<span data-ttu-id="9c0b5-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9c0b5-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="9c0b5-676">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-676">String</span></span>|  
|<span data-ttu-id="9c0b5-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-677">INDEX_NAME</span></span>|<span data-ttu-id="9c0b5-678">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-678">String</span></span>|  
|<span data-ttu-id="9c0b5-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9c0b5-679">PRIMARY_KEY</span></span>|<span data-ttu-id="9c0b5-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-680">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-681">UNIQUE</span></span>|<span data-ttu-id="9c0b5-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-682">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-683">CLUSTERED</span></span>|<span data-ttu-id="9c0b5-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-684">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-685">TYPE</span></span>|<span data-ttu-id="9c0b5-686">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-686">Int32</span></span>|  
|<span data-ttu-id="9c0b5-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9c0b5-687">FILL_FACTOR</span></span>|<span data-ttu-id="9c0b5-688">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-688">Int32</span></span>|  
|<span data-ttu-id="9c0b5-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-689">INITIAL_SIZE</span></span>|<span data-ttu-id="9c0b5-690">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-690">Int32</span></span>|  
|<span data-ttu-id="9c0b5-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-691">NULLS</span></span>|<span data-ttu-id="9c0b5-692">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-692">Int32</span></span>|  
|<span data-ttu-id="9c0b5-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9c0b5-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9c0b5-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-694">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9c0b5-695">AUTO_UPDATE</span></span>|<span data-ttu-id="9c0b5-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-696">Boolean</span></span>|  
|<span data-ttu-id="9c0b5-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-697">NULL_COLLATION</span></span>|<span data-ttu-id="9c0b5-698">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-698">Int32</span></span>|  
|<span data-ttu-id="9c0b5-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="9c0b5-700">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-700">Int64</span></span>|  
|<span data-ttu-id="9c0b5-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9c0b5-701">COLUMN_NAME</span></span>|<span data-ttu-id="9c0b5-702">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-702">String</span></span>|  
|<span data-ttu-id="9c0b5-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-703">COLUMN_GUID</span></span>|<span data-ttu-id="9c0b5-704">Guid</span><span class="sxs-lookup"><span data-stu-id="9c0b5-704">Guid</span></span>|  
|<span data-ttu-id="9c0b5-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9c0b5-705">COLUMN_PROPID</span></span>|<span data-ttu-id="9c0b5-706">Int64</span><span class="sxs-lookup"><span data-stu-id="9c0b5-706">Int64</span></span>|  
|<span data-ttu-id="9c0b5-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-707">COLLATION</span></span>|<span data-ttu-id="9c0b5-708">Int16</span><span class="sxs-lookup"><span data-stu-id="9c0b5-708">Int16</span></span>|  
|<span data-ttu-id="9c0b5-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9c0b5-709">CARDINALITY</span></span>|<span data-ttu-id="9c0b5-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="9c0b5-710">Decimal</span></span>|  
|<span data-ttu-id="9c0b5-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="9c0b5-711">PAGES</span></span>|<span data-ttu-id="9c0b5-712">Int32</span><span class="sxs-lookup"><span data-stu-id="9c0b5-712">Int32</span></span>|  
|<span data-ttu-id="9c0b5-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9c0b5-713">FILTER_CONDITION</span></span>|<span data-ttu-id="9c0b5-714">String</span><span class="sxs-lookup"><span data-stu-id="9c0b5-714">String</span></span>|  
|<span data-ttu-id="9c0b5-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9c0b5-715">INTEGRATED</span></span>|<span data-ttu-id="9c0b5-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="9c0b5-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c0b5-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c0b5-717">See Also</span></span>  
 [<span data-ttu-id="9c0b5-718">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="9c0b5-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
