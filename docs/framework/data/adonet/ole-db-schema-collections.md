---
title: OLE DB 架构集合
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="df8b2-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="df8b2-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="df8b2-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="df8b2-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="df8b2-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="df8b2-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="df8b2-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="df8b2-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="df8b2-106">表</span><span class="sxs-lookup"><span data-stu-id="df8b2-106">Tables</span></span>  
  
-   <span data-ttu-id="df8b2-107">Columns</span><span class="sxs-lookup"><span data-stu-id="df8b2-107">Columns</span></span>  
  
-   <span data-ttu-id="df8b2-108">过程</span><span class="sxs-lookup"><span data-stu-id="df8b2-108">Procedures</span></span>  
  
-   <span data-ttu-id="df8b2-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="df8b2-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="df8b2-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="df8b2-110">Catalog</span></span>  
  
-   <span data-ttu-id="df8b2-111">索引</span><span class="sxs-lookup"><span data-stu-id="df8b2-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="df8b2-112">表</span><span class="sxs-lookup"><span data-stu-id="df8b2-112">Tables</span></span>  
  
|<span data-ttu-id="df8b2-113">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-113">ColumnName</span></span>|<span data-ttu-id="df8b2-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-115">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-116">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-116">String</span></span>|  
|<span data-ttu-id="df8b2-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-118">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-118">String</span></span>|  
|<span data-ttu-id="df8b2-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-119">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-120">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-120">String</span></span>|  
|<span data-ttu-id="df8b2-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-121">TABLE_TYPE</span></span>|<span data-ttu-id="df8b2-122">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-122">String</span></span>|  
|<span data-ttu-id="df8b2-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-123">TABLE_GUID</span></span>|<span data-ttu-id="df8b2-124">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-124">Guid</span></span>|  
|<span data-ttu-id="df8b2-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-125">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-126">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-126">String</span></span>|  
|<span data-ttu-id="df8b2-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-127">TABLE_PROPID</span></span>|<span data-ttu-id="df8b2-128">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-128">Int64</span></span>|  
|<span data-ttu-id="df8b2-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-129">DATE_CREATED</span></span>|<span data-ttu-id="df8b2-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-130">DateTime</span></span>|  
|<span data-ttu-id="df8b2-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df8b2-131">DATE_MODIFIED</span></span>|<span data-ttu-id="df8b2-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="df8b2-133">Columns</span><span class="sxs-lookup"><span data-stu-id="df8b2-133">Columns</span></span>  
  
|<span data-ttu-id="df8b2-134">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-134">ColumnName</span></span>|<span data-ttu-id="df8b2-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-136">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-137">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-137">String</span></span>|  
|<span data-ttu-id="df8b2-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-139">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-139">String</span></span>|  
|<span data-ttu-id="df8b2-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-140">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-141">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-141">String</span></span>|  
|<span data-ttu-id="df8b2-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-142">COLUMN_NAME</span></span>|<span data-ttu-id="df8b2-143">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-143">String</span></span>|  
|<span data-ttu-id="df8b2-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-144">COLUMN_GUID</span></span>|<span data-ttu-id="df8b2-145">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-145">Guid</span></span>|  
|<span data-ttu-id="df8b2-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-146">COLUMN_PROPID</span></span>|<span data-ttu-id="df8b2-147">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-147">Int64</span></span>|  
|<span data-ttu-id="df8b2-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="df8b2-149">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-149">Int64</span></span>|  
|<span data-ttu-id="df8b2-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="df8b2-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="df8b2-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-151">Boolean</span></span>|  
|<span data-ttu-id="df8b2-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="df8b2-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="df8b2-153">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-153">String</span></span>|  
|<span data-ttu-id="df8b2-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="df8b2-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="df8b2-155">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-155">Int64</span></span>|  
|<span data-ttu-id="df8b2-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df8b2-156">IS_NULLABLE</span></span>|<span data-ttu-id="df8b2-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-157">Boolean</span></span>|  
|<span data-ttu-id="df8b2-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-158">DATA_TYPE</span></span>|<span data-ttu-id="df8b2-159">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-159">Int32</span></span>|  
|<span data-ttu-id="df8b2-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-160">TYPE_GUID</span></span>|<span data-ttu-id="df8b2-161">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-161">Guid</span></span>|  
|<span data-ttu-id="df8b2-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df8b2-163">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-163">Int64</span></span>|  
|<span data-ttu-id="df8b2-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df8b2-165">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-165">Int64</span></span>|  
|<span data-ttu-id="df8b2-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df8b2-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df8b2-167">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-167">Int32</span></span>|  
|<span data-ttu-id="df8b2-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df8b2-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="df8b2-169">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-169">Int16</span></span>|  
|<span data-ttu-id="df8b2-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df8b2-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="df8b2-171">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-171">Int64</span></span>|  
|<span data-ttu-id="df8b2-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="df8b2-173">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-173">String</span></span>|  
|<span data-ttu-id="df8b2-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="df8b2-175">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-175">String</span></span>|  
|<span data-ttu-id="df8b2-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="df8b2-177">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-177">String</span></span>|  
|<span data-ttu-id="df8b2-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="df8b2-179">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-179">String</span></span>|  
|<span data-ttu-id="df8b2-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="df8b2-181">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-181">String</span></span>|  
|<span data-ttu-id="df8b2-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-182">COLLATION_NAME</span></span>|<span data-ttu-id="df8b2-183">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-183">String</span></span>|  
|<span data-ttu-id="df8b2-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="df8b2-185">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-185">String</span></span>|  
|<span data-ttu-id="df8b2-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="df8b2-187">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-187">String</span></span>|  
|<span data-ttu-id="df8b2-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-188">DOMAIN_NAME</span></span>|<span data-ttu-id="df8b2-189">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-189">String</span></span>|  
|<span data-ttu-id="df8b2-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-190">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-191">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-191">String</span></span>|  
|<span data-ttu-id="df8b2-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="df8b2-192">COLUMN_LCID</span></span>|<span data-ttu-id="df8b2-193">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-193">Int32</span></span>|  
|<span data-ttu-id="df8b2-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="df8b2-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="df8b2-195">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-195">Int32</span></span>|  
|<span data-ttu-id="df8b2-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="df8b2-196">COLUMN_SORTID</span></span>|<span data-ttu-id="df8b2-197">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-197">Int32</span></span>|  
|<span data-ttu-id="df8b2-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="df8b2-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="df8b2-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="df8b2-199">Byte[]</span></span>|  
|<span data-ttu-id="df8b2-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="df8b2-200">IS_COMPUTED</span></span>|<span data-ttu-id="df8b2-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="df8b2-202">过程</span><span class="sxs-lookup"><span data-stu-id="df8b2-202">Procedures</span></span>  
  
