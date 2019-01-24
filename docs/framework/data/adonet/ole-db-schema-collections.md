---
title: OLE DB 架构集合
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f753f35aab0a0200da5de463a73abb9813253d11
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658450"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="37fe2-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="37fe2-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="37fe2-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="37fe2-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="37fe2-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="37fe2-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="37fe2-105">Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="37fe2-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="37fe2-106">表</span><span class="sxs-lookup"><span data-stu-id="37fe2-106">Tables</span></span>  
  
-   <span data-ttu-id="37fe2-107">Columns</span><span class="sxs-lookup"><span data-stu-id="37fe2-107">Columns</span></span>  
  
-   <span data-ttu-id="37fe2-108">过程</span><span class="sxs-lookup"><span data-stu-id="37fe2-108">Procedures</span></span>  
  
-   <span data-ttu-id="37fe2-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="37fe2-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="37fe2-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="37fe2-110">Catalog</span></span>  
  
-   <span data-ttu-id="37fe2-111">索引</span><span class="sxs-lookup"><span data-stu-id="37fe2-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="37fe2-112">表</span><span class="sxs-lookup"><span data-stu-id="37fe2-112">Tables</span></span>  
  
|<span data-ttu-id="37fe2-113">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-113">ColumnName</span></span>|<span data-ttu-id="37fe2-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-115">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-116">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-116">String</span></span>|  
|<span data-ttu-id="37fe2-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-118">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-118">String</span></span>|  
|<span data-ttu-id="37fe2-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-119">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-120">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-120">String</span></span>|  
|<span data-ttu-id="37fe2-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-121">TABLE_TYPE</span></span>|<span data-ttu-id="37fe2-122">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-122">String</span></span>|  
|<span data-ttu-id="37fe2-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-123">TABLE_GUID</span></span>|<span data-ttu-id="37fe2-124">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-124">Guid</span></span>|  
|<span data-ttu-id="37fe2-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-125">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-126">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-126">String</span></span>|  
|<span data-ttu-id="37fe2-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-127">TABLE_PROPID</span></span>|<span data-ttu-id="37fe2-128">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-128">Int64</span></span>|  
|<span data-ttu-id="37fe2-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-129">DATE_CREATED</span></span>|<span data-ttu-id="37fe2-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-130">DateTime</span></span>|  
|<span data-ttu-id="37fe2-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37fe2-131">DATE_MODIFIED</span></span>|<span data-ttu-id="37fe2-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="37fe2-133">Columns</span><span class="sxs-lookup"><span data-stu-id="37fe2-133">Columns</span></span>  
  
|<span data-ttu-id="37fe2-134">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-134">ColumnName</span></span>|<span data-ttu-id="37fe2-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-136">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-137">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-137">String</span></span>|  
|<span data-ttu-id="37fe2-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-139">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-139">String</span></span>|  
|<span data-ttu-id="37fe2-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-140">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-141">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-141">String</span></span>|  
|<span data-ttu-id="37fe2-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-142">COLUMN_NAME</span></span>|<span data-ttu-id="37fe2-143">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-143">String</span></span>|  
|<span data-ttu-id="37fe2-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-144">COLUMN_GUID</span></span>|<span data-ttu-id="37fe2-145">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-145">Guid</span></span>|  
|<span data-ttu-id="37fe2-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-146">COLUMN_PROPID</span></span>|<span data-ttu-id="37fe2-147">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-147">Int64</span></span>|  
|<span data-ttu-id="37fe2-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="37fe2-149">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-149">Int64</span></span>|  
|<span data-ttu-id="37fe2-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37fe2-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="37fe2-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-151">Boolean</span></span>|  
|<span data-ttu-id="37fe2-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37fe2-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="37fe2-153">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-153">String</span></span>|  
|<span data-ttu-id="37fe2-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37fe2-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="37fe2-155">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-155">Int64</span></span>|  
|<span data-ttu-id="37fe2-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37fe2-156">IS_NULLABLE</span></span>|<span data-ttu-id="37fe2-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-157">Boolean</span></span>|  
|<span data-ttu-id="37fe2-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-158">DATA_TYPE</span></span>|<span data-ttu-id="37fe2-159">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-159">Int32</span></span>|  
|<span data-ttu-id="37fe2-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-160">TYPE_GUID</span></span>|<span data-ttu-id="37fe2-161">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-161">Guid</span></span>|  
|<span data-ttu-id="37fe2-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37fe2-163">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-163">Int64</span></span>|  
|<span data-ttu-id="37fe2-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37fe2-165">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-165">Int64</span></span>|  
|<span data-ttu-id="37fe2-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37fe2-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37fe2-167">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-167">Int32</span></span>|  
|<span data-ttu-id="37fe2-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37fe2-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="37fe2-169">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-169">Int16</span></span>|  
|<span data-ttu-id="37fe2-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37fe2-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="37fe2-171">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-171">Int64</span></span>|  
|<span data-ttu-id="37fe2-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="37fe2-173">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-173">String</span></span>|  
|<span data-ttu-id="37fe2-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="37fe2-175">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-175">String</span></span>|  
|<span data-ttu-id="37fe2-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="37fe2-177">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-177">String</span></span>|  
|<span data-ttu-id="37fe2-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="37fe2-179">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-179">String</span></span>|  
|<span data-ttu-id="37fe2-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="37fe2-181">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-181">String</span></span>|  
|<span data-ttu-id="37fe2-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-182">COLLATION_NAME</span></span>|<span data-ttu-id="37fe2-183">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-183">String</span></span>|  
|<span data-ttu-id="37fe2-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="37fe2-185">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-185">String</span></span>|  
|<span data-ttu-id="37fe2-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="37fe2-187">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-187">String</span></span>|  
|<span data-ttu-id="37fe2-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-188">DOMAIN_NAME</span></span>|<span data-ttu-id="37fe2-189">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-189">String</span></span>|  
|<span data-ttu-id="37fe2-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-190">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-191">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-191">String</span></span>|  
|<span data-ttu-id="37fe2-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="37fe2-192">COLUMN_LCID</span></span>|<span data-ttu-id="37fe2-193">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-193">Int32</span></span>|  
|<span data-ttu-id="37fe2-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="37fe2-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="37fe2-195">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-195">Int32</span></span>|  
|<span data-ttu-id="37fe2-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="37fe2-196">COLUMN_SORTID</span></span>|<span data-ttu-id="37fe2-197">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-197">Int32</span></span>|  
|<span data-ttu-id="37fe2-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="37fe2-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="37fe2-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="37fe2-199">Byte[]</span></span>|  
|<span data-ttu-id="37fe2-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="37fe2-200">IS_COMPUTED</span></span>|<span data-ttu-id="37fe2-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="37fe2-202">过程</span><span class="sxs-lookup"><span data-stu-id="37fe2-202">Procedures</span></span>  
  
