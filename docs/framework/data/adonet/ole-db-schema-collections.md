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
ms.openlocfilehash: 9b88308c5dad69ed1ba6f48f525931e94f13ef1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="598ca-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="598ca-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="598ca-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="598ca-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="598ca-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="598ca-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="598ca-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="598ca-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="598ca-106">表</span><span class="sxs-lookup"><span data-stu-id="598ca-106">Tables</span></span>  
  
-   <span data-ttu-id="598ca-107">Columns</span><span class="sxs-lookup"><span data-stu-id="598ca-107">Columns</span></span>  
  
-   <span data-ttu-id="598ca-108">过程</span><span class="sxs-lookup"><span data-stu-id="598ca-108">Procedures</span></span>  
  
-   <span data-ttu-id="598ca-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="598ca-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="598ca-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="598ca-110">Catalog</span></span>  
  
-   <span data-ttu-id="598ca-111">索引</span><span class="sxs-lookup"><span data-stu-id="598ca-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="598ca-112">表</span><span class="sxs-lookup"><span data-stu-id="598ca-112">Tables</span></span>  
  
|<span data-ttu-id="598ca-113">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-113">ColumnName</span></span>|<span data-ttu-id="598ca-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-115">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-116">String</span><span class="sxs-lookup"><span data-stu-id="598ca-116">String</span></span>|  
|<span data-ttu-id="598ca-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-118">String</span><span class="sxs-lookup"><span data-stu-id="598ca-118">String</span></span>|  
|<span data-ttu-id="598ca-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-119">TABLE_NAME</span></span>|<span data-ttu-id="598ca-120">String</span><span class="sxs-lookup"><span data-stu-id="598ca-120">String</span></span>|  
|<span data-ttu-id="598ca-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-121">TABLE_TYPE</span></span>|<span data-ttu-id="598ca-122">String</span><span class="sxs-lookup"><span data-stu-id="598ca-122">String</span></span>|  
|<span data-ttu-id="598ca-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-123">TABLE_GUID</span></span>|<span data-ttu-id="598ca-124">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-124">Guid</span></span>|  
|<span data-ttu-id="598ca-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-125">DESCRIPTION</span></span>|<span data-ttu-id="598ca-126">String</span><span class="sxs-lookup"><span data-stu-id="598ca-126">String</span></span>|  
|<span data-ttu-id="598ca-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-127">TABLE_PROPID</span></span>|<span data-ttu-id="598ca-128">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-128">Int64</span></span>|  
|<span data-ttu-id="598ca-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="598ca-129">DATE_CREATED</span></span>|<span data-ttu-id="598ca-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-130">DateTime</span></span>|  
|<span data-ttu-id="598ca-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="598ca-131">DATE_MODIFIED</span></span>|<span data-ttu-id="598ca-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="598ca-133">Columns</span><span class="sxs-lookup"><span data-stu-id="598ca-133">Columns</span></span>  
  
|<span data-ttu-id="598ca-134">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-134">ColumnName</span></span>|<span data-ttu-id="598ca-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-136">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-137">String</span><span class="sxs-lookup"><span data-stu-id="598ca-137">String</span></span>|  
|<span data-ttu-id="598ca-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-139">String</span><span class="sxs-lookup"><span data-stu-id="598ca-139">String</span></span>|  
|<span data-ttu-id="598ca-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-140">TABLE_NAME</span></span>|<span data-ttu-id="598ca-141">String</span><span class="sxs-lookup"><span data-stu-id="598ca-141">String</span></span>|  
|<span data-ttu-id="598ca-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-142">COLUMN_NAME</span></span>|<span data-ttu-id="598ca-143">String</span><span class="sxs-lookup"><span data-stu-id="598ca-143">String</span></span>|  
|<span data-ttu-id="598ca-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-144">COLUMN_GUID</span></span>|<span data-ttu-id="598ca-145">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-145">Guid</span></span>|  
|<span data-ttu-id="598ca-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-146">COLUMN_PROPID</span></span>|<span data-ttu-id="598ca-147">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-147">Int64</span></span>|  
|<span data-ttu-id="598ca-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="598ca-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="598ca-149">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-149">Int64</span></span>|  
|<span data-ttu-id="598ca-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="598ca-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="598ca-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-151">Boolean</span></span>|  
|<span data-ttu-id="598ca-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="598ca-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="598ca-153">String</span><span class="sxs-lookup"><span data-stu-id="598ca-153">String</span></span>|  
|<span data-ttu-id="598ca-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="598ca-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="598ca-155">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-155">Int64</span></span>|  
|<span data-ttu-id="598ca-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="598ca-156">IS_NULLABLE</span></span>|<span data-ttu-id="598ca-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-157">Boolean</span></span>|  
|<span data-ttu-id="598ca-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-158">DATA_TYPE</span></span>|<span data-ttu-id="598ca-159">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-159">Int32</span></span>|  
|<span data-ttu-id="598ca-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-160">TYPE_GUID</span></span>|<span data-ttu-id="598ca-161">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-161">Guid</span></span>|  
|<span data-ttu-id="598ca-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="598ca-163">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-163">Int64</span></span>|  
|<span data-ttu-id="598ca-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="598ca-165">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-165">Int64</span></span>|  
|<span data-ttu-id="598ca-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="598ca-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="598ca-167">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-167">Int32</span></span>|  
|<span data-ttu-id="598ca-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="598ca-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="598ca-169">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-169">Int16</span></span>|  
|<span data-ttu-id="598ca-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="598ca-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="598ca-171">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-171">Int64</span></span>|  
|<span data-ttu-id="598ca-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="598ca-173">String</span><span class="sxs-lookup"><span data-stu-id="598ca-173">String</span></span>|  
|<span data-ttu-id="598ca-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="598ca-175">String</span><span class="sxs-lookup"><span data-stu-id="598ca-175">String</span></span>|  
|<span data-ttu-id="598ca-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="598ca-177">String</span><span class="sxs-lookup"><span data-stu-id="598ca-177">String</span></span>|  
|<span data-ttu-id="598ca-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="598ca-179">String</span><span class="sxs-lookup"><span data-stu-id="598ca-179">String</span></span>|  
|<span data-ttu-id="598ca-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="598ca-181">String</span><span class="sxs-lookup"><span data-stu-id="598ca-181">String</span></span>|  
|<span data-ttu-id="598ca-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-182">COLLATION_NAME</span></span>|<span data-ttu-id="598ca-183">String</span><span class="sxs-lookup"><span data-stu-id="598ca-183">String</span></span>|  
|<span data-ttu-id="598ca-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="598ca-185">String</span><span class="sxs-lookup"><span data-stu-id="598ca-185">String</span></span>|  
|<span data-ttu-id="598ca-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="598ca-187">String</span><span class="sxs-lookup"><span data-stu-id="598ca-187">String</span></span>|  
|<span data-ttu-id="598ca-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-188">DOMAIN_NAME</span></span>|<span data-ttu-id="598ca-189">String</span><span class="sxs-lookup"><span data-stu-id="598ca-189">String</span></span>|  
|<span data-ttu-id="598ca-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-190">DESCRIPTION</span></span>|<span data-ttu-id="598ca-191">String</span><span class="sxs-lookup"><span data-stu-id="598ca-191">String</span></span>|  
|<span data-ttu-id="598ca-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="598ca-192">COLUMN_LCID</span></span>|<span data-ttu-id="598ca-193">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-193">Int32</span></span>|  
|<span data-ttu-id="598ca-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="598ca-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="598ca-195">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-195">Int32</span></span>|  
|<span data-ttu-id="598ca-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="598ca-196">COLUMN_SORTID</span></span>|<span data-ttu-id="598ca-197">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-197">Int32</span></span>|  
|<span data-ttu-id="598ca-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="598ca-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="598ca-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="598ca-199">Byte[]</span></span>|  
|<span data-ttu-id="598ca-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="598ca-200">IS_COMPUTED</span></span>|<span data-ttu-id="598ca-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="598ca-202">过程</span><span class="sxs-lookup"><span data-stu-id="598ca-202">Procedures</span></span>  
  