|<span data-ttu-id="df8b2-203">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-203">ColumnName</span></span>|<span data-ttu-id="df8b2-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df8b2-206">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-206">String</span></span>|  
|<span data-ttu-id="df8b2-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df8b2-208">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-208">String</span></span>|  
|<span data-ttu-id="df8b2-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="df8b2-210">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-210">String</span></span>|  
|<span data-ttu-id="df8b2-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="df8b2-212">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-212">Int16</span></span>|  
|<span data-ttu-id="df8b2-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="df8b2-214">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-214">String</span></span>|  
|<span data-ttu-id="df8b2-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-215">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-216">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-216">String</span></span>|  
|<span data-ttu-id="df8b2-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-217">DATE_CREATED</span></span>|<span data-ttu-id="df8b2-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-218">DateTime</span></span>|  
|<span data-ttu-id="df8b2-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df8b2-219">DATE_MODIFIED</span></span>|<span data-ttu-id="df8b2-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="df8b2-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="df8b2-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="df8b2-222">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-222">ColumnName</span></span>|<span data-ttu-id="df8b2-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df8b2-225">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-225">String</span></span>|  
|<span data-ttu-id="df8b2-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df8b2-227">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-227">String</span></span>|  
|<span data-ttu-id="df8b2-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="df8b2-229">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-229">String</span></span>|  
|<span data-ttu-id="df8b2-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-230">PARAMETER_NAME</span></span>|<span data-ttu-id="df8b2-231">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-231">String</span></span>|  
|<span data-ttu-id="df8b2-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="df8b2-233">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-233">Int32</span></span>|  
|<span data-ttu-id="df8b2-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="df8b2-235">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-235">Int32</span></span>|  
|<span data-ttu-id="df8b2-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="df8b2-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="df8b2-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-237">Boolean</span></span>|  
|<span data-ttu-id="df8b2-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="df8b2-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="df8b2-239">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-239">String</span></span>|  
|<span data-ttu-id="df8b2-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df8b2-240">IS_NULLABLE</span></span>|<span data-ttu-id="df8b2-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-241">Boolean</span></span>|  
|<span data-ttu-id="df8b2-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-242">DATA_TYPE</span></span>|<span data-ttu-id="df8b2-243">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-243">Int32</span></span>|  
|<span data-ttu-id="df8b2-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df8b2-245">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-245">Int64</span></span>|  
|<span data-ttu-id="df8b2-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df8b2-247">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-247">Int64</span></span>|  
|<span data-ttu-id="df8b2-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df8b2-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df8b2-249">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-249">Int32</span></span>|  
|<span data-ttu-id="df8b2-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df8b2-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="df8b2-251">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-251">Int16</span></span>|  
|<span data-ttu-id="df8b2-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-252">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-253">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-253">String</span></span>|  
|<span data-ttu-id="df8b2-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-254">TYPE_NAME</span></span>|<span data-ttu-id="df8b2-255">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-255">String</span></span>|  
|<span data-ttu-id="df8b2-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="df8b2-257">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="df8b2-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="df8b2-258">Catalog</span></span>  
  
|<span data-ttu-id="df8b2-259">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-259">ColumnName</span></span>|<span data-ttu-id="df8b2-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-261">CATALOG_NAME</span></span>|<span data-ttu-id="df8b2-262">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-262">String</span></span>|  
|<span data-ttu-id="df8b2-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-263">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-264">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="df8b2-265">索引</span><span class="sxs-lookup"><span data-stu-id="df8b2-265">Indexes</span></span>  
  