|<span data-ttu-id="37fe2-203">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-203">ColumnName</span></span>|<span data-ttu-id="37fe2-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37fe2-206">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-206">String</span></span>|  
|<span data-ttu-id="37fe2-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37fe2-208">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-208">String</span></span>|  
|<span data-ttu-id="37fe2-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="37fe2-210">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-210">String</span></span>|  
|<span data-ttu-id="37fe2-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="37fe2-212">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-212">Int16</span></span>|  
|<span data-ttu-id="37fe2-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="37fe2-214">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-214">String</span></span>|  
|<span data-ttu-id="37fe2-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-215">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-216">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-216">String</span></span>|  
|<span data-ttu-id="37fe2-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-217">DATE_CREATED</span></span>|<span data-ttu-id="37fe2-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-218">DateTime</span></span>|  
|<span data-ttu-id="37fe2-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37fe2-219">DATE_MODIFIED</span></span>|<span data-ttu-id="37fe2-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="37fe2-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="37fe2-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="37fe2-222">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-222">ColumnName</span></span>|<span data-ttu-id="37fe2-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37fe2-225">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-225">String</span></span>|  
|<span data-ttu-id="37fe2-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37fe2-227">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-227">String</span></span>|  
|<span data-ttu-id="37fe2-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="37fe2-229">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-229">String</span></span>|  
|<span data-ttu-id="37fe2-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-230">PARAMETER_NAME</span></span>|<span data-ttu-id="37fe2-231">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-231">String</span></span>|  
|<span data-ttu-id="37fe2-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="37fe2-233">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-233">Int32</span></span>|  
|<span data-ttu-id="37fe2-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="37fe2-235">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-235">Int32</span></span>|  
|<span data-ttu-id="37fe2-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37fe2-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="37fe2-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-237">Boolean</span></span>|  
|<span data-ttu-id="37fe2-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37fe2-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="37fe2-239">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-239">String</span></span>|  
|<span data-ttu-id="37fe2-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37fe2-240">IS_NULLABLE</span></span>|<span data-ttu-id="37fe2-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-241">Boolean</span></span>|  
|<span data-ttu-id="37fe2-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-242">DATA_TYPE</span></span>|<span data-ttu-id="37fe2-243">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-243">Int32</span></span>|  
|<span data-ttu-id="37fe2-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37fe2-245">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-245">Int64</span></span>|  
|<span data-ttu-id="37fe2-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37fe2-247">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-247">Int64</span></span>|  
|<span data-ttu-id="37fe2-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37fe2-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37fe2-249">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-249">Int32</span></span>|  
|<span data-ttu-id="37fe2-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37fe2-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="37fe2-251">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-251">Int16</span></span>|  
|<span data-ttu-id="37fe2-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-252">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-253">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-253">String</span></span>|  
|<span data-ttu-id="37fe2-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-254">TYPE_NAME</span></span>|<span data-ttu-id="37fe2-255">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-255">String</span></span>|  
|<span data-ttu-id="37fe2-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="37fe2-257">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="37fe2-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="37fe2-258">Catalog</span></span>  
  
|<span data-ttu-id="37fe2-259">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-259">ColumnName</span></span>|<span data-ttu-id="37fe2-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-261">CATALOG_NAME</span></span>|<span data-ttu-id="37fe2-262">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-262">String</span></span>|  
|<span data-ttu-id="37fe2-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-263">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-264">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="37fe2-265">索引</span><span class="sxs-lookup"><span data-stu-id="37fe2-265">Indexes</span></span>  
  