|<span data-ttu-id="598ca-203">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-203">ColumnName</span></span>|<span data-ttu-id="598ca-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="598ca-206">String</span><span class="sxs-lookup"><span data-stu-id="598ca-206">String</span></span>|  
|<span data-ttu-id="598ca-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="598ca-208">String</span><span class="sxs-lookup"><span data-stu-id="598ca-208">String</span></span>|  
|<span data-ttu-id="598ca-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="598ca-210">String</span><span class="sxs-lookup"><span data-stu-id="598ca-210">String</span></span>|  
|<span data-ttu-id="598ca-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="598ca-212">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-212">Int16</span></span>|  
|<span data-ttu-id="598ca-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="598ca-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="598ca-214">String</span><span class="sxs-lookup"><span data-stu-id="598ca-214">String</span></span>|  
|<span data-ttu-id="598ca-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-215">DESCRIPTION</span></span>|<span data-ttu-id="598ca-216">String</span><span class="sxs-lookup"><span data-stu-id="598ca-216">String</span></span>|  
|<span data-ttu-id="598ca-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="598ca-217">DATE_CREATED</span></span>|<span data-ttu-id="598ca-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-218">DateTime</span></span>|  
|<span data-ttu-id="598ca-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="598ca-219">DATE_MODIFIED</span></span>|<span data-ttu-id="598ca-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="598ca-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="598ca-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="598ca-222">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-222">ColumnName</span></span>|<span data-ttu-id="598ca-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="598ca-225">String</span><span class="sxs-lookup"><span data-stu-id="598ca-225">String</span></span>|  
|<span data-ttu-id="598ca-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="598ca-227">String</span><span class="sxs-lookup"><span data-stu-id="598ca-227">String</span></span>|  
|<span data-ttu-id="598ca-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="598ca-229">String</span><span class="sxs-lookup"><span data-stu-id="598ca-229">String</span></span>|  
|<span data-ttu-id="598ca-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-230">PARAMETER_NAME</span></span>|<span data-ttu-id="598ca-231">String</span><span class="sxs-lookup"><span data-stu-id="598ca-231">String</span></span>|  
|<span data-ttu-id="598ca-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="598ca-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="598ca-233">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-233">Int32</span></span>|  
|<span data-ttu-id="598ca-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="598ca-235">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-235">Int32</span></span>|  
|<span data-ttu-id="598ca-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="598ca-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="598ca-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-237">Boolean</span></span>|  
|<span data-ttu-id="598ca-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="598ca-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="598ca-239">String</span><span class="sxs-lookup"><span data-stu-id="598ca-239">String</span></span>|  
|<span data-ttu-id="598ca-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="598ca-240">IS_NULLABLE</span></span>|<span data-ttu-id="598ca-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-241">Boolean</span></span>|  
|<span data-ttu-id="598ca-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-242">DATA_TYPE</span></span>|<span data-ttu-id="598ca-243">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-243">Int32</span></span>|  
|<span data-ttu-id="598ca-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="598ca-245">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-245">Int64</span></span>|  
|<span data-ttu-id="598ca-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="598ca-247">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-247">Int64</span></span>|  
|<span data-ttu-id="598ca-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="598ca-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="598ca-249">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-249">Int32</span></span>|  
|<span data-ttu-id="598ca-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="598ca-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="598ca-251">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-251">Int16</span></span>|  
|<span data-ttu-id="598ca-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-252">DESCRIPTION</span></span>|<span data-ttu-id="598ca-253">String</span><span class="sxs-lookup"><span data-stu-id="598ca-253">String</span></span>|  
|<span data-ttu-id="598ca-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-254">TYPE_NAME</span></span>|<span data-ttu-id="598ca-255">String</span><span class="sxs-lookup"><span data-stu-id="598ca-255">String</span></span>|  
|<span data-ttu-id="598ca-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="598ca-257">String</span><span class="sxs-lookup"><span data-stu-id="598ca-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="598ca-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="598ca-258">Catalog</span></span>  
  
|<span data-ttu-id="598ca-259">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-259">ColumnName</span></span>|<span data-ttu-id="598ca-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-261">CATALOG_NAME</span></span>|<span data-ttu-id="598ca-262">String</span><span class="sxs-lookup"><span data-stu-id="598ca-262">String</span></span>|  
|<span data-ttu-id="598ca-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-263">DESCRIPTION</span></span>|<span data-ttu-id="598ca-264">String</span><span class="sxs-lookup"><span data-stu-id="598ca-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="598ca-265">索引</span><span class="sxs-lookup"><span data-stu-id="598ca-265">Indexes</span></span>  
  