|<span data-ttu-id="df8b2-266">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-266">ColumnName</span></span>|<span data-ttu-id="df8b2-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-268">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-269">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-269">String</span></span>|  
|<span data-ttu-id="df8b2-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-271">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-271">String</span></span>|  
|<span data-ttu-id="df8b2-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-272">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-273">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-273">String</span></span>|  
|<span data-ttu-id="df8b2-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-274">INDEX_CATALOG</span></span>|<span data-ttu-id="df8b2-275">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-275">String</span></span>|  
|<span data-ttu-id="df8b2-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="df8b2-277">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-277">String</span></span>|  
|<span data-ttu-id="df8b2-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-278">INDEX_NAME</span></span>|<span data-ttu-id="df8b2-279">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-279">String</span></span>|  
|<span data-ttu-id="df8b2-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="df8b2-280">PRIMARY_KEY</span></span>|<span data-ttu-id="df8b2-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-281">Boolean</span></span>|  
|<span data-ttu-id="df8b2-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="df8b2-282">UNIQUE</span></span>|<span data-ttu-id="df8b2-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-283">Boolean</span></span>|  
|<span data-ttu-id="df8b2-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="df8b2-284">CLUSTERED</span></span>|<span data-ttu-id="df8b2-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-285">Boolean</span></span>|  
|<span data-ttu-id="df8b2-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-286">TYPE</span></span>|<span data-ttu-id="df8b2-287">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-287">Int32</span></span>|  
|<span data-ttu-id="df8b2-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="df8b2-288">FILL_FACTOR</span></span>|<span data-ttu-id="df8b2-289">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-289">Int32</span></span>|  
|<span data-ttu-id="df8b2-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="df8b2-290">INITIAL_SIZE</span></span>|<span data-ttu-id="df8b2-291">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-291">Int32</span></span>|  
|<span data-ttu-id="df8b2-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="df8b2-292">NULLS</span></span>|<span data-ttu-id="df8b2-293">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-293">Int32</span></span>|  
|<span data-ttu-id="df8b2-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="df8b2-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="df8b2-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-295">Boolean</span></span>|  
|<span data-ttu-id="df8b2-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="df8b2-296">AUTO_UPDATE</span></span>|<span data-ttu-id="df8b2-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-297">Boolean</span></span>|  
|<span data-ttu-id="df8b2-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="df8b2-298">NULL_COLLATION</span></span>|<span data-ttu-id="df8b2-299">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-299">Int32</span></span>|  
|<span data-ttu-id="df8b2-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="df8b2-301">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-301">Int64</span></span>|  
|<span data-ttu-id="df8b2-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-302">COLUMN_NAME</span></span>|<span data-ttu-id="df8b2-303">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-303">String</span></span>|  
|<span data-ttu-id="df8b2-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-304">COLUMN_GUID</span></span>|<span data-ttu-id="df8b2-305">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-305">Guid</span></span>|  
|<span data-ttu-id="df8b2-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-306">COLUMN_PROPID</span></span>|<span data-ttu-id="df8b2-307">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-307">Int64</span></span>|  
|<span data-ttu-id="df8b2-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="df8b2-308">COLLATION</span></span>|<span data-ttu-id="df8b2-309">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-309">Int16</span></span>|  
|<span data-ttu-id="df8b2-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="df8b2-310">CARDINALITY</span></span>|<span data-ttu-id="df8b2-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="df8b2-311">Decimal</span></span>|  
|<span data-ttu-id="df8b2-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="df8b2-312">PAGES</span></span>|<span data-ttu-id="df8b2-313">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-313">Int32</span></span>|  
|<span data-ttu-id="df8b2-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-314">FILTER_CONDITION</span></span>|<span data-ttu-id="df8b2-315">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-315">String</span></span>|  
|<span data-ttu-id="df8b2-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-316">INTEGRATED</span></span>|<span data-ttu-id="df8b2-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="df8b2-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="df8b2-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="df8b2-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="df8b2-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="df8b2-320">表</span><span class="sxs-lookup"><span data-stu-id="df8b2-320">Tables</span></span>  
  
-   <span data-ttu-id="df8b2-321">Columns</span><span class="sxs-lookup"><span data-stu-id="df8b2-321">Columns</span></span>  
  
-   <span data-ttu-id="df8b2-322">过程</span><span class="sxs-lookup"><span data-stu-id="df8b2-322">Procedures</span></span>  
  
-   <span data-ttu-id="df8b2-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="df8b2-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="df8b2-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="df8b2-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="df8b2-325">视图</span><span class="sxs-lookup"><span data-stu-id="df8b2-325">Views</span></span>  
  
-   <span data-ttu-id="df8b2-326">索引</span><span class="sxs-lookup"><span data-stu-id="df8b2-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="df8b2-327">表</span><span class="sxs-lookup"><span data-stu-id="df8b2-327">Tables</span></span>  
  