|<span data-ttu-id="37fe2-266">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-266">ColumnName</span></span>|<span data-ttu-id="37fe2-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-268">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-269">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-269">String</span></span>|  
|<span data-ttu-id="37fe2-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-271">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-271">String</span></span>|  
|<span data-ttu-id="37fe2-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-272">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-273">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-273">String</span></span>|  
|<span data-ttu-id="37fe2-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-274">INDEX_CATALOG</span></span>|<span data-ttu-id="37fe2-275">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-275">String</span></span>|  
|<span data-ttu-id="37fe2-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="37fe2-277">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-277">String</span></span>|  
|<span data-ttu-id="37fe2-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-278">INDEX_NAME</span></span>|<span data-ttu-id="37fe2-279">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-279">String</span></span>|  
|<span data-ttu-id="37fe2-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="37fe2-280">PRIMARY_KEY</span></span>|<span data-ttu-id="37fe2-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-281">Boolean</span></span>|  
|<span data-ttu-id="37fe2-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="37fe2-282">UNIQUE</span></span>|<span data-ttu-id="37fe2-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-283">Boolean</span></span>|  
|<span data-ttu-id="37fe2-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="37fe2-284">CLUSTERED</span></span>|<span data-ttu-id="37fe2-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-285">Boolean</span></span>|  
|<span data-ttu-id="37fe2-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-286">TYPE</span></span>|<span data-ttu-id="37fe2-287">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-287">Int32</span></span>|  
|<span data-ttu-id="37fe2-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="37fe2-288">FILL_FACTOR</span></span>|<span data-ttu-id="37fe2-289">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-289">Int32</span></span>|  
|<span data-ttu-id="37fe2-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="37fe2-290">INITIAL_SIZE</span></span>|<span data-ttu-id="37fe2-291">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-291">Int32</span></span>|  
|<span data-ttu-id="37fe2-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="37fe2-292">NULLS</span></span>|<span data-ttu-id="37fe2-293">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-293">Int32</span></span>|  
|<span data-ttu-id="37fe2-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="37fe2-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="37fe2-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-295">Boolean</span></span>|  
|<span data-ttu-id="37fe2-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="37fe2-296">AUTO_UPDATE</span></span>|<span data-ttu-id="37fe2-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-297">Boolean</span></span>|  
|<span data-ttu-id="37fe2-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="37fe2-298">NULL_COLLATION</span></span>|<span data-ttu-id="37fe2-299">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-299">Int32</span></span>|  
|<span data-ttu-id="37fe2-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="37fe2-301">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-301">Int64</span></span>|  
|<span data-ttu-id="37fe2-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-302">COLUMN_NAME</span></span>|<span data-ttu-id="37fe2-303">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-303">String</span></span>|  
|<span data-ttu-id="37fe2-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-304">COLUMN_GUID</span></span>|<span data-ttu-id="37fe2-305">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-305">Guid</span></span>|  
|<span data-ttu-id="37fe2-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-306">COLUMN_PROPID</span></span>|<span data-ttu-id="37fe2-307">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-307">Int64</span></span>|  
|<span data-ttu-id="37fe2-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="37fe2-308">COLLATION</span></span>|<span data-ttu-id="37fe2-309">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-309">Int16</span></span>|  
|<span data-ttu-id="37fe2-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="37fe2-310">CARDINALITY</span></span>|<span data-ttu-id="37fe2-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="37fe2-311">Decimal</span></span>|  
|<span data-ttu-id="37fe2-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="37fe2-312">PAGES</span></span>|<span data-ttu-id="37fe2-313">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-313">Int32</span></span>|  
|<span data-ttu-id="37fe2-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-314">FILTER_CONDITION</span></span>|<span data-ttu-id="37fe2-315">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-315">String</span></span>|  
|<span data-ttu-id="37fe2-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-316">INTEGRATED</span></span>|<span data-ttu-id="37fe2-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="37fe2-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="37fe2-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="37fe2-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="37fe2-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="37fe2-320">表</span><span class="sxs-lookup"><span data-stu-id="37fe2-320">Tables</span></span>  
  
-   <span data-ttu-id="37fe2-321">Columns</span><span class="sxs-lookup"><span data-stu-id="37fe2-321">Columns</span></span>  
  
-   <span data-ttu-id="37fe2-322">过程</span><span class="sxs-lookup"><span data-stu-id="37fe2-322">Procedures</span></span>  
  
-   <span data-ttu-id="37fe2-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="37fe2-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="37fe2-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="37fe2-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="37fe2-325">视图</span><span class="sxs-lookup"><span data-stu-id="37fe2-325">Views</span></span>  
  
-   <span data-ttu-id="37fe2-326">索引</span><span class="sxs-lookup"><span data-stu-id="37fe2-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="37fe2-327">表</span><span class="sxs-lookup"><span data-stu-id="37fe2-327">Tables</span></span>  
  