|<span data-ttu-id="598ca-266">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-266">ColumnName</span></span>|<span data-ttu-id="598ca-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-268">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-269">String</span><span class="sxs-lookup"><span data-stu-id="598ca-269">String</span></span>|  
|<span data-ttu-id="598ca-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-271">String</span><span class="sxs-lookup"><span data-stu-id="598ca-271">String</span></span>|  
|<span data-ttu-id="598ca-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-272">TABLE_NAME</span></span>|<span data-ttu-id="598ca-273">String</span><span class="sxs-lookup"><span data-stu-id="598ca-273">String</span></span>|  
|<span data-ttu-id="598ca-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-274">INDEX_CATALOG</span></span>|<span data-ttu-id="598ca-275">String</span><span class="sxs-lookup"><span data-stu-id="598ca-275">String</span></span>|  
|<span data-ttu-id="598ca-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="598ca-277">String</span><span class="sxs-lookup"><span data-stu-id="598ca-277">String</span></span>|  
|<span data-ttu-id="598ca-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-278">INDEX_NAME</span></span>|<span data-ttu-id="598ca-279">String</span><span class="sxs-lookup"><span data-stu-id="598ca-279">String</span></span>|  
|<span data-ttu-id="598ca-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="598ca-280">PRIMARY_KEY</span></span>|<span data-ttu-id="598ca-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-281">Boolean</span></span>|  
|<span data-ttu-id="598ca-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="598ca-282">UNIQUE</span></span>|<span data-ttu-id="598ca-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-283">Boolean</span></span>|  
|<span data-ttu-id="598ca-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="598ca-284">CLUSTERED</span></span>|<span data-ttu-id="598ca-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-285">Boolean</span></span>|  
|<span data-ttu-id="598ca-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-286">TYPE</span></span>|<span data-ttu-id="598ca-287">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-287">Int32</span></span>|  
|<span data-ttu-id="598ca-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="598ca-288">FILL_FACTOR</span></span>|<span data-ttu-id="598ca-289">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-289">Int32</span></span>|  
|<span data-ttu-id="598ca-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="598ca-290">INITIAL_SIZE</span></span>|<span data-ttu-id="598ca-291">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-291">Int32</span></span>|  
|<span data-ttu-id="598ca-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="598ca-292">NULLS</span></span>|<span data-ttu-id="598ca-293">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-293">Int32</span></span>|  
|<span data-ttu-id="598ca-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="598ca-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="598ca-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-295">Boolean</span></span>|  
|<span data-ttu-id="598ca-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="598ca-296">AUTO_UPDATE</span></span>|<span data-ttu-id="598ca-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-297">Boolean</span></span>|  
|<span data-ttu-id="598ca-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="598ca-298">NULL_COLLATION</span></span>|<span data-ttu-id="598ca-299">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-299">Int32</span></span>|  
|<span data-ttu-id="598ca-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="598ca-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="598ca-301">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-301">Int64</span></span>|  
|<span data-ttu-id="598ca-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-302">COLUMN_NAME</span></span>|<span data-ttu-id="598ca-303">String</span><span class="sxs-lookup"><span data-stu-id="598ca-303">String</span></span>|  
|<span data-ttu-id="598ca-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-304">COLUMN_GUID</span></span>|<span data-ttu-id="598ca-305">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-305">Guid</span></span>|  
|<span data-ttu-id="598ca-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-306">COLUMN_PROPID</span></span>|<span data-ttu-id="598ca-307">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-307">Int64</span></span>|  
|<span data-ttu-id="598ca-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="598ca-308">COLLATION</span></span>|<span data-ttu-id="598ca-309">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-309">Int16</span></span>|  
|<span data-ttu-id="598ca-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="598ca-310">CARDINALITY</span></span>|<span data-ttu-id="598ca-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="598ca-311">Decimal</span></span>|  
|<span data-ttu-id="598ca-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="598ca-312">PAGES</span></span>|<span data-ttu-id="598ca-313">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-313">Int32</span></span>|  
|<span data-ttu-id="598ca-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="598ca-314">FILTER_CONDITION</span></span>|<span data-ttu-id="598ca-315">String</span><span class="sxs-lookup"><span data-stu-id="598ca-315">String</span></span>|  
|<span data-ttu-id="598ca-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="598ca-316">INTEGRATED</span></span>|<span data-ttu-id="598ca-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="598ca-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="598ca-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="598ca-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="598ca-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="598ca-320">表</span><span class="sxs-lookup"><span data-stu-id="598ca-320">Tables</span></span>  
  
-   <span data-ttu-id="598ca-321">Columns</span><span class="sxs-lookup"><span data-stu-id="598ca-321">Columns</span></span>  
  
-   <span data-ttu-id="598ca-322">过程</span><span class="sxs-lookup"><span data-stu-id="598ca-322">Procedures</span></span>  
  
-   <span data-ttu-id="598ca-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="598ca-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="598ca-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="598ca-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="598ca-325">视图</span><span class="sxs-lookup"><span data-stu-id="598ca-325">Views</span></span>  
  
-   <span data-ttu-id="598ca-326">索引</span><span class="sxs-lookup"><span data-stu-id="598ca-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="598ca-327">表</span><span class="sxs-lookup"><span data-stu-id="598ca-327">Tables</span></span>  
  