|<span data-ttu-id="df8b2-328">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-328">ColumnName</span></span>|<span data-ttu-id="df8b2-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-330">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-331">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-331">String</span></span>|  
|<span data-ttu-id="df8b2-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-333">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-333">String</span></span>|  
|<span data-ttu-id="df8b2-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-334">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-335">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-335">String</span></span>|  
|<span data-ttu-id="df8b2-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-336">TABLE_TYPE</span></span>|<span data-ttu-id="df8b2-337">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-337">String</span></span>|  
|<span data-ttu-id="df8b2-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-338">TABLE_GUID</span></span>|<span data-ttu-id="df8b2-339">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-339">Guid</span></span>|  
|<span data-ttu-id="df8b2-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-340">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-341">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-341">String</span></span>|  
|<span data-ttu-id="df8b2-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-342">TABLE_PROPID</span></span>|<span data-ttu-id="df8b2-343">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-343">Int64</span></span>|  
|<span data-ttu-id="df8b2-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-344">DATE_CREATED</span></span>|<span data-ttu-id="df8b2-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-345">DateTime</span></span>|  
|<span data-ttu-id="df8b2-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df8b2-346">DATE_MODIFIED</span></span>|<span data-ttu-id="df8b2-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="df8b2-348">Columns</span><span class="sxs-lookup"><span data-stu-id="df8b2-348">Columns</span></span>  
  
|<span data-ttu-id="df8b2-349">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-349">ColumnName</span></span>|<span data-ttu-id="df8b2-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-351">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-352">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-352">String</span></span>|  
|<span data-ttu-id="df8b2-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-354">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-354">String</span></span>|  
|<span data-ttu-id="df8b2-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-355">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-356">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-356">String</span></span>|  
|<span data-ttu-id="df8b2-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-357">COLUMN_NAME</span></span>|<span data-ttu-id="df8b2-358">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-358">String</span></span>|  
|<span data-ttu-id="df8b2-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-359">COLUMN_GUID</span></span>|<span data-ttu-id="df8b2-360">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-360">Guid</span></span>|  
|<span data-ttu-id="df8b2-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-361">COLUMN_PROPID</span></span>|<span data-ttu-id="df8b2-362">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-362">Int64</span></span>|  
|<span data-ttu-id="df8b2-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="df8b2-364">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-364">Int64</span></span>|  
|<span data-ttu-id="df8b2-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="df8b2-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="df8b2-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-366">Boolean</span></span>|  
|<span data-ttu-id="df8b2-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="df8b2-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="df8b2-368">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-368">String</span></span>|  
|<span data-ttu-id="df8b2-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="df8b2-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="df8b2-370">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-370">Int64</span></span>|  
|<span data-ttu-id="df8b2-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df8b2-371">IS_NULLABLE</span></span>|<span data-ttu-id="df8b2-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-372">Boolean</span></span>|  
|<span data-ttu-id="df8b2-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-373">DATA_TYPE</span></span>|<span data-ttu-id="df8b2-374">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-374">Int32</span></span>|  
|<span data-ttu-id="df8b2-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-375">TYPE_GUID</span></span>|<span data-ttu-id="df8b2-376">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-376">Guid</span></span>|  
|<span data-ttu-id="df8b2-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df8b2-378">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-378">Int64</span></span>|  
|<span data-ttu-id="df8b2-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df8b2-380">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-380">Int64</span></span>|  
|<span data-ttu-id="df8b2-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df8b2-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df8b2-382">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-382">Int32</span></span>|  
|<span data-ttu-id="df8b2-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df8b2-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="df8b2-384">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-384">Int16</span></span>|  
|<span data-ttu-id="df8b2-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df8b2-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="df8b2-386">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-386">Int64</span></span>|  
|<span data-ttu-id="df8b2-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="df8b2-388">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-388">String</span></span>|  
|<span data-ttu-id="df8b2-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="df8b2-390">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-390">String</span></span>|  
|<span data-ttu-id="df8b2-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="df8b2-392">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-392">String</span></span>|  
|<span data-ttu-id="df8b2-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="df8b2-394">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-394">String</span></span>|  
|<span data-ttu-id="df8b2-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="df8b2-396">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-396">String</span></span>|  
|<span data-ttu-id="df8b2-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-397">COLLATION_NAME</span></span>|<span data-ttu-id="df8b2-398">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-398">String</span></span>|  
|<span data-ttu-id="df8b2-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="df8b2-400">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-400">String</span></span>|  
|<span data-ttu-id="df8b2-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="df8b2-402">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-402">String</span></span>|  
|<span data-ttu-id="df8b2-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-403">DOMAIN_NAME</span></span>|<span data-ttu-id="df8b2-404">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-404">String</span></span>|  
|<span data-ttu-id="df8b2-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-405">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-406">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="df8b2-407">过程</span><span class="sxs-lookup"><span data-stu-id="df8b2-407">Procedures</span></span>  
  