|<span data-ttu-id="37fe2-328">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-328">ColumnName</span></span>|<span data-ttu-id="37fe2-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-330">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-331">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-331">String</span></span>|  
|<span data-ttu-id="37fe2-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-333">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-333">String</span></span>|  
|<span data-ttu-id="37fe2-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-334">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-335">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-335">String</span></span>|  
|<span data-ttu-id="37fe2-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-336">TABLE_TYPE</span></span>|<span data-ttu-id="37fe2-337">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-337">String</span></span>|  
|<span data-ttu-id="37fe2-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-338">TABLE_GUID</span></span>|<span data-ttu-id="37fe2-339">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-339">Guid</span></span>|  
|<span data-ttu-id="37fe2-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-340">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-341">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-341">String</span></span>|  
|<span data-ttu-id="37fe2-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-342">TABLE_PROPID</span></span>|<span data-ttu-id="37fe2-343">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-343">Int64</span></span>|  
|<span data-ttu-id="37fe2-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-344">DATE_CREATED</span></span>|<span data-ttu-id="37fe2-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-345">DateTime</span></span>|  
|<span data-ttu-id="37fe2-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37fe2-346">DATE_MODIFIED</span></span>|<span data-ttu-id="37fe2-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="37fe2-348">Columns</span><span class="sxs-lookup"><span data-stu-id="37fe2-348">Columns</span></span>  
  
|<span data-ttu-id="37fe2-349">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-349">ColumnName</span></span>|<span data-ttu-id="37fe2-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-351">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-352">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-352">String</span></span>|  
|<span data-ttu-id="37fe2-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-354">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-354">String</span></span>|  
|<span data-ttu-id="37fe2-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-355">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-356">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-356">String</span></span>|  
|<span data-ttu-id="37fe2-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-357">COLUMN_NAME</span></span>|<span data-ttu-id="37fe2-358">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-358">String</span></span>|  
|<span data-ttu-id="37fe2-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-359">COLUMN_GUID</span></span>|<span data-ttu-id="37fe2-360">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-360">Guid</span></span>|  
|<span data-ttu-id="37fe2-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-361">COLUMN_PROPID</span></span>|<span data-ttu-id="37fe2-362">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-362">Int64</span></span>|  
|<span data-ttu-id="37fe2-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="37fe2-364">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-364">Int64</span></span>|  
|<span data-ttu-id="37fe2-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37fe2-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="37fe2-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-366">Boolean</span></span>|  
|<span data-ttu-id="37fe2-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37fe2-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="37fe2-368">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-368">String</span></span>|  
|<span data-ttu-id="37fe2-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37fe2-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="37fe2-370">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-370">Int64</span></span>|  
|<span data-ttu-id="37fe2-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37fe2-371">IS_NULLABLE</span></span>|<span data-ttu-id="37fe2-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-372">Boolean</span></span>|  
|<span data-ttu-id="37fe2-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-373">DATA_TYPE</span></span>|<span data-ttu-id="37fe2-374">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-374">Int32</span></span>|  
|<span data-ttu-id="37fe2-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-375">TYPE_GUID</span></span>|<span data-ttu-id="37fe2-376">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-376">Guid</span></span>|  
|<span data-ttu-id="37fe2-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37fe2-378">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-378">Int64</span></span>|  
|<span data-ttu-id="37fe2-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37fe2-380">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-380">Int64</span></span>|  
|<span data-ttu-id="37fe2-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37fe2-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37fe2-382">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-382">Int32</span></span>|  
|<span data-ttu-id="37fe2-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37fe2-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="37fe2-384">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-384">Int16</span></span>|  
|<span data-ttu-id="37fe2-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37fe2-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="37fe2-386">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-386">Int64</span></span>|  
|<span data-ttu-id="37fe2-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="37fe2-388">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-388">String</span></span>|  
|<span data-ttu-id="37fe2-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="37fe2-390">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-390">String</span></span>|  
|<span data-ttu-id="37fe2-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="37fe2-392">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-392">String</span></span>|  
|<span data-ttu-id="37fe2-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="37fe2-394">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-394">String</span></span>|  
|<span data-ttu-id="37fe2-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="37fe2-396">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-396">String</span></span>|  
|<span data-ttu-id="37fe2-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-397">COLLATION_NAME</span></span>|<span data-ttu-id="37fe2-398">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-398">String</span></span>|  
|<span data-ttu-id="37fe2-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="37fe2-400">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-400">String</span></span>|  
|<span data-ttu-id="37fe2-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="37fe2-402">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-402">String</span></span>|  
|<span data-ttu-id="37fe2-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-403">DOMAIN_NAME</span></span>|<span data-ttu-id="37fe2-404">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-404">String</span></span>|  
|<span data-ttu-id="37fe2-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-405">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-406">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="37fe2-407">过程</span><span class="sxs-lookup"><span data-stu-id="37fe2-407">Procedures</span></span>  
  