|<span data-ttu-id="598ca-328">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-328">ColumnName</span></span>|<span data-ttu-id="598ca-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-330">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-331">String</span><span class="sxs-lookup"><span data-stu-id="598ca-331">String</span></span>|  
|<span data-ttu-id="598ca-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-333">String</span><span class="sxs-lookup"><span data-stu-id="598ca-333">String</span></span>|  
|<span data-ttu-id="598ca-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-334">TABLE_NAME</span></span>|<span data-ttu-id="598ca-335">String</span><span class="sxs-lookup"><span data-stu-id="598ca-335">String</span></span>|  
|<span data-ttu-id="598ca-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-336">TABLE_TYPE</span></span>|<span data-ttu-id="598ca-337">String</span><span class="sxs-lookup"><span data-stu-id="598ca-337">String</span></span>|  
|<span data-ttu-id="598ca-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-338">TABLE_GUID</span></span>|<span data-ttu-id="598ca-339">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-339">Guid</span></span>|  
|<span data-ttu-id="598ca-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-340">DESCRIPTION</span></span>|<span data-ttu-id="598ca-341">String</span><span class="sxs-lookup"><span data-stu-id="598ca-341">String</span></span>|  
|<span data-ttu-id="598ca-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-342">TABLE_PROPID</span></span>|<span data-ttu-id="598ca-343">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-343">Int64</span></span>|  
|<span data-ttu-id="598ca-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="598ca-344">DATE_CREATED</span></span>|<span data-ttu-id="598ca-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-345">DateTime</span></span>|  
|<span data-ttu-id="598ca-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="598ca-346">DATE_MODIFIED</span></span>|<span data-ttu-id="598ca-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="598ca-348">Columns</span><span class="sxs-lookup"><span data-stu-id="598ca-348">Columns</span></span>  
  
|<span data-ttu-id="598ca-349">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-349">ColumnName</span></span>|<span data-ttu-id="598ca-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-351">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-352">String</span><span class="sxs-lookup"><span data-stu-id="598ca-352">String</span></span>|  
|<span data-ttu-id="598ca-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-354">String</span><span class="sxs-lookup"><span data-stu-id="598ca-354">String</span></span>|  
|<span data-ttu-id="598ca-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-355">TABLE_NAME</span></span>|<span data-ttu-id="598ca-356">String</span><span class="sxs-lookup"><span data-stu-id="598ca-356">String</span></span>|  
|<span data-ttu-id="598ca-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-357">COLUMN_NAME</span></span>|<span data-ttu-id="598ca-358">String</span><span class="sxs-lookup"><span data-stu-id="598ca-358">String</span></span>|  
|<span data-ttu-id="598ca-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-359">COLUMN_GUID</span></span>|<span data-ttu-id="598ca-360">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-360">Guid</span></span>|  
|<span data-ttu-id="598ca-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-361">COLUMN_PROPID</span></span>|<span data-ttu-id="598ca-362">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-362">Int64</span></span>|  
|<span data-ttu-id="598ca-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="598ca-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="598ca-364">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-364">Int64</span></span>|  
|<span data-ttu-id="598ca-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="598ca-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="598ca-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-366">Boolean</span></span>|  
|<span data-ttu-id="598ca-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="598ca-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="598ca-368">String</span><span class="sxs-lookup"><span data-stu-id="598ca-368">String</span></span>|  
|<span data-ttu-id="598ca-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="598ca-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="598ca-370">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-370">Int64</span></span>|  
|<span data-ttu-id="598ca-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="598ca-371">IS_NULLABLE</span></span>|<span data-ttu-id="598ca-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-372">Boolean</span></span>|  
|<span data-ttu-id="598ca-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-373">DATA_TYPE</span></span>|<span data-ttu-id="598ca-374">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-374">Int32</span></span>|  
|<span data-ttu-id="598ca-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-375">TYPE_GUID</span></span>|<span data-ttu-id="598ca-376">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-376">Guid</span></span>|  
|<span data-ttu-id="598ca-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="598ca-378">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-378">Int64</span></span>|  
|<span data-ttu-id="598ca-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="598ca-380">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-380">Int64</span></span>|  
|<span data-ttu-id="598ca-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="598ca-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="598ca-382">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-382">Int32</span></span>|  
|<span data-ttu-id="598ca-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="598ca-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="598ca-384">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-384">Int16</span></span>|  
|<span data-ttu-id="598ca-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="598ca-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="598ca-386">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-386">Int64</span></span>|  
|<span data-ttu-id="598ca-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="598ca-388">String</span><span class="sxs-lookup"><span data-stu-id="598ca-388">String</span></span>|  
|<span data-ttu-id="598ca-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="598ca-390">String</span><span class="sxs-lookup"><span data-stu-id="598ca-390">String</span></span>|  
|<span data-ttu-id="598ca-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="598ca-392">String</span><span class="sxs-lookup"><span data-stu-id="598ca-392">String</span></span>|  
|<span data-ttu-id="598ca-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="598ca-394">String</span><span class="sxs-lookup"><span data-stu-id="598ca-394">String</span></span>|  
|<span data-ttu-id="598ca-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="598ca-396">String</span><span class="sxs-lookup"><span data-stu-id="598ca-396">String</span></span>|  
|<span data-ttu-id="598ca-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-397">COLLATION_NAME</span></span>|<span data-ttu-id="598ca-398">String</span><span class="sxs-lookup"><span data-stu-id="598ca-398">String</span></span>|  
|<span data-ttu-id="598ca-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="598ca-400">String</span><span class="sxs-lookup"><span data-stu-id="598ca-400">String</span></span>|  
|<span data-ttu-id="598ca-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="598ca-402">String</span><span class="sxs-lookup"><span data-stu-id="598ca-402">String</span></span>|  
|<span data-ttu-id="598ca-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-403">DOMAIN_NAME</span></span>|<span data-ttu-id="598ca-404">String</span><span class="sxs-lookup"><span data-stu-id="598ca-404">String</span></span>|  
|<span data-ttu-id="598ca-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-405">DESCRIPTION</span></span>|<span data-ttu-id="598ca-406">String</span><span class="sxs-lookup"><span data-stu-id="598ca-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="598ca-407">过程</span><span class="sxs-lookup"><span data-stu-id="598ca-407">Procedures</span></span>  
  