|<span data-ttu-id="df8b2-408">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-408">ColumnName</span></span>|<span data-ttu-id="df8b2-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df8b2-411">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-411">String</span></span>|  
|<span data-ttu-id="df8b2-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df8b2-413">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-413">String</span></span>|  
|<span data-ttu-id="df8b2-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="df8b2-415">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-415">String</span></span>|  
|<span data-ttu-id="df8b2-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="df8b2-417">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-417">Int16</span></span>|  
|<span data-ttu-id="df8b2-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="df8b2-419">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-419">String</span></span>|  
|<span data-ttu-id="df8b2-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-420">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-421">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-421">String</span></span>|  
|<span data-ttu-id="df8b2-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-422">DATE_CREATED</span></span>|<span data-ttu-id="df8b2-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-423">DateTime</span></span>|  
|<span data-ttu-id="df8b2-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df8b2-424">DATE_MODIFIED</span></span>|<span data-ttu-id="df8b2-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="df8b2-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="df8b2-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="df8b2-427">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-427">ColumnName</span></span>|<span data-ttu-id="df8b2-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df8b2-430">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-430">String</span></span>|  
|<span data-ttu-id="df8b2-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df8b2-432">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-432">String</span></span>|  
|<span data-ttu-id="df8b2-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="df8b2-434">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-434">String</span></span>|  
|<span data-ttu-id="df8b2-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-435">COLUMN_NAME</span></span>|<span data-ttu-id="df8b2-436">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-436">String</span></span>|  
|<span data-ttu-id="df8b2-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-437">COLUMN_GUID</span></span>|<span data-ttu-id="df8b2-438">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-438">Guid</span></span>|  
|<span data-ttu-id="df8b2-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-439">COLUMN_PROPID</span></span>|<span data-ttu-id="df8b2-440">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-440">Int64</span></span>|  
|<span data-ttu-id="df8b2-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="df8b2-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="df8b2-442">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-442">Int64</span></span>|  
|<span data-ttu-id="df8b2-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="df8b2-444">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-444">Int64</span></span>|  
|<span data-ttu-id="df8b2-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df8b2-445">IS_NULLABLE</span></span>|<span data-ttu-id="df8b2-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-446">Boolean</span></span>|  
|<span data-ttu-id="df8b2-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-447">DATA_TYPE</span></span>|<span data-ttu-id="df8b2-448">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-448">Int32</span></span>|  
|<span data-ttu-id="df8b2-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-449">TYPE_GUID</span></span>|<span data-ttu-id="df8b2-450">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-450">Guid</span></span>|  
|<span data-ttu-id="df8b2-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df8b2-452">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-452">Int64</span></span>|  
|<span data-ttu-id="df8b2-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df8b2-454">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-454">Int64</span></span>|  
|<span data-ttu-id="df8b2-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df8b2-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df8b2-456">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-456">Int32</span></span>|  
|<span data-ttu-id="df8b2-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df8b2-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="df8b2-458">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-458">Int16</span></span>|  
|<span data-ttu-id="df8b2-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-459">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-460">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-460">String</span></span>|  
|<span data-ttu-id="df8b2-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="df8b2-461">OVERLOAD</span></span>|<span data-ttu-id="df8b2-462">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="df8b2-463">视图</span><span class="sxs-lookup"><span data-stu-id="df8b2-463">Views</span></span>  
  
|<span data-ttu-id="df8b2-464">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-464">ColumnName</span></span>|<span data-ttu-id="df8b2-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-466">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-467">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-467">String</span></span>|  
|<span data-ttu-id="df8b2-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-469">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-469">String</span></span>|  
|<span data-ttu-id="df8b2-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-470">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-471">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-471">String</span></span>|  
|<span data-ttu-id="df8b2-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="df8b2-473">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-473">String</span></span>|  
|<span data-ttu-id="df8b2-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-474">CHECK_OPTION</span></span>|<span data-ttu-id="df8b2-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-475">Boolean</span></span>|  
|<span data-ttu-id="df8b2-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="df8b2-476">IS_UPDATABLE</span></span>|<span data-ttu-id="df8b2-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-477">Boolean</span></span>|  
|<span data-ttu-id="df8b2-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-478">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-479">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-479">String</span></span>|  
|<span data-ttu-id="df8b2-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-480">DATE_CREATED</span></span>|<span data-ttu-id="df8b2-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-481">DateTime</span></span>|  
|<span data-ttu-id="df8b2-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df8b2-482">DATE_MODIFIED</span></span>|<span data-ttu-id="df8b2-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="df8b2-484">索引</span><span class="sxs-lookup"><span data-stu-id="df8b2-484">Indexes</span></span>  
  