|<span data-ttu-id="37fe2-408">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-408">ColumnName</span></span>|<span data-ttu-id="37fe2-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37fe2-411">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-411">String</span></span>|  
|<span data-ttu-id="37fe2-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37fe2-413">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-413">String</span></span>|  
|<span data-ttu-id="37fe2-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="37fe2-415">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-415">String</span></span>|  
|<span data-ttu-id="37fe2-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="37fe2-417">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-417">Int16</span></span>|  
|<span data-ttu-id="37fe2-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="37fe2-419">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-419">String</span></span>|  
|<span data-ttu-id="37fe2-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-420">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-421">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-421">String</span></span>|  
|<span data-ttu-id="37fe2-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-422">DATE_CREATED</span></span>|<span data-ttu-id="37fe2-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-423">DateTime</span></span>|  
|<span data-ttu-id="37fe2-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37fe2-424">DATE_MODIFIED</span></span>|<span data-ttu-id="37fe2-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="37fe2-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="37fe2-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="37fe2-427">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-427">ColumnName</span></span>|<span data-ttu-id="37fe2-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37fe2-430">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-430">String</span></span>|  
|<span data-ttu-id="37fe2-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37fe2-432">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-432">String</span></span>|  
|<span data-ttu-id="37fe2-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="37fe2-434">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-434">String</span></span>|  
|<span data-ttu-id="37fe2-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-435">COLUMN_NAME</span></span>|<span data-ttu-id="37fe2-436">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-436">String</span></span>|  
|<span data-ttu-id="37fe2-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-437">COLUMN_GUID</span></span>|<span data-ttu-id="37fe2-438">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-438">Guid</span></span>|  
|<span data-ttu-id="37fe2-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-439">COLUMN_PROPID</span></span>|<span data-ttu-id="37fe2-440">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-440">Int64</span></span>|  
|<span data-ttu-id="37fe2-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="37fe2-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="37fe2-442">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-442">Int64</span></span>|  
|<span data-ttu-id="37fe2-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="37fe2-444">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-444">Int64</span></span>|  
|<span data-ttu-id="37fe2-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37fe2-445">IS_NULLABLE</span></span>|<span data-ttu-id="37fe2-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-446">Boolean</span></span>|  
|<span data-ttu-id="37fe2-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-447">DATA_TYPE</span></span>|<span data-ttu-id="37fe2-448">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-448">Int32</span></span>|  
|<span data-ttu-id="37fe2-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-449">TYPE_GUID</span></span>|<span data-ttu-id="37fe2-450">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-450">Guid</span></span>|  
|<span data-ttu-id="37fe2-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37fe2-452">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-452">Int64</span></span>|  
|<span data-ttu-id="37fe2-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37fe2-454">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-454">Int64</span></span>|  
|<span data-ttu-id="37fe2-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37fe2-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37fe2-456">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-456">Int32</span></span>|  
|<span data-ttu-id="37fe2-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37fe2-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="37fe2-458">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-458">Int16</span></span>|  
|<span data-ttu-id="37fe2-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-459">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-460">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-460">String</span></span>|  
|<span data-ttu-id="37fe2-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="37fe2-461">OVERLOAD</span></span>|<span data-ttu-id="37fe2-462">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="37fe2-463">视图</span><span class="sxs-lookup"><span data-stu-id="37fe2-463">Views</span></span>  
  
|<span data-ttu-id="37fe2-464">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-464">ColumnName</span></span>|<span data-ttu-id="37fe2-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-466">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-467">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-467">String</span></span>|  
|<span data-ttu-id="37fe2-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-469">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-469">String</span></span>|  
|<span data-ttu-id="37fe2-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-470">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-471">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-471">String</span></span>|  
|<span data-ttu-id="37fe2-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="37fe2-473">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-473">String</span></span>|  
|<span data-ttu-id="37fe2-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-474">CHECK_OPTION</span></span>|<span data-ttu-id="37fe2-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-475">Boolean</span></span>|  
|<span data-ttu-id="37fe2-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="37fe2-476">IS_UPDATABLE</span></span>|<span data-ttu-id="37fe2-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-477">Boolean</span></span>|  
|<span data-ttu-id="37fe2-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-478">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-479">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-479">String</span></span>|  
|<span data-ttu-id="37fe2-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-480">DATE_CREATED</span></span>|<span data-ttu-id="37fe2-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-481">DateTime</span></span>|  
|<span data-ttu-id="37fe2-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37fe2-482">DATE_MODIFIED</span></span>|<span data-ttu-id="37fe2-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="37fe2-484">索引</span><span class="sxs-lookup"><span data-stu-id="37fe2-484">Indexes</span></span>  
  