|<span data-ttu-id="598ca-408">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-408">ColumnName</span></span>|<span data-ttu-id="598ca-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="598ca-411">String</span><span class="sxs-lookup"><span data-stu-id="598ca-411">String</span></span>|  
|<span data-ttu-id="598ca-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="598ca-413">String</span><span class="sxs-lookup"><span data-stu-id="598ca-413">String</span></span>|  
|<span data-ttu-id="598ca-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="598ca-415">String</span><span class="sxs-lookup"><span data-stu-id="598ca-415">String</span></span>|  
|<span data-ttu-id="598ca-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="598ca-417">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-417">Int16</span></span>|  
|<span data-ttu-id="598ca-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="598ca-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="598ca-419">String</span><span class="sxs-lookup"><span data-stu-id="598ca-419">String</span></span>|  
|<span data-ttu-id="598ca-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-420">DESCRIPTION</span></span>|<span data-ttu-id="598ca-421">String</span><span class="sxs-lookup"><span data-stu-id="598ca-421">String</span></span>|  
|<span data-ttu-id="598ca-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="598ca-422">DATE_CREATED</span></span>|<span data-ttu-id="598ca-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-423">DateTime</span></span>|  
|<span data-ttu-id="598ca-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="598ca-424">DATE_MODIFIED</span></span>|<span data-ttu-id="598ca-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="598ca-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="598ca-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="598ca-427">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-427">ColumnName</span></span>|<span data-ttu-id="598ca-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="598ca-430">String</span><span class="sxs-lookup"><span data-stu-id="598ca-430">String</span></span>|  
|<span data-ttu-id="598ca-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="598ca-432">String</span><span class="sxs-lookup"><span data-stu-id="598ca-432">String</span></span>|  
|<span data-ttu-id="598ca-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="598ca-434">String</span><span class="sxs-lookup"><span data-stu-id="598ca-434">String</span></span>|  
|<span data-ttu-id="598ca-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-435">COLUMN_NAME</span></span>|<span data-ttu-id="598ca-436">String</span><span class="sxs-lookup"><span data-stu-id="598ca-436">String</span></span>|  
|<span data-ttu-id="598ca-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-437">COLUMN_GUID</span></span>|<span data-ttu-id="598ca-438">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-438">Guid</span></span>|  
|<span data-ttu-id="598ca-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-439">COLUMN_PROPID</span></span>|<span data-ttu-id="598ca-440">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-440">Int64</span></span>|  
|<span data-ttu-id="598ca-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="598ca-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="598ca-442">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-442">Int64</span></span>|  
|<span data-ttu-id="598ca-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="598ca-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="598ca-444">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-444">Int64</span></span>|  
|<span data-ttu-id="598ca-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="598ca-445">IS_NULLABLE</span></span>|<span data-ttu-id="598ca-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-446">Boolean</span></span>|  
|<span data-ttu-id="598ca-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-447">DATA_TYPE</span></span>|<span data-ttu-id="598ca-448">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-448">Int32</span></span>|  
|<span data-ttu-id="598ca-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-449">TYPE_GUID</span></span>|<span data-ttu-id="598ca-450">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-450">Guid</span></span>|  
|<span data-ttu-id="598ca-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="598ca-452">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-452">Int64</span></span>|  
|<span data-ttu-id="598ca-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="598ca-454">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-454">Int64</span></span>|  
|<span data-ttu-id="598ca-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="598ca-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="598ca-456">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-456">Int32</span></span>|  
|<span data-ttu-id="598ca-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="598ca-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="598ca-458">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-458">Int16</span></span>|  
|<span data-ttu-id="598ca-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-459">DESCRIPTION</span></span>|<span data-ttu-id="598ca-460">String</span><span class="sxs-lookup"><span data-stu-id="598ca-460">String</span></span>|  
|<span data-ttu-id="598ca-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="598ca-461">OVERLOAD</span></span>|<span data-ttu-id="598ca-462">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="598ca-463">视图</span><span class="sxs-lookup"><span data-stu-id="598ca-463">Views</span></span>  
  
|<span data-ttu-id="598ca-464">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-464">ColumnName</span></span>|<span data-ttu-id="598ca-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-466">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-467">String</span><span class="sxs-lookup"><span data-stu-id="598ca-467">String</span></span>|  
|<span data-ttu-id="598ca-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-469">String</span><span class="sxs-lookup"><span data-stu-id="598ca-469">String</span></span>|  
|<span data-ttu-id="598ca-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-470">TABLE_NAME</span></span>|<span data-ttu-id="598ca-471">String</span><span class="sxs-lookup"><span data-stu-id="598ca-471">String</span></span>|  
|<span data-ttu-id="598ca-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="598ca-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="598ca-473">String</span><span class="sxs-lookup"><span data-stu-id="598ca-473">String</span></span>|  
|<span data-ttu-id="598ca-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-474">CHECK_OPTION</span></span>|<span data-ttu-id="598ca-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-475">Boolean</span></span>|  
|<span data-ttu-id="598ca-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="598ca-476">IS_UPDATABLE</span></span>|<span data-ttu-id="598ca-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-477">Boolean</span></span>|  
|<span data-ttu-id="598ca-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-478">DESCRIPTION</span></span>|<span data-ttu-id="598ca-479">String</span><span class="sxs-lookup"><span data-stu-id="598ca-479">String</span></span>|  
|<span data-ttu-id="598ca-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="598ca-480">DATE_CREATED</span></span>|<span data-ttu-id="598ca-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-481">DateTime</span></span>|  
|<span data-ttu-id="598ca-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="598ca-482">DATE_MODIFIED</span></span>|<span data-ttu-id="598ca-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="598ca-484">索引</span><span class="sxs-lookup"><span data-stu-id="598ca-484">Indexes</span></span>  
  