|<span data-ttu-id="df8b2-485">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-485">ColumnName</span></span>|<span data-ttu-id="df8b2-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-487">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-488">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-488">String</span></span>|  
|<span data-ttu-id="df8b2-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-490">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-490">String</span></span>|  
|<span data-ttu-id="df8b2-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-491">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-492">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-492">String</span></span>|  
|<span data-ttu-id="df8b2-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-493">INDEX_CATALOG</span></span>|<span data-ttu-id="df8b2-494">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-494">String</span></span>|  
|<span data-ttu-id="df8b2-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="df8b2-496">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-496">String</span></span>|  
|<span data-ttu-id="df8b2-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-497">INDEX_NAME</span></span>|<span data-ttu-id="df8b2-498">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-498">String</span></span>|  
|<span data-ttu-id="df8b2-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="df8b2-499">PRIMARY_KEY</span></span>|<span data-ttu-id="df8b2-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-500">Boolean</span></span>|  
|<span data-ttu-id="df8b2-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="df8b2-501">UNIQUE</span></span>|<span data-ttu-id="df8b2-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-502">Boolean</span></span>|  
|<span data-ttu-id="df8b2-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="df8b2-503">CLUSTERED</span></span>|<span data-ttu-id="df8b2-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-504">Boolean</span></span>|  
|<span data-ttu-id="df8b2-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-505">TYPE</span></span>|<span data-ttu-id="df8b2-506">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-506">Int32</span></span>|  
|<span data-ttu-id="df8b2-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="df8b2-507">FILL_FACTOR</span></span>|<span data-ttu-id="df8b2-508">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-508">Int32</span></span>|  
|<span data-ttu-id="df8b2-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="df8b2-509">INITIAL_SIZE</span></span>|<span data-ttu-id="df8b2-510">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-510">Int32</span></span>|  
|<span data-ttu-id="df8b2-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="df8b2-511">NULLS</span></span>|<span data-ttu-id="df8b2-512">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-512">Int32</span></span>|  
|<span data-ttu-id="df8b2-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="df8b2-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="df8b2-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-514">Boolean</span></span>|  
|<span data-ttu-id="df8b2-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="df8b2-515">AUTO_UPDATE</span></span>|<span data-ttu-id="df8b2-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-516">Boolean</span></span>|  
|<span data-ttu-id="df8b2-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="df8b2-517">NULL_COLLATION</span></span>|<span data-ttu-id="df8b2-518">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-518">Int32</span></span>|  
|<span data-ttu-id="df8b2-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="df8b2-520">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-520">Int64</span></span>|  
|<span data-ttu-id="df8b2-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-521">COLUMN_NAME</span></span>|<span data-ttu-id="df8b2-522">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-522">String</span></span>|  
|<span data-ttu-id="df8b2-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-523">COLUMN_GUID</span></span>|<span data-ttu-id="df8b2-524">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-524">Guid</span></span>|  
|<span data-ttu-id="df8b2-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-525">COLUMN_PROPID</span></span>|<span data-ttu-id="df8b2-526">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-526">Int64</span></span>|  
|<span data-ttu-id="df8b2-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="df8b2-527">COLLATION</span></span>|<span data-ttu-id="df8b2-528">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-528">Int16</span></span>|  
|<span data-ttu-id="df8b2-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="df8b2-529">CARDINALITY</span></span>|<span data-ttu-id="df8b2-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="df8b2-530">Decimal</span></span>|  
|<span data-ttu-id="df8b2-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="df8b2-531">PAGES</span></span>|<span data-ttu-id="df8b2-532">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-532">Int32</span></span>|  
|<span data-ttu-id="df8b2-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-533">FILTER_CONDITION</span></span>|<span data-ttu-id="df8b2-534">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-534">String</span></span>|  
|<span data-ttu-id="df8b2-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-535">INTEGRATED</span></span>|<span data-ttu-id="df8b2-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="df8b2-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="df8b2-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="df8b2-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="df8b2-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="df8b2-539">表</span><span class="sxs-lookup"><span data-stu-id="df8b2-539">Tables</span></span>  
  
-   <span data-ttu-id="df8b2-540">Columns</span><span class="sxs-lookup"><span data-stu-id="df8b2-540">Columns</span></span>  
  
-   <span data-ttu-id="df8b2-541">过程</span><span class="sxs-lookup"><span data-stu-id="df8b2-541">Procedures</span></span>  
  
-   <span data-ttu-id="df8b2-542">视图</span><span class="sxs-lookup"><span data-stu-id="df8b2-542">Views</span></span>  
  
-   <span data-ttu-id="df8b2-543">索引</span><span class="sxs-lookup"><span data-stu-id="df8b2-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="df8b2-544">表</span><span class="sxs-lookup"><span data-stu-id="df8b2-544">Tables</span></span>  
  
|<span data-ttu-id="df8b2-545">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-545">ColumnName</span></span>|<span data-ttu-id="df8b2-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-547">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-548">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-548">String</span></span>|  
|<span data-ttu-id="df8b2-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-550">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-550">String</span></span>|  
|<span data-ttu-id="df8b2-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-551">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-552">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-552">String</span></span>|  
|<span data-ttu-id="df8b2-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-553">TABLE_TYPE</span></span>|<span data-ttu-id="df8b2-554">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-554">String</span></span>|  
|<span data-ttu-id="df8b2-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-555">TABLE_GUID</span></span>|<span data-ttu-id="df8b2-556">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-556">Guid</span></span>|  
|<span data-ttu-id="df8b2-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-557">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-558">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-558">String</span></span>|  
|<span data-ttu-id="df8b2-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-559">TABLE_PROPID</span></span>|<span data-ttu-id="df8b2-560">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-560">Int64</span></span>|  
|<span data-ttu-id="df8b2-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-561">DATE_CREATED</span></span>|<span data-ttu-id="df8b2-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-562">DateTime</span></span>|  
|<span data-ttu-id="df8b2-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df8b2-563">DATE_MODIFIED</span></span>|<span data-ttu-id="df8b2-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="df8b2-565">Columns</span><span class="sxs-lookup"><span data-stu-id="df8b2-565">Columns</span></span>  
  