|<span data-ttu-id="37fe2-485">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-485">ColumnName</span></span>|<span data-ttu-id="37fe2-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-487">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-488">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-488">String</span></span>|  
|<span data-ttu-id="37fe2-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-490">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-490">String</span></span>|  
|<span data-ttu-id="37fe2-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-491">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-492">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-492">String</span></span>|  
|<span data-ttu-id="37fe2-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-493">INDEX_CATALOG</span></span>|<span data-ttu-id="37fe2-494">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-494">String</span></span>|  
|<span data-ttu-id="37fe2-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="37fe2-496">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-496">String</span></span>|  
|<span data-ttu-id="37fe2-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-497">INDEX_NAME</span></span>|<span data-ttu-id="37fe2-498">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-498">String</span></span>|  
|<span data-ttu-id="37fe2-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="37fe2-499">PRIMARY_KEY</span></span>|<span data-ttu-id="37fe2-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-500">Boolean</span></span>|  
|<span data-ttu-id="37fe2-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="37fe2-501">UNIQUE</span></span>|<span data-ttu-id="37fe2-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-502">Boolean</span></span>|  
|<span data-ttu-id="37fe2-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="37fe2-503">CLUSTERED</span></span>|<span data-ttu-id="37fe2-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-504">Boolean</span></span>|  
|<span data-ttu-id="37fe2-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-505">TYPE</span></span>|<span data-ttu-id="37fe2-506">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-506">Int32</span></span>|  
|<span data-ttu-id="37fe2-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="37fe2-507">FILL_FACTOR</span></span>|<span data-ttu-id="37fe2-508">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-508">Int32</span></span>|  
|<span data-ttu-id="37fe2-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="37fe2-509">INITIAL_SIZE</span></span>|<span data-ttu-id="37fe2-510">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-510">Int32</span></span>|  
|<span data-ttu-id="37fe2-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="37fe2-511">NULLS</span></span>|<span data-ttu-id="37fe2-512">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-512">Int32</span></span>|  
|<span data-ttu-id="37fe2-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="37fe2-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="37fe2-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-514">Boolean</span></span>|  
|<span data-ttu-id="37fe2-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="37fe2-515">AUTO_UPDATE</span></span>|<span data-ttu-id="37fe2-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-516">Boolean</span></span>|  
|<span data-ttu-id="37fe2-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="37fe2-517">NULL_COLLATION</span></span>|<span data-ttu-id="37fe2-518">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-518">Int32</span></span>|  
|<span data-ttu-id="37fe2-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="37fe2-520">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-520">Int64</span></span>|  
|<span data-ttu-id="37fe2-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-521">COLUMN_NAME</span></span>|<span data-ttu-id="37fe2-522">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-522">String</span></span>|  
|<span data-ttu-id="37fe2-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-523">COLUMN_GUID</span></span>|<span data-ttu-id="37fe2-524">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-524">Guid</span></span>|  
|<span data-ttu-id="37fe2-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-525">COLUMN_PROPID</span></span>|<span data-ttu-id="37fe2-526">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-526">Int64</span></span>|  
|<span data-ttu-id="37fe2-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="37fe2-527">COLLATION</span></span>|<span data-ttu-id="37fe2-528">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-528">Int16</span></span>|  
|<span data-ttu-id="37fe2-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="37fe2-529">CARDINALITY</span></span>|<span data-ttu-id="37fe2-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="37fe2-530">Decimal</span></span>|  
|<span data-ttu-id="37fe2-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="37fe2-531">PAGES</span></span>|<span data-ttu-id="37fe2-532">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-532">Int32</span></span>|  
|<span data-ttu-id="37fe2-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-533">FILTER_CONDITION</span></span>|<span data-ttu-id="37fe2-534">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-534">String</span></span>|  
|<span data-ttu-id="37fe2-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-535">INTEGRATED</span></span>|<span data-ttu-id="37fe2-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="37fe2-537">Microsoft Jet OLE DB     </span><span class="sxs-lookup"><span data-stu-id="37fe2-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="37fe2-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="37fe2-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="37fe2-539">表</span><span class="sxs-lookup"><span data-stu-id="37fe2-539">Tables</span></span>  
  
-   <span data-ttu-id="37fe2-540">Columns</span><span class="sxs-lookup"><span data-stu-id="37fe2-540">Columns</span></span>  
  
-   <span data-ttu-id="37fe2-541">过程</span><span class="sxs-lookup"><span data-stu-id="37fe2-541">Procedures</span></span>  
  
-   <span data-ttu-id="37fe2-542">视图</span><span class="sxs-lookup"><span data-stu-id="37fe2-542">Views</span></span>  
  
-   <span data-ttu-id="37fe2-543">索引</span><span class="sxs-lookup"><span data-stu-id="37fe2-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="37fe2-544">表</span><span class="sxs-lookup"><span data-stu-id="37fe2-544">Tables</span></span>  
  
|<span data-ttu-id="37fe2-545">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-545">ColumnName</span></span>|<span data-ttu-id="37fe2-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-547">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-548">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-548">String</span></span>|  
|<span data-ttu-id="37fe2-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-550">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-550">String</span></span>|  
|<span data-ttu-id="37fe2-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-551">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-552">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-552">String</span></span>|  
|<span data-ttu-id="37fe2-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-553">TABLE_TYPE</span></span>|<span data-ttu-id="37fe2-554">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-554">String</span></span>|  
|<span data-ttu-id="37fe2-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-555">TABLE_GUID</span></span>|<span data-ttu-id="37fe2-556">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-556">Guid</span></span>|  
|<span data-ttu-id="37fe2-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-557">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-558">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-558">String</span></span>|  
|<span data-ttu-id="37fe2-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-559">TABLE_PROPID</span></span>|<span data-ttu-id="37fe2-560">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-560">Int64</span></span>|  
|<span data-ttu-id="37fe2-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-561">DATE_CREATED</span></span>|<span data-ttu-id="37fe2-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-562">DateTime</span></span>|  
|<span data-ttu-id="37fe2-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37fe2-563">DATE_MODIFIED</span></span>|<span data-ttu-id="37fe2-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="37fe2-565">Columns</span><span class="sxs-lookup"><span data-stu-id="37fe2-565">Columns</span></span>  
  