|<span data-ttu-id="598ca-485">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-485">ColumnName</span></span>|<span data-ttu-id="598ca-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-487">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-488">String</span><span class="sxs-lookup"><span data-stu-id="598ca-488">String</span></span>|  
|<span data-ttu-id="598ca-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-490">String</span><span class="sxs-lookup"><span data-stu-id="598ca-490">String</span></span>|  
|<span data-ttu-id="598ca-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-491">TABLE_NAME</span></span>|<span data-ttu-id="598ca-492">String</span><span class="sxs-lookup"><span data-stu-id="598ca-492">String</span></span>|  
|<span data-ttu-id="598ca-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-493">INDEX_CATALOG</span></span>|<span data-ttu-id="598ca-494">String</span><span class="sxs-lookup"><span data-stu-id="598ca-494">String</span></span>|  
|<span data-ttu-id="598ca-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="598ca-496">String</span><span class="sxs-lookup"><span data-stu-id="598ca-496">String</span></span>|  
|<span data-ttu-id="598ca-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-497">INDEX_NAME</span></span>|<span data-ttu-id="598ca-498">String</span><span class="sxs-lookup"><span data-stu-id="598ca-498">String</span></span>|  
|<span data-ttu-id="598ca-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="598ca-499">PRIMARY_KEY</span></span>|<span data-ttu-id="598ca-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-500">Boolean</span></span>|  
|<span data-ttu-id="598ca-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="598ca-501">UNIQUE</span></span>|<span data-ttu-id="598ca-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-502">Boolean</span></span>|  
|<span data-ttu-id="598ca-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="598ca-503">CLUSTERED</span></span>|<span data-ttu-id="598ca-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-504">Boolean</span></span>|  
|<span data-ttu-id="598ca-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-505">TYPE</span></span>|<span data-ttu-id="598ca-506">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-506">Int32</span></span>|  
|<span data-ttu-id="598ca-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="598ca-507">FILL_FACTOR</span></span>|<span data-ttu-id="598ca-508">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-508">Int32</span></span>|  
|<span data-ttu-id="598ca-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="598ca-509">INITIAL_SIZE</span></span>|<span data-ttu-id="598ca-510">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-510">Int32</span></span>|  
|<span data-ttu-id="598ca-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="598ca-511">NULLS</span></span>|<span data-ttu-id="598ca-512">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-512">Int32</span></span>|  
|<span data-ttu-id="598ca-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="598ca-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="598ca-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-514">Boolean</span></span>|  
|<span data-ttu-id="598ca-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="598ca-515">AUTO_UPDATE</span></span>|<span data-ttu-id="598ca-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-516">Boolean</span></span>|  
|<span data-ttu-id="598ca-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="598ca-517">NULL_COLLATION</span></span>|<span data-ttu-id="598ca-518">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-518">Int32</span></span>|  
|<span data-ttu-id="598ca-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="598ca-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="598ca-520">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-520">Int64</span></span>|  
|<span data-ttu-id="598ca-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-521">COLUMN_NAME</span></span>|<span data-ttu-id="598ca-522">String</span><span class="sxs-lookup"><span data-stu-id="598ca-522">String</span></span>|  
|<span data-ttu-id="598ca-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-523">COLUMN_GUID</span></span>|<span data-ttu-id="598ca-524">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-524">Guid</span></span>|  
|<span data-ttu-id="598ca-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-525">COLUMN_PROPID</span></span>|<span data-ttu-id="598ca-526">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-526">Int64</span></span>|  
|<span data-ttu-id="598ca-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="598ca-527">COLLATION</span></span>|<span data-ttu-id="598ca-528">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-528">Int16</span></span>|  
|<span data-ttu-id="598ca-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="598ca-529">CARDINALITY</span></span>|<span data-ttu-id="598ca-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="598ca-530">Decimal</span></span>|  
|<span data-ttu-id="598ca-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="598ca-531">PAGES</span></span>|<span data-ttu-id="598ca-532">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-532">Int32</span></span>|  
|<span data-ttu-id="598ca-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="598ca-533">FILTER_CONDITION</span></span>|<span data-ttu-id="598ca-534">String</span><span class="sxs-lookup"><span data-stu-id="598ca-534">String</span></span>|  
|<span data-ttu-id="598ca-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="598ca-535">INTEGRATED</span></span>|<span data-ttu-id="598ca-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="598ca-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="598ca-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="598ca-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="598ca-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="598ca-539">表</span><span class="sxs-lookup"><span data-stu-id="598ca-539">Tables</span></span>  
  
-   <span data-ttu-id="598ca-540">Columns</span><span class="sxs-lookup"><span data-stu-id="598ca-540">Columns</span></span>  
  
-   <span data-ttu-id="598ca-541">过程</span><span class="sxs-lookup"><span data-stu-id="598ca-541">Procedures</span></span>  
  
-   <span data-ttu-id="598ca-542">视图</span><span class="sxs-lookup"><span data-stu-id="598ca-542">Views</span></span>  
  
-   <span data-ttu-id="598ca-543">索引</span><span class="sxs-lookup"><span data-stu-id="598ca-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="598ca-544">表</span><span class="sxs-lookup"><span data-stu-id="598ca-544">Tables</span></span>  
  
|<span data-ttu-id="598ca-545">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-545">ColumnName</span></span>|<span data-ttu-id="598ca-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-547">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-548">String</span><span class="sxs-lookup"><span data-stu-id="598ca-548">String</span></span>|  
|<span data-ttu-id="598ca-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-550">String</span><span class="sxs-lookup"><span data-stu-id="598ca-550">String</span></span>|  
|<span data-ttu-id="598ca-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-551">TABLE_NAME</span></span>|<span data-ttu-id="598ca-552">String</span><span class="sxs-lookup"><span data-stu-id="598ca-552">String</span></span>|  
|<span data-ttu-id="598ca-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-553">TABLE_TYPE</span></span>|<span data-ttu-id="598ca-554">String</span><span class="sxs-lookup"><span data-stu-id="598ca-554">String</span></span>|  
|<span data-ttu-id="598ca-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-555">TABLE_GUID</span></span>|<span data-ttu-id="598ca-556">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-556">Guid</span></span>|  
|<span data-ttu-id="598ca-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-557">DESCRIPTION</span></span>|<span data-ttu-id="598ca-558">String</span><span class="sxs-lookup"><span data-stu-id="598ca-558">String</span></span>|  
|<span data-ttu-id="598ca-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-559">TABLE_PROPID</span></span>|<span data-ttu-id="598ca-560">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-560">Int64</span></span>|  
|<span data-ttu-id="598ca-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="598ca-561">DATE_CREATED</span></span>|<span data-ttu-id="598ca-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-562">DateTime</span></span>|  
|<span data-ttu-id="598ca-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="598ca-563">DATE_MODIFIED</span></span>|<span data-ttu-id="598ca-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="598ca-565">Columns</span><span class="sxs-lookup"><span data-stu-id="598ca-565">Columns</span></span>  
  