|<span data-ttu-id="df8b2-566">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-566">ColumnName</span></span>|<span data-ttu-id="df8b2-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-568">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-569">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-569">String</span></span>|  
|<span data-ttu-id="df8b2-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-571">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-571">String</span></span>|  
|<span data-ttu-id="df8b2-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-572">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-573">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-573">String</span></span>|  
|<span data-ttu-id="df8b2-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-574">COLUMN_NAME</span></span>|<span data-ttu-id="df8b2-575">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-575">String</span></span>|  
|<span data-ttu-id="df8b2-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-576">COLUMN_GUID</span></span>|<span data-ttu-id="df8b2-577">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-577">Guid</span></span>|  
|<span data-ttu-id="df8b2-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-578">COLUMN_PROPID</span></span>|<span data-ttu-id="df8b2-579">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-579">Int64</span></span>|  
|<span data-ttu-id="df8b2-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="df8b2-581">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-581">Int64</span></span>|  
|<span data-ttu-id="df8b2-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="df8b2-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="df8b2-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-583">Boolean</span></span>|  
|<span data-ttu-id="df8b2-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="df8b2-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="df8b2-585">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-585">String</span></span>|  
|<span data-ttu-id="df8b2-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="df8b2-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="df8b2-587">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-587">Int64</span></span>|  
|<span data-ttu-id="df8b2-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="df8b2-588">IS_NULLABLE</span></span>|<span data-ttu-id="df8b2-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-589">Boolean</span></span>|  
|<span data-ttu-id="df8b2-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-590">DATA_TYPE</span></span>|<span data-ttu-id="df8b2-591">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-591">Int32</span></span>|  
|<span data-ttu-id="df8b2-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-592">TYPE_GUID</span></span>|<span data-ttu-id="df8b2-593">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-593">Guid</span></span>|  
|<span data-ttu-id="df8b2-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="df8b2-595">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-595">Int64</span></span>|  
|<span data-ttu-id="df8b2-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="df8b2-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="df8b2-597">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-597">Int64</span></span>|  
|<span data-ttu-id="df8b2-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df8b2-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="df8b2-599">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-599">Int32</span></span>|  
|<span data-ttu-id="df8b2-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="df8b2-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="df8b2-601">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-601">Int16</span></span>|  
|<span data-ttu-id="df8b2-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="df8b2-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="df8b2-603">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-603">Int64</span></span>|  
|<span data-ttu-id="df8b2-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="df8b2-605">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-605">String</span></span>|  
|<span data-ttu-id="df8b2-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="df8b2-607">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-607">String</span></span>|  
|<span data-ttu-id="df8b2-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="df8b2-609">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-609">String</span></span>|  
|<span data-ttu-id="df8b2-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="df8b2-611">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-611">String</span></span>|  
|<span data-ttu-id="df8b2-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="df8b2-613">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-613">String</span></span>|  
|<span data-ttu-id="df8b2-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-614">COLLATION_NAME</span></span>|<span data-ttu-id="df8b2-615">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-615">String</span></span>|  
|<span data-ttu-id="df8b2-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="df8b2-617">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-617">String</span></span>|  
|<span data-ttu-id="df8b2-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="df8b2-619">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-619">String</span></span>|  
|<span data-ttu-id="df8b2-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-620">DOMAIN_NAME</span></span>|<span data-ttu-id="df8b2-621">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-621">String</span></span>|  
|<span data-ttu-id="df8b2-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-622">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-623">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="df8b2-624">过程</span><span class="sxs-lookup"><span data-stu-id="df8b2-624">Procedures</span></span>  
  
|<span data-ttu-id="df8b2-625">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-625">ColumnName</span></span>|<span data-ttu-id="df8b2-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="df8b2-628">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-628">String</span></span>|  
|<span data-ttu-id="df8b2-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="df8b2-630">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-630">String</span></span>|  
|<span data-ttu-id="df8b2-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="df8b2-632">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-632">String</span></span>|  
|<span data-ttu-id="df8b2-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="df8b2-634">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-634">Int16</span></span>|  
|<span data-ttu-id="df8b2-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="df8b2-636">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-636">String</span></span>|  
|<span data-ttu-id="df8b2-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-637">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-638">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-638">String</span></span>|  
|<span data-ttu-id="df8b2-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-639">DATE_CREATED</span></span>|<span data-ttu-id="df8b2-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-640">DateTime</span></span>|  
|<span data-ttu-id="df8b2-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df8b2-641">DATE_MODIFIED</span></span>|<span data-ttu-id="df8b2-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="df8b2-643">视图</span><span class="sxs-lookup"><span data-stu-id="df8b2-643">Views</span></span>  
  
|<span data-ttu-id="df8b2-644">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-644">ColumnName</span></span>|<span data-ttu-id="df8b2-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-646">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-647">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-647">String</span></span>|  
|<span data-ttu-id="df8b2-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-649">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-649">String</span></span>|  
|<span data-ttu-id="df8b2-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-650">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-651">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-651">String</span></span>|  
|<span data-ttu-id="df8b2-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="df8b2-653">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-653">String</span></span>|  
|<span data-ttu-id="df8b2-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-654">CHECK_OPTION</span></span>|<span data-ttu-id="df8b2-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-655">Boolean</span></span>|  
|<span data-ttu-id="df8b2-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="df8b2-656">IS_UPDATABLE</span></span>|<span data-ttu-id="df8b2-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-657">Boolean</span></span>|  
|<span data-ttu-id="df8b2-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df8b2-658">DESCRIPTION</span></span>|<span data-ttu-id="df8b2-659">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-659">String</span></span>|  
|<span data-ttu-id="df8b2-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-660">DATE_CREATED</span></span>|<span data-ttu-id="df8b2-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-661">DateTime</span></span>|  
|<span data-ttu-id="df8b2-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="df8b2-662">DATE_MODIFIED</span></span>|<span data-ttu-id="df8b2-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="df8b2-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="df8b2-664">索引</span><span class="sxs-lookup"><span data-stu-id="df8b2-664">Indexes</span></span>  
  