|<span data-ttu-id="37fe2-566">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-566">ColumnName</span></span>|<span data-ttu-id="37fe2-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-568">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-569">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-569">String</span></span>|  
|<span data-ttu-id="37fe2-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-571">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-571">String</span></span>|  
|<span data-ttu-id="37fe2-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-572">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-573">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-573">String</span></span>|  
|<span data-ttu-id="37fe2-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-574">COLUMN_NAME</span></span>|<span data-ttu-id="37fe2-575">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-575">String</span></span>|  
|<span data-ttu-id="37fe2-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-576">COLUMN_GUID</span></span>|<span data-ttu-id="37fe2-577">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-577">Guid</span></span>|  
|<span data-ttu-id="37fe2-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-578">COLUMN_PROPID</span></span>|<span data-ttu-id="37fe2-579">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-579">Int64</span></span>|  
|<span data-ttu-id="37fe2-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="37fe2-581">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-581">Int64</span></span>|  
|<span data-ttu-id="37fe2-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="37fe2-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="37fe2-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-583">Boolean</span></span>|  
|<span data-ttu-id="37fe2-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="37fe2-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="37fe2-585">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-585">String</span></span>|  
|<span data-ttu-id="37fe2-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="37fe2-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="37fe2-587">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-587">Int64</span></span>|  
|<span data-ttu-id="37fe2-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="37fe2-588">IS_NULLABLE</span></span>|<span data-ttu-id="37fe2-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-589">Boolean</span></span>|  
|<span data-ttu-id="37fe2-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-590">DATA_TYPE</span></span>|<span data-ttu-id="37fe2-591">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-591">Int32</span></span>|  
|<span data-ttu-id="37fe2-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-592">TYPE_GUID</span></span>|<span data-ttu-id="37fe2-593">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-593">Guid</span></span>|  
|<span data-ttu-id="37fe2-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="37fe2-595">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-595">Int64</span></span>|  
|<span data-ttu-id="37fe2-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="37fe2-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="37fe2-597">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-597">Int64</span></span>|  
|<span data-ttu-id="37fe2-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37fe2-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="37fe2-599">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-599">Int32</span></span>|  
|<span data-ttu-id="37fe2-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="37fe2-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="37fe2-601">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-601">Int16</span></span>|  
|<span data-ttu-id="37fe2-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="37fe2-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="37fe2-603">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-603">Int64</span></span>|  
|<span data-ttu-id="37fe2-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="37fe2-605">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-605">String</span></span>|  
|<span data-ttu-id="37fe2-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="37fe2-607">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-607">String</span></span>|  
|<span data-ttu-id="37fe2-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="37fe2-609">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-609">String</span></span>|  
|<span data-ttu-id="37fe2-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="37fe2-611">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-611">String</span></span>|  
|<span data-ttu-id="37fe2-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="37fe2-613">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-613">String</span></span>|  
|<span data-ttu-id="37fe2-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-614">COLLATION_NAME</span></span>|<span data-ttu-id="37fe2-615">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-615">String</span></span>|  
|<span data-ttu-id="37fe2-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="37fe2-617">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-617">String</span></span>|  
|<span data-ttu-id="37fe2-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="37fe2-619">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-619">String</span></span>|  
|<span data-ttu-id="37fe2-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-620">DOMAIN_NAME</span></span>|<span data-ttu-id="37fe2-621">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-621">String</span></span>|  
|<span data-ttu-id="37fe2-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-622">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-623">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="37fe2-624">过程</span><span class="sxs-lookup"><span data-stu-id="37fe2-624">Procedures</span></span>  
  
|<span data-ttu-id="37fe2-625">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-625">ColumnName</span></span>|<span data-ttu-id="37fe2-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="37fe2-628">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-628">String</span></span>|  
|<span data-ttu-id="37fe2-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="37fe2-630">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-630">String</span></span>|  
|<span data-ttu-id="37fe2-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="37fe2-632">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-632">String</span></span>|  
|<span data-ttu-id="37fe2-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="37fe2-634">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-634">Int16</span></span>|  
|<span data-ttu-id="37fe2-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="37fe2-636">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-636">String</span></span>|  
|<span data-ttu-id="37fe2-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-637">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-638">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-638">String</span></span>|  
|<span data-ttu-id="37fe2-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-639">DATE_CREATED</span></span>|<span data-ttu-id="37fe2-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-640">DateTime</span></span>|  
|<span data-ttu-id="37fe2-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37fe2-641">DATE_MODIFIED</span></span>|<span data-ttu-id="37fe2-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="37fe2-643">视图</span><span class="sxs-lookup"><span data-stu-id="37fe2-643">Views</span></span>  
  
|<span data-ttu-id="37fe2-644">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-644">ColumnName</span></span>|<span data-ttu-id="37fe2-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-646">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-647">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-647">String</span></span>|  
|<span data-ttu-id="37fe2-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-649">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-649">String</span></span>|  
|<span data-ttu-id="37fe2-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-650">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-651">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-651">String</span></span>|  
|<span data-ttu-id="37fe2-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="37fe2-653">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-653">String</span></span>|  
|<span data-ttu-id="37fe2-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-654">CHECK_OPTION</span></span>|<span data-ttu-id="37fe2-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-655">Boolean</span></span>|  
|<span data-ttu-id="37fe2-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="37fe2-656">IS_UPDATABLE</span></span>|<span data-ttu-id="37fe2-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-657">Boolean</span></span>|  
|<span data-ttu-id="37fe2-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37fe2-658">DESCRIPTION</span></span>|<span data-ttu-id="37fe2-659">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-659">String</span></span>|  
|<span data-ttu-id="37fe2-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-660">DATE_CREATED</span></span>|<span data-ttu-id="37fe2-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-661">DateTime</span></span>|  
|<span data-ttu-id="37fe2-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="37fe2-662">DATE_MODIFIED</span></span>|<span data-ttu-id="37fe2-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="37fe2-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="37fe2-664">索引</span><span class="sxs-lookup"><span data-stu-id="37fe2-664">Indexes</span></span>  
  