|<span data-ttu-id="598ca-566">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-566">ColumnName</span></span>|<span data-ttu-id="598ca-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-568">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-569">String</span><span class="sxs-lookup"><span data-stu-id="598ca-569">String</span></span>|  
|<span data-ttu-id="598ca-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-571">String</span><span class="sxs-lookup"><span data-stu-id="598ca-571">String</span></span>|  
|<span data-ttu-id="598ca-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-572">TABLE_NAME</span></span>|<span data-ttu-id="598ca-573">String</span><span class="sxs-lookup"><span data-stu-id="598ca-573">String</span></span>|  
|<span data-ttu-id="598ca-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-574">COLUMN_NAME</span></span>|<span data-ttu-id="598ca-575">String</span><span class="sxs-lookup"><span data-stu-id="598ca-575">String</span></span>|  
|<span data-ttu-id="598ca-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-576">COLUMN_GUID</span></span>|<span data-ttu-id="598ca-577">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-577">Guid</span></span>|  
|<span data-ttu-id="598ca-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-578">COLUMN_PROPID</span></span>|<span data-ttu-id="598ca-579">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-579">Int64</span></span>|  
|<span data-ttu-id="598ca-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="598ca-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="598ca-581">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-581">Int64</span></span>|  
|<span data-ttu-id="598ca-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="598ca-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="598ca-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-583">Boolean</span></span>|  
|<span data-ttu-id="598ca-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="598ca-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="598ca-585">String</span><span class="sxs-lookup"><span data-stu-id="598ca-585">String</span></span>|  
|<span data-ttu-id="598ca-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="598ca-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="598ca-587">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-587">Int64</span></span>|  
|<span data-ttu-id="598ca-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="598ca-588">IS_NULLABLE</span></span>|<span data-ttu-id="598ca-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-589">Boolean</span></span>|  
|<span data-ttu-id="598ca-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-590">DATA_TYPE</span></span>|<span data-ttu-id="598ca-591">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-591">Int32</span></span>|  
|<span data-ttu-id="598ca-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-592">TYPE_GUID</span></span>|<span data-ttu-id="598ca-593">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-593">Guid</span></span>|  
|<span data-ttu-id="598ca-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="598ca-595">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-595">Int64</span></span>|  
|<span data-ttu-id="598ca-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="598ca-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="598ca-597">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-597">Int64</span></span>|  
|<span data-ttu-id="598ca-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="598ca-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="598ca-599">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-599">Int32</span></span>|  
|<span data-ttu-id="598ca-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="598ca-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="598ca-601">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-601">Int16</span></span>|  
|<span data-ttu-id="598ca-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="598ca-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="598ca-603">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-603">Int64</span></span>|  
|<span data-ttu-id="598ca-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="598ca-605">String</span><span class="sxs-lookup"><span data-stu-id="598ca-605">String</span></span>|  
|<span data-ttu-id="598ca-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="598ca-607">String</span><span class="sxs-lookup"><span data-stu-id="598ca-607">String</span></span>|  
|<span data-ttu-id="598ca-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="598ca-609">String</span><span class="sxs-lookup"><span data-stu-id="598ca-609">String</span></span>|  
|<span data-ttu-id="598ca-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="598ca-611">String</span><span class="sxs-lookup"><span data-stu-id="598ca-611">String</span></span>|  
|<span data-ttu-id="598ca-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="598ca-613">String</span><span class="sxs-lookup"><span data-stu-id="598ca-613">String</span></span>|  
|<span data-ttu-id="598ca-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-614">COLLATION_NAME</span></span>|<span data-ttu-id="598ca-615">String</span><span class="sxs-lookup"><span data-stu-id="598ca-615">String</span></span>|  
|<span data-ttu-id="598ca-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="598ca-617">String</span><span class="sxs-lookup"><span data-stu-id="598ca-617">String</span></span>|  
|<span data-ttu-id="598ca-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="598ca-619">String</span><span class="sxs-lookup"><span data-stu-id="598ca-619">String</span></span>|  
|<span data-ttu-id="598ca-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-620">DOMAIN_NAME</span></span>|<span data-ttu-id="598ca-621">String</span><span class="sxs-lookup"><span data-stu-id="598ca-621">String</span></span>|  
|<span data-ttu-id="598ca-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-622">DESCRIPTION</span></span>|<span data-ttu-id="598ca-623">String</span><span class="sxs-lookup"><span data-stu-id="598ca-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="598ca-624">过程</span><span class="sxs-lookup"><span data-stu-id="598ca-624">Procedures</span></span>  
  
|<span data-ttu-id="598ca-625">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-625">ColumnName</span></span>|<span data-ttu-id="598ca-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="598ca-628">String</span><span class="sxs-lookup"><span data-stu-id="598ca-628">String</span></span>|  
|<span data-ttu-id="598ca-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="598ca-630">String</span><span class="sxs-lookup"><span data-stu-id="598ca-630">String</span></span>|  
|<span data-ttu-id="598ca-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="598ca-632">String</span><span class="sxs-lookup"><span data-stu-id="598ca-632">String</span></span>|  
|<span data-ttu-id="598ca-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="598ca-634">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-634">Int16</span></span>|  
|<span data-ttu-id="598ca-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="598ca-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="598ca-636">String</span><span class="sxs-lookup"><span data-stu-id="598ca-636">String</span></span>|  
|<span data-ttu-id="598ca-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-637">DESCRIPTION</span></span>|<span data-ttu-id="598ca-638">String</span><span class="sxs-lookup"><span data-stu-id="598ca-638">String</span></span>|  
|<span data-ttu-id="598ca-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="598ca-639">DATE_CREATED</span></span>|<span data-ttu-id="598ca-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-640">DateTime</span></span>|  
|<span data-ttu-id="598ca-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="598ca-641">DATE_MODIFIED</span></span>|<span data-ttu-id="598ca-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="598ca-643">视图</span><span class="sxs-lookup"><span data-stu-id="598ca-643">Views</span></span>  
  