|<span data-ttu-id="df8b2-665">列名</span><span class="sxs-lookup"><span data-stu-id="df8b2-665">ColumnName</span></span>|<span data-ttu-id="df8b2-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="df8b2-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="df8b2-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-667">TABLE_CATALOG</span></span>|<span data-ttu-id="df8b2-668">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-668">String</span></span>|  
|<span data-ttu-id="df8b2-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="df8b2-670">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-670">String</span></span>|  
|<span data-ttu-id="df8b2-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-671">TABLE_NAME</span></span>|<span data-ttu-id="df8b2-672">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-672">String</span></span>|  
|<span data-ttu-id="df8b2-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df8b2-673">INDEX_CATALOG</span></span>|<span data-ttu-id="df8b2-674">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-674">String</span></span>|  
|<span data-ttu-id="df8b2-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df8b2-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="df8b2-676">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-676">String</span></span>|  
|<span data-ttu-id="df8b2-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-677">INDEX_NAME</span></span>|<span data-ttu-id="df8b2-678">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-678">String</span></span>|  
|<span data-ttu-id="df8b2-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="df8b2-679">PRIMARY_KEY</span></span>|<span data-ttu-id="df8b2-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-680">Boolean</span></span>|  
|<span data-ttu-id="df8b2-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="df8b2-681">UNIQUE</span></span>|<span data-ttu-id="df8b2-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-682">Boolean</span></span>|  
|<span data-ttu-id="df8b2-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="df8b2-683">CLUSTERED</span></span>|<span data-ttu-id="df8b2-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-684">Boolean</span></span>|  
|<span data-ttu-id="df8b2-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="df8b2-685">TYPE</span></span>|<span data-ttu-id="df8b2-686">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-686">Int32</span></span>|  
|<span data-ttu-id="df8b2-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="df8b2-687">FILL_FACTOR</span></span>|<span data-ttu-id="df8b2-688">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-688">Int32</span></span>|  
|<span data-ttu-id="df8b2-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="df8b2-689">INITIAL_SIZE</span></span>|<span data-ttu-id="df8b2-690">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-690">Int32</span></span>|  
|<span data-ttu-id="df8b2-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="df8b2-691">NULLS</span></span>|<span data-ttu-id="df8b2-692">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-692">Int32</span></span>|  
|<span data-ttu-id="df8b2-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="df8b2-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="df8b2-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-694">Boolean</span></span>|  
|<span data-ttu-id="df8b2-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="df8b2-695">AUTO_UPDATE</span></span>|<span data-ttu-id="df8b2-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-696">Boolean</span></span>|  
|<span data-ttu-id="df8b2-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="df8b2-697">NULL_COLLATION</span></span>|<span data-ttu-id="df8b2-698">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-698">Int32</span></span>|  
|<span data-ttu-id="df8b2-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="df8b2-700">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-700">Int64</span></span>|  
|<span data-ttu-id="df8b2-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df8b2-701">COLUMN_NAME</span></span>|<span data-ttu-id="df8b2-702">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-702">String</span></span>|  
|<span data-ttu-id="df8b2-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="df8b2-703">COLUMN_GUID</span></span>|<span data-ttu-id="df8b2-704">Guid</span><span class="sxs-lookup"><span data-stu-id="df8b2-704">Guid</span></span>|  
|<span data-ttu-id="df8b2-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="df8b2-705">COLUMN_PROPID</span></span>|<span data-ttu-id="df8b2-706">Int64</span><span class="sxs-lookup"><span data-stu-id="df8b2-706">Int64</span></span>|  
|<span data-ttu-id="df8b2-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="df8b2-707">COLLATION</span></span>|<span data-ttu-id="df8b2-708">Int16</span><span class="sxs-lookup"><span data-stu-id="df8b2-708">Int16</span></span>|  
|<span data-ttu-id="df8b2-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="df8b2-709">CARDINALITY</span></span>|<span data-ttu-id="df8b2-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="df8b2-710">Decimal</span></span>|  
|<span data-ttu-id="df8b2-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="df8b2-711">PAGES</span></span>|<span data-ttu-id="df8b2-712">Int32</span><span class="sxs-lookup"><span data-stu-id="df8b2-712">Int32</span></span>|  
|<span data-ttu-id="df8b2-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="df8b2-713">FILTER_CONDITION</span></span>|<span data-ttu-id="df8b2-714">String</span><span class="sxs-lookup"><span data-stu-id="df8b2-714">String</span></span>|  
|<span data-ttu-id="df8b2-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="df8b2-715">INTEGRATED</span></span>|<span data-ttu-id="df8b2-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="df8b2-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df8b2-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="df8b2-717">See Also</span></span>  
 [<span data-ttu-id="df8b2-718">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="df8b2-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