|<span data-ttu-id="37fe2-665">列名</span><span class="sxs-lookup"><span data-stu-id="37fe2-665">ColumnName</span></span>|<span data-ttu-id="37fe2-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="37fe2-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="37fe2-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-667">TABLE_CATALOG</span></span>|<span data-ttu-id="37fe2-668">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-668">String</span></span>|  
|<span data-ttu-id="37fe2-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="37fe2-670">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-670">String</span></span>|  
|<span data-ttu-id="37fe2-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-671">TABLE_NAME</span></span>|<span data-ttu-id="37fe2-672">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-672">String</span></span>|  
|<span data-ttu-id="37fe2-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="37fe2-673">INDEX_CATALOG</span></span>|<span data-ttu-id="37fe2-674">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-674">String</span></span>|  
|<span data-ttu-id="37fe2-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="37fe2-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="37fe2-676">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-676">String</span></span>|  
|<span data-ttu-id="37fe2-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-677">INDEX_NAME</span></span>|<span data-ttu-id="37fe2-678">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-678">String</span></span>|  
|<span data-ttu-id="37fe2-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="37fe2-679">PRIMARY_KEY</span></span>|<span data-ttu-id="37fe2-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-680">Boolean</span></span>|  
|<span data-ttu-id="37fe2-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="37fe2-681">UNIQUE</span></span>|<span data-ttu-id="37fe2-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-682">Boolean</span></span>|  
|<span data-ttu-id="37fe2-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="37fe2-683">CLUSTERED</span></span>|<span data-ttu-id="37fe2-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-684">Boolean</span></span>|  
|<span data-ttu-id="37fe2-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="37fe2-685">TYPE</span></span>|<span data-ttu-id="37fe2-686">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-686">Int32</span></span>|  
|<span data-ttu-id="37fe2-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="37fe2-687">FILL_FACTOR</span></span>|<span data-ttu-id="37fe2-688">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-688">Int32</span></span>|  
|<span data-ttu-id="37fe2-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="37fe2-689">INITIAL_SIZE</span></span>|<span data-ttu-id="37fe2-690">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-690">Int32</span></span>|  
|<span data-ttu-id="37fe2-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="37fe2-691">NULLS</span></span>|<span data-ttu-id="37fe2-692">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-692">Int32</span></span>|  
|<span data-ttu-id="37fe2-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="37fe2-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="37fe2-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-694">Boolean</span></span>|  
|<span data-ttu-id="37fe2-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="37fe2-695">AUTO_UPDATE</span></span>|<span data-ttu-id="37fe2-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-696">Boolean</span></span>|  
|<span data-ttu-id="37fe2-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="37fe2-697">NULL_COLLATION</span></span>|<span data-ttu-id="37fe2-698">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-698">Int32</span></span>|  
|<span data-ttu-id="37fe2-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="37fe2-700">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-700">Int64</span></span>|  
|<span data-ttu-id="37fe2-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="37fe2-701">COLUMN_NAME</span></span>|<span data-ttu-id="37fe2-702">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-702">String</span></span>|  
|<span data-ttu-id="37fe2-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="37fe2-703">COLUMN_GUID</span></span>|<span data-ttu-id="37fe2-704">Guid</span><span class="sxs-lookup"><span data-stu-id="37fe2-704">Guid</span></span>|  
|<span data-ttu-id="37fe2-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="37fe2-705">COLUMN_PROPID</span></span>|<span data-ttu-id="37fe2-706">Int64</span><span class="sxs-lookup"><span data-stu-id="37fe2-706">Int64</span></span>|  
|<span data-ttu-id="37fe2-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="37fe2-707">COLLATION</span></span>|<span data-ttu-id="37fe2-708">Int16</span><span class="sxs-lookup"><span data-stu-id="37fe2-708">Int16</span></span>|  
|<span data-ttu-id="37fe2-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="37fe2-709">CARDINALITY</span></span>|<span data-ttu-id="37fe2-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="37fe2-710">Decimal</span></span>|  
|<span data-ttu-id="37fe2-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="37fe2-711">PAGES</span></span>|<span data-ttu-id="37fe2-712">Int32</span><span class="sxs-lookup"><span data-stu-id="37fe2-712">Int32</span></span>|  
|<span data-ttu-id="37fe2-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="37fe2-713">FILTER_CONDITION</span></span>|<span data-ttu-id="37fe2-714">String</span><span class="sxs-lookup"><span data-stu-id="37fe2-714">String</span></span>|  
|<span data-ttu-id="37fe2-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="37fe2-715">INTEGRATED</span></span>|<span data-ttu-id="37fe2-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="37fe2-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37fe2-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="37fe2-717">See also</span></span>
- [<span data-ttu-id="37fe2-718">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="37fe2-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