|<span data-ttu-id="598ca-644">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-644">ColumnName</span></span>|<span data-ttu-id="598ca-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-646">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-647">String</span><span class="sxs-lookup"><span data-stu-id="598ca-647">String</span></span>|  
|<span data-ttu-id="598ca-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-649">String</span><span class="sxs-lookup"><span data-stu-id="598ca-649">String</span></span>|  
|<span data-ttu-id="598ca-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-650">TABLE_NAME</span></span>|<span data-ttu-id="598ca-651">String</span><span class="sxs-lookup"><span data-stu-id="598ca-651">String</span></span>|  
|<span data-ttu-id="598ca-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="598ca-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="598ca-653">String</span><span class="sxs-lookup"><span data-stu-id="598ca-653">String</span></span>|  
|<span data-ttu-id="598ca-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-654">CHECK_OPTION</span></span>|<span data-ttu-id="598ca-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-655">Boolean</span></span>|  
|<span data-ttu-id="598ca-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="598ca-656">IS_UPDATABLE</span></span>|<span data-ttu-id="598ca-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-657">Boolean</span></span>|  
|<span data-ttu-id="598ca-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598ca-658">DESCRIPTION</span></span>|<span data-ttu-id="598ca-659">String</span><span class="sxs-lookup"><span data-stu-id="598ca-659">String</span></span>|  
|<span data-ttu-id="598ca-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="598ca-660">DATE_CREATED</span></span>|<span data-ttu-id="598ca-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-661">DateTime</span></span>|  
|<span data-ttu-id="598ca-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="598ca-662">DATE_MODIFIED</span></span>|<span data-ttu-id="598ca-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="598ca-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="598ca-664">索引</span><span class="sxs-lookup"><span data-stu-id="598ca-664">Indexes</span></span>  
  
|<span data-ttu-id="598ca-665">列名</span><span class="sxs-lookup"><span data-stu-id="598ca-665">ColumnName</span></span>|<span data-ttu-id="598ca-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="598ca-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="598ca-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-667">TABLE_CATALOG</span></span>|<span data-ttu-id="598ca-668">String</span><span class="sxs-lookup"><span data-stu-id="598ca-668">String</span></span>|  
|<span data-ttu-id="598ca-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="598ca-670">String</span><span class="sxs-lookup"><span data-stu-id="598ca-670">String</span></span>|  
|<span data-ttu-id="598ca-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-671">TABLE_NAME</span></span>|<span data-ttu-id="598ca-672">String</span><span class="sxs-lookup"><span data-stu-id="598ca-672">String</span></span>|  
|<span data-ttu-id="598ca-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="598ca-673">INDEX_CATALOG</span></span>|<span data-ttu-id="598ca-674">String</span><span class="sxs-lookup"><span data-stu-id="598ca-674">String</span></span>|  
|<span data-ttu-id="598ca-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="598ca-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="598ca-676">String</span><span class="sxs-lookup"><span data-stu-id="598ca-676">String</span></span>|  
|<span data-ttu-id="598ca-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-677">INDEX_NAME</span></span>|<span data-ttu-id="598ca-678">String</span><span class="sxs-lookup"><span data-stu-id="598ca-678">String</span></span>|  
|<span data-ttu-id="598ca-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="598ca-679">PRIMARY_KEY</span></span>|<span data-ttu-id="598ca-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-680">Boolean</span></span>|  
|<span data-ttu-id="598ca-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="598ca-681">UNIQUE</span></span>|<span data-ttu-id="598ca-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-682">Boolean</span></span>|  
|<span data-ttu-id="598ca-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="598ca-683">CLUSTERED</span></span>|<span data-ttu-id="598ca-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-684">Boolean</span></span>|  
|<span data-ttu-id="598ca-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="598ca-685">TYPE</span></span>|<span data-ttu-id="598ca-686">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-686">Int32</span></span>|  
|<span data-ttu-id="598ca-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="598ca-687">FILL_FACTOR</span></span>|<span data-ttu-id="598ca-688">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-688">Int32</span></span>|  
|<span data-ttu-id="598ca-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="598ca-689">INITIAL_SIZE</span></span>|<span data-ttu-id="598ca-690">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-690">Int32</span></span>|  
|<span data-ttu-id="598ca-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="598ca-691">NULLS</span></span>|<span data-ttu-id="598ca-692">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-692">Int32</span></span>|  
|<span data-ttu-id="598ca-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="598ca-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="598ca-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-694">Boolean</span></span>|  
|<span data-ttu-id="598ca-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="598ca-695">AUTO_UPDATE</span></span>|<span data-ttu-id="598ca-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-696">Boolean</span></span>|  
|<span data-ttu-id="598ca-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="598ca-697">NULL_COLLATION</span></span>|<span data-ttu-id="598ca-698">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-698">Int32</span></span>|  
|<span data-ttu-id="598ca-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="598ca-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="598ca-700">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-700">Int64</span></span>|  
|<span data-ttu-id="598ca-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="598ca-701">COLUMN_NAME</span></span>|<span data-ttu-id="598ca-702">String</span><span class="sxs-lookup"><span data-stu-id="598ca-702">String</span></span>|  
|<span data-ttu-id="598ca-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="598ca-703">COLUMN_GUID</span></span>|<span data-ttu-id="598ca-704">Guid</span><span class="sxs-lookup"><span data-stu-id="598ca-704">Guid</span></span>|  
|<span data-ttu-id="598ca-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="598ca-705">COLUMN_PROPID</span></span>|<span data-ttu-id="598ca-706">Int64</span><span class="sxs-lookup"><span data-stu-id="598ca-706">Int64</span></span>|  
|<span data-ttu-id="598ca-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="598ca-707">COLLATION</span></span>|<span data-ttu-id="598ca-708">Int16</span><span class="sxs-lookup"><span data-stu-id="598ca-708">Int16</span></span>|  
|<span data-ttu-id="598ca-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="598ca-709">CARDINALITY</span></span>|<span data-ttu-id="598ca-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="598ca-710">Decimal</span></span>|  
|<span data-ttu-id="598ca-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="598ca-711">PAGES</span></span>|<span data-ttu-id="598ca-712">Int32</span><span class="sxs-lookup"><span data-stu-id="598ca-712">Int32</span></span>|  
|<span data-ttu-id="598ca-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="598ca-713">FILTER_CONDITION</span></span>|<span data-ttu-id="598ca-714">String</span><span class="sxs-lookup"><span data-stu-id="598ca-714">String</span></span>|  
|<span data-ttu-id="598ca-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="598ca-715">INTEGRATED</span></span>|<span data-ttu-id="598ca-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="598ca-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="598ca-717">另请参阅</span><span class="sxs-lookup"><span data-stu-id="598ca-717">See Also</span></span>  
 [<span data-ttu-id="598ca-718">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="598ca-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
