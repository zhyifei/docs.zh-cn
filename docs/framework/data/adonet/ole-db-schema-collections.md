---
title: OLE DB 架构集合
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783446"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="c3a8a-102">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="c3a8a-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="c3a8a-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 OLE DB 提供程序的架构集合支持</span><span class="sxs-lookup"><span data-stu-id="c3a8a-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="c3a8a-104">Microsoft SQL Server OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="c3a8a-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="c3a8a-105">除了通用架构集合之外，Microsoft SQL Server OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="c3a8a-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="c3a8a-106">表</span><span class="sxs-lookup"><span data-stu-id="c3a8a-106">Tables</span></span>  
  
- <span data-ttu-id="c3a8a-107">列</span><span class="sxs-lookup"><span data-stu-id="c3a8a-107">Columns</span></span>  
  
- <span data-ttu-id="c3a8a-108">过程</span><span class="sxs-lookup"><span data-stu-id="c3a8a-108">Procedures</span></span>  
  
- <span data-ttu-id="c3a8a-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c3a8a-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="c3a8a-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="c3a8a-110">Catalog</span></span>  
  
- <span data-ttu-id="c3a8a-111">索引</span><span class="sxs-lookup"><span data-stu-id="c3a8a-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="c3a8a-112">表</span><span class="sxs-lookup"><span data-stu-id="c3a8a-112">Tables</span></span>  
  
|<span data-ttu-id="c3a8a-113">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-113">ColumnName</span></span>|<span data-ttu-id="c3a8a-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-115">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-116">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-116">String</span></span>|  
|<span data-ttu-id="c3a8a-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-118">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-118">String</span></span>|  
|<span data-ttu-id="c3a8a-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-119">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-120">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-120">String</span></span>|  
|<span data-ttu-id="c3a8a-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-121">TABLE_TYPE</span></span>|<span data-ttu-id="c3a8a-122">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-122">String</span></span>|  
|<span data-ttu-id="c3a8a-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-123">TABLE_GUID</span></span>|<span data-ttu-id="c3a8a-124">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-124">Guid</span></span>|  
|<span data-ttu-id="c3a8a-125">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-125">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-126">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-126">String</span></span>|  
|<span data-ttu-id="c3a8a-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-127">TABLE_PROPID</span></span>|<span data-ttu-id="c3a8a-128">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-128">Int64</span></span>|  
|<span data-ttu-id="c3a8a-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-129">DATE_CREATED</span></span>|<span data-ttu-id="c3a8a-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-130">DateTime</span></span>|  
|<span data-ttu-id="c3a8a-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-131">DATE_MODIFIED</span></span>|<span data-ttu-id="c3a8a-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c3a8a-133">列</span><span class="sxs-lookup"><span data-stu-id="c3a8a-133">Columns</span></span>  
  
|<span data-ttu-id="c3a8a-134">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-134">ColumnName</span></span>|<span data-ttu-id="c3a8a-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-136">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-137">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-137">String</span></span>|  
|<span data-ttu-id="c3a8a-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-139">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-139">String</span></span>|  
|<span data-ttu-id="c3a8a-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-140">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-141">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-141">String</span></span>|  
|<span data-ttu-id="c3a8a-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-142">COLUMN_NAME</span></span>|<span data-ttu-id="c3a8a-143">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-143">String</span></span>|  
|<span data-ttu-id="c3a8a-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-144">COLUMN_GUID</span></span>|<span data-ttu-id="c3a8a-145">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-145">Guid</span></span>|  
|<span data-ttu-id="c3a8a-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-146">COLUMN_PROPID</span></span>|<span data-ttu-id="c3a8a-147">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-147">Int64</span></span>|  
|<span data-ttu-id="c3a8a-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="c3a8a-149">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-149">Int64</span></span>|  
|<span data-ttu-id="c3a8a-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="c3a8a-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="c3a8a-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-151">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c3a8a-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="c3a8a-153">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-153">String</span></span>|  
|<span data-ttu-id="c3a8a-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="c3a8a-155">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-155">Int64</span></span>|  
|<span data-ttu-id="c3a8a-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-156">IS_NULLABLE</span></span>|<span data-ttu-id="c3a8a-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-157">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-158">DATA_TYPE</span></span>|<span data-ttu-id="c3a8a-159">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-159">Int32</span></span>|  
|<span data-ttu-id="c3a8a-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-160">TYPE_GUID</span></span>|<span data-ttu-id="c3a8a-161">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-161">Guid</span></span>|  
|<span data-ttu-id="c3a8a-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c3a8a-163">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-163">Int64</span></span>|  
|<span data-ttu-id="c3a8a-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c3a8a-165">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-165">Int64</span></span>|  
|<span data-ttu-id="c3a8a-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c3a8a-167">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-167">Int32</span></span>|  
|<span data-ttu-id="c3a8a-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="c3a8a-169">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-169">Int16</span></span>|  
|<span data-ttu-id="c3a8a-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="c3a8a-171">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-171">Int64</span></span>|  
|<span data-ttu-id="c3a8a-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="c3a8a-173">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-173">String</span></span>|  
|<span data-ttu-id="c3a8a-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="c3a8a-175">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-175">String</span></span>|  
|<span data-ttu-id="c3a8a-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="c3a8a-177">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-177">String</span></span>|  
|<span data-ttu-id="c3a8a-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="c3a8a-179">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-179">String</span></span>|  
|<span data-ttu-id="c3a8a-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="c3a8a-181">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-181">String</span></span>|  
|<span data-ttu-id="c3a8a-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-182">COLLATION_NAME</span></span>|<span data-ttu-id="c3a8a-183">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-183">String</span></span>|  
|<span data-ttu-id="c3a8a-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="c3a8a-185">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-185">String</span></span>|  
|<span data-ttu-id="c3a8a-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="c3a8a-187">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-187">String</span></span>|  
|<span data-ttu-id="c3a8a-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-188">DOMAIN_NAME</span></span>|<span data-ttu-id="c3a8a-189">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-189">String</span></span>|  
|<span data-ttu-id="c3a8a-190">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-190">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-191">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-191">String</span></span>|  
|<span data-ttu-id="c3a8a-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-192">COLUMN_LCID</span></span>|<span data-ttu-id="c3a8a-193">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-193">Int32</span></span>|  
|<span data-ttu-id="c3a8a-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="c3a8a-195">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-195">Int32</span></span>|  
|<span data-ttu-id="c3a8a-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-196">COLUMN_SORTID</span></span>|<span data-ttu-id="c3a8a-197">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-197">Int32</span></span>|  
|<span data-ttu-id="c3a8a-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="c3a8a-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="c3a8a-199">Byte[]</span></span>|  
|<span data-ttu-id="c3a8a-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-200">IS_COMPUTED</span></span>|<span data-ttu-id="c3a8a-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c3a8a-202">过程</span><span class="sxs-lookup"><span data-stu-id="c3a8a-202">Procedures</span></span>  
  
|<span data-ttu-id="c3a8a-203">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-203">ColumnName</span></span>|<span data-ttu-id="c3a8a-204">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c3a8a-206">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-206">String</span></span>|  
|<span data-ttu-id="c3a8a-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-208">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-208">String</span></span>|  
|<span data-ttu-id="c3a8a-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="c3a8a-210">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-210">String</span></span>|  
|<span data-ttu-id="c3a8a-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c3a8a-212">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-212">Int16</span></span>|  
|<span data-ttu-id="c3a8a-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="c3a8a-214">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-214">String</span></span>|  
|<span data-ttu-id="c3a8a-215">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-215">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-216">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-216">String</span></span>|  
|<span data-ttu-id="c3a8a-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-217">DATE_CREATED</span></span>|<span data-ttu-id="c3a8a-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-218">DateTime</span></span>|  
|<span data-ttu-id="c3a8a-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-219">DATE_MODIFIED</span></span>|<span data-ttu-id="c3a8a-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="c3a8a-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c3a8a-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="c3a8a-222">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-222">ColumnName</span></span>|<span data-ttu-id="c3a8a-223">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c3a8a-225">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-225">String</span></span>|  
|<span data-ttu-id="c3a8a-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-227">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-227">String</span></span>|  
|<span data-ttu-id="c3a8a-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="c3a8a-229">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-229">String</span></span>|  
|<span data-ttu-id="c3a8a-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-230">PARAMETER_NAME</span></span>|<span data-ttu-id="c3a8a-231">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-231">String</span></span>|  
|<span data-ttu-id="c3a8a-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="c3a8a-233">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-233">Int32</span></span>|  
|<span data-ttu-id="c3a8a-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="c3a8a-235">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-235">Int32</span></span>|  
|<span data-ttu-id="c3a8a-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="c3a8a-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="c3a8a-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-237">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c3a8a-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="c3a8a-239">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-239">String</span></span>|  
|<span data-ttu-id="c3a8a-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-240">IS_NULLABLE</span></span>|<span data-ttu-id="c3a8a-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-241">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-242">DATA_TYPE</span></span>|<span data-ttu-id="c3a8a-243">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-243">Int32</span></span>|  
|<span data-ttu-id="c3a8a-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c3a8a-245">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-245">Int64</span></span>|  
|<span data-ttu-id="c3a8a-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c3a8a-247">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-247">Int64</span></span>|  
|<span data-ttu-id="c3a8a-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c3a8a-249">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-249">Int32</span></span>|  
|<span data-ttu-id="c3a8a-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="c3a8a-251">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-251">Int16</span></span>|  
|<span data-ttu-id="c3a8a-252">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-252">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-253">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-253">String</span></span>|  
|<span data-ttu-id="c3a8a-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-254">TYPE_NAME</span></span>|<span data-ttu-id="c3a8a-255">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-255">String</span></span>|  
|<span data-ttu-id="c3a8a-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="c3a8a-257">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="c3a8a-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="c3a8a-258">Catalog</span></span>  
  
|<span data-ttu-id="c3a8a-259">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-259">ColumnName</span></span>|<span data-ttu-id="c3a8a-260">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-261">CATALOG_NAME</span></span>|<span data-ttu-id="c3a8a-262">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-262">String</span></span>|  
|<span data-ttu-id="c3a8a-263">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-263">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-264">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="c3a8a-265">索引</span><span class="sxs-lookup"><span data-stu-id="c3a8a-265">Indexes</span></span>  
  
|<span data-ttu-id="c3a8a-266">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-266">ColumnName</span></span>|<span data-ttu-id="c3a8a-267">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-268">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-269">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-269">String</span></span>|  
|<span data-ttu-id="c3a8a-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-271">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-271">String</span></span>|  
|<span data-ttu-id="c3a8a-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-272">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-273">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-273">String</span></span>|  
|<span data-ttu-id="c3a8a-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-274">INDEX_CATALOG</span></span>|<span data-ttu-id="c3a8a-275">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-275">String</span></span>|  
|<span data-ttu-id="c3a8a-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="c3a8a-277">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-277">String</span></span>|  
|<span data-ttu-id="c3a8a-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-278">INDEX_NAME</span></span>|<span data-ttu-id="c3a8a-279">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-279">String</span></span>|  
|<span data-ttu-id="c3a8a-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="c3a8a-280">PRIMARY_KEY</span></span>|<span data-ttu-id="c3a8a-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-281">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-282">UNIQUE</span></span>|<span data-ttu-id="c3a8a-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-283">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-284">CLUSTERED</span></span>|<span data-ttu-id="c3a8a-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-285">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-286">TYPE</span></span>|<span data-ttu-id="c3a8a-287">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-287">Int32</span></span>|  
|<span data-ttu-id="c3a8a-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="c3a8a-288">FILL_FACTOR</span></span>|<span data-ttu-id="c3a8a-289">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-289">Int32</span></span>|  
|<span data-ttu-id="c3a8a-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-290">INITIAL_SIZE</span></span>|<span data-ttu-id="c3a8a-291">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-291">Int32</span></span>|  
|<span data-ttu-id="c3a8a-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-292">NULLS</span></span>|<span data-ttu-id="c3a8a-293">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-293">Int32</span></span>|  
|<span data-ttu-id="c3a8a-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="c3a8a-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-295">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-296">AUTO_UPDATE</span></span>|<span data-ttu-id="c3a8a-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-297">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-298">NULL_COLLATION</span></span>|<span data-ttu-id="c3a8a-299">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-299">Int32</span></span>|  
|<span data-ttu-id="c3a8a-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="c3a8a-301">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-301">Int64</span></span>|  
|<span data-ttu-id="c3a8a-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-302">COLUMN_NAME</span></span>|<span data-ttu-id="c3a8a-303">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-303">String</span></span>|  
|<span data-ttu-id="c3a8a-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-304">COLUMN_GUID</span></span>|<span data-ttu-id="c3a8a-305">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-305">Guid</span></span>|  
|<span data-ttu-id="c3a8a-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-306">COLUMN_PROPID</span></span>|<span data-ttu-id="c3a8a-307">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-307">Int64</span></span>|  
|<span data-ttu-id="c3a8a-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-308">COLLATION</span></span>|<span data-ttu-id="c3a8a-309">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-309">Int16</span></span>|  
|<span data-ttu-id="c3a8a-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="c3a8a-310">CARDINALITY</span></span>|<span data-ttu-id="c3a8a-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="c3a8a-311">Decimal</span></span>|  
|<span data-ttu-id="c3a8a-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="c3a8a-312">PAGES</span></span>|<span data-ttu-id="c3a8a-313">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-313">Int32</span></span>|  
|<span data-ttu-id="c3a8a-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-314">FILTER_CONDITION</span></span>|<span data-ttu-id="c3a8a-315">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-315">String</span></span>|  
|<span data-ttu-id="c3a8a-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-316">INTEGRATED</span></span>|<span data-ttu-id="c3a8a-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="c3a8a-318">Microsoft Oracle OLE DB 提供程序</span><span class="sxs-lookup"><span data-stu-id="c3a8a-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="c3a8a-319">除了通用架构集合之外，Microsoft Oracle OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="c3a8a-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="c3a8a-320">表</span><span class="sxs-lookup"><span data-stu-id="c3a8a-320">Tables</span></span>  
  
- <span data-ttu-id="c3a8a-321">列</span><span class="sxs-lookup"><span data-stu-id="c3a8a-321">Columns</span></span>  
  
- <span data-ttu-id="c3a8a-322">过程</span><span class="sxs-lookup"><span data-stu-id="c3a8a-322">Procedures</span></span>  
  
- <span data-ttu-id="c3a8a-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c3a8a-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="c3a8a-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c3a8a-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="c3a8a-325">Views</span><span class="sxs-lookup"><span data-stu-id="c3a8a-325">Views</span></span>  
  
- <span data-ttu-id="c3a8a-326">索引</span><span class="sxs-lookup"><span data-stu-id="c3a8a-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="c3a8a-327">表</span><span class="sxs-lookup"><span data-stu-id="c3a8a-327">Tables</span></span>  
  
|<span data-ttu-id="c3a8a-328">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-328">ColumnName</span></span>|<span data-ttu-id="c3a8a-329">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-330">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-331">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-331">String</span></span>|  
|<span data-ttu-id="c3a8a-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-333">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-333">String</span></span>|  
|<span data-ttu-id="c3a8a-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-334">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-335">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-335">String</span></span>|  
|<span data-ttu-id="c3a8a-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-336">TABLE_TYPE</span></span>|<span data-ttu-id="c3a8a-337">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-337">String</span></span>|  
|<span data-ttu-id="c3a8a-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-338">TABLE_GUID</span></span>|<span data-ttu-id="c3a8a-339">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-339">Guid</span></span>|  
|<span data-ttu-id="c3a8a-340">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-340">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-341">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-341">String</span></span>|  
|<span data-ttu-id="c3a8a-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-342">TABLE_PROPID</span></span>|<span data-ttu-id="c3a8a-343">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-343">Int64</span></span>|  
|<span data-ttu-id="c3a8a-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-344">DATE_CREATED</span></span>|<span data-ttu-id="c3a8a-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-345">DateTime</span></span>|  
|<span data-ttu-id="c3a8a-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-346">DATE_MODIFIED</span></span>|<span data-ttu-id="c3a8a-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c3a8a-348">列</span><span class="sxs-lookup"><span data-stu-id="c3a8a-348">Columns</span></span>  
  
|<span data-ttu-id="c3a8a-349">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-349">ColumnName</span></span>|<span data-ttu-id="c3a8a-350">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-351">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-352">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-352">String</span></span>|  
|<span data-ttu-id="c3a8a-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-354">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-354">String</span></span>|  
|<span data-ttu-id="c3a8a-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-355">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-356">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-356">String</span></span>|  
|<span data-ttu-id="c3a8a-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-357">COLUMN_NAME</span></span>|<span data-ttu-id="c3a8a-358">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-358">String</span></span>|  
|<span data-ttu-id="c3a8a-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-359">COLUMN_GUID</span></span>|<span data-ttu-id="c3a8a-360">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-360">Guid</span></span>|  
|<span data-ttu-id="c3a8a-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-361">COLUMN_PROPID</span></span>|<span data-ttu-id="c3a8a-362">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-362">Int64</span></span>|  
|<span data-ttu-id="c3a8a-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="c3a8a-364">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-364">Int64</span></span>|  
|<span data-ttu-id="c3a8a-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="c3a8a-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="c3a8a-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-366">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c3a8a-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="c3a8a-368">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-368">String</span></span>|  
|<span data-ttu-id="c3a8a-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="c3a8a-370">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-370">Int64</span></span>|  
|<span data-ttu-id="c3a8a-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-371">IS_NULLABLE</span></span>|<span data-ttu-id="c3a8a-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-372">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-373">DATA_TYPE</span></span>|<span data-ttu-id="c3a8a-374">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-374">Int32</span></span>|  
|<span data-ttu-id="c3a8a-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-375">TYPE_GUID</span></span>|<span data-ttu-id="c3a8a-376">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-376">Guid</span></span>|  
|<span data-ttu-id="c3a8a-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c3a8a-378">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-378">Int64</span></span>|  
|<span data-ttu-id="c3a8a-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c3a8a-380">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-380">Int64</span></span>|  
|<span data-ttu-id="c3a8a-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c3a8a-382">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-382">Int32</span></span>|  
|<span data-ttu-id="c3a8a-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="c3a8a-384">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-384">Int16</span></span>|  
|<span data-ttu-id="c3a8a-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="c3a8a-386">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-386">Int64</span></span>|  
|<span data-ttu-id="c3a8a-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="c3a8a-388">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-388">String</span></span>|  
|<span data-ttu-id="c3a8a-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="c3a8a-390">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-390">String</span></span>|  
|<span data-ttu-id="c3a8a-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="c3a8a-392">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-392">String</span></span>|  
|<span data-ttu-id="c3a8a-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="c3a8a-394">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-394">String</span></span>|  
|<span data-ttu-id="c3a8a-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="c3a8a-396">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-396">String</span></span>|  
|<span data-ttu-id="c3a8a-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-397">COLLATION_NAME</span></span>|<span data-ttu-id="c3a8a-398">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-398">String</span></span>|  
|<span data-ttu-id="c3a8a-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="c3a8a-400">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-400">String</span></span>|  
|<span data-ttu-id="c3a8a-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="c3a8a-402">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-402">String</span></span>|  
|<span data-ttu-id="c3a8a-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-403">DOMAIN_NAME</span></span>|<span data-ttu-id="c3a8a-404">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-404">String</span></span>|  
|<span data-ttu-id="c3a8a-405">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-405">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-406">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c3a8a-407">过程</span><span class="sxs-lookup"><span data-stu-id="c3a8a-407">Procedures</span></span>  
  
|<span data-ttu-id="c3a8a-408">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-408">ColumnName</span></span>|<span data-ttu-id="c3a8a-409">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c3a8a-411">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-411">String</span></span>|  
|<span data-ttu-id="c3a8a-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-413">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-413">String</span></span>|  
|<span data-ttu-id="c3a8a-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="c3a8a-415">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-415">String</span></span>|  
|<span data-ttu-id="c3a8a-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c3a8a-417">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-417">Int16</span></span>|  
|<span data-ttu-id="c3a8a-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="c3a8a-419">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-419">String</span></span>|  
|<span data-ttu-id="c3a8a-420">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-420">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-421">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-421">String</span></span>|  
|<span data-ttu-id="c3a8a-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-422">DATE_CREATED</span></span>|<span data-ttu-id="c3a8a-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-423">DateTime</span></span>|  
|<span data-ttu-id="c3a8a-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-424">DATE_MODIFIED</span></span>|<span data-ttu-id="c3a8a-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="c3a8a-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c3a8a-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="c3a8a-427">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-427">ColumnName</span></span>|<span data-ttu-id="c3a8a-428">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c3a8a-430">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-430">String</span></span>|  
|<span data-ttu-id="c3a8a-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-432">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-432">String</span></span>|  
|<span data-ttu-id="c3a8a-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="c3a8a-434">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-434">String</span></span>|  
|<span data-ttu-id="c3a8a-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-435">COLUMN_NAME</span></span>|<span data-ttu-id="c3a8a-436">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-436">String</span></span>|  
|<span data-ttu-id="c3a8a-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-437">COLUMN_GUID</span></span>|<span data-ttu-id="c3a8a-438">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-438">Guid</span></span>|  
|<span data-ttu-id="c3a8a-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-439">COLUMN_PROPID</span></span>|<span data-ttu-id="c3a8a-440">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-440">Int64</span></span>|  
|<span data-ttu-id="c3a8a-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="c3a8a-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="c3a8a-442">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-442">Int64</span></span>|  
|<span data-ttu-id="c3a8a-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="c3a8a-444">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-444">Int64</span></span>|  
|<span data-ttu-id="c3a8a-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-445">IS_NULLABLE</span></span>|<span data-ttu-id="c3a8a-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-446">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-447">DATA_TYPE</span></span>|<span data-ttu-id="c3a8a-448">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-448">Int32</span></span>|  
|<span data-ttu-id="c3a8a-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-449">TYPE_GUID</span></span>|<span data-ttu-id="c3a8a-450">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-450">Guid</span></span>|  
|<span data-ttu-id="c3a8a-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c3a8a-452">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-452">Int64</span></span>|  
|<span data-ttu-id="c3a8a-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c3a8a-454">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-454">Int64</span></span>|  
|<span data-ttu-id="c3a8a-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c3a8a-456">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-456">Int32</span></span>|  
|<span data-ttu-id="c3a8a-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="c3a8a-458">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-458">Int16</span></span>|  
|<span data-ttu-id="c3a8a-459">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-459">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-460">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-460">String</span></span>|  
|<span data-ttu-id="c3a8a-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="c3a8a-461">OVERLOAD</span></span>|<span data-ttu-id="c3a8a-462">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="c3a8a-463">Views</span><span class="sxs-lookup"><span data-stu-id="c3a8a-463">Views</span></span>  
  
|<span data-ttu-id="c3a8a-464">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-464">ColumnName</span></span>|<span data-ttu-id="c3a8a-465">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-466">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-467">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-467">String</span></span>|  
|<span data-ttu-id="c3a8a-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-469">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-469">String</span></span>|  
|<span data-ttu-id="c3a8a-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-470">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-471">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-471">String</span></span>|  
|<span data-ttu-id="c3a8a-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="c3a8a-473">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-473">String</span></span>|  
|<span data-ttu-id="c3a8a-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-474">CHECK_OPTION</span></span>|<span data-ttu-id="c3a8a-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-475">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-476">IS_UPDATABLE</span></span>|<span data-ttu-id="c3a8a-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-477">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-478">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-478">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-479">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-479">String</span></span>|  
|<span data-ttu-id="c3a8a-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-480">DATE_CREATED</span></span>|<span data-ttu-id="c3a8a-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-481">DateTime</span></span>|  
|<span data-ttu-id="c3a8a-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-482">DATE_MODIFIED</span></span>|<span data-ttu-id="c3a8a-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="c3a8a-484">索引</span><span class="sxs-lookup"><span data-stu-id="c3a8a-484">Indexes</span></span>  
  
|<span data-ttu-id="c3a8a-485">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-485">ColumnName</span></span>|<span data-ttu-id="c3a8a-486">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-487">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-488">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-488">String</span></span>|  
|<span data-ttu-id="c3a8a-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-490">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-490">String</span></span>|  
|<span data-ttu-id="c3a8a-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-491">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-492">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-492">String</span></span>|  
|<span data-ttu-id="c3a8a-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-493">INDEX_CATALOG</span></span>|<span data-ttu-id="c3a8a-494">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-494">String</span></span>|  
|<span data-ttu-id="c3a8a-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="c3a8a-496">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-496">String</span></span>|  
|<span data-ttu-id="c3a8a-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-497">INDEX_NAME</span></span>|<span data-ttu-id="c3a8a-498">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-498">String</span></span>|  
|<span data-ttu-id="c3a8a-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="c3a8a-499">PRIMARY_KEY</span></span>|<span data-ttu-id="c3a8a-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-500">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-501">UNIQUE</span></span>|<span data-ttu-id="c3a8a-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-502">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-503">CLUSTERED</span></span>|<span data-ttu-id="c3a8a-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-504">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-505">TYPE</span></span>|<span data-ttu-id="c3a8a-506">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-506">Int32</span></span>|  
|<span data-ttu-id="c3a8a-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="c3a8a-507">FILL_FACTOR</span></span>|<span data-ttu-id="c3a8a-508">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-508">Int32</span></span>|  
|<span data-ttu-id="c3a8a-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-509">INITIAL_SIZE</span></span>|<span data-ttu-id="c3a8a-510">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-510">Int32</span></span>|  
|<span data-ttu-id="c3a8a-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-511">NULLS</span></span>|<span data-ttu-id="c3a8a-512">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-512">Int32</span></span>|  
|<span data-ttu-id="c3a8a-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="c3a8a-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-514">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-515">AUTO_UPDATE</span></span>|<span data-ttu-id="c3a8a-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-516">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-517">NULL_COLLATION</span></span>|<span data-ttu-id="c3a8a-518">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-518">Int32</span></span>|  
|<span data-ttu-id="c3a8a-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="c3a8a-520">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-520">Int64</span></span>|  
|<span data-ttu-id="c3a8a-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-521">COLUMN_NAME</span></span>|<span data-ttu-id="c3a8a-522">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-522">String</span></span>|  
|<span data-ttu-id="c3a8a-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-523">COLUMN_GUID</span></span>|<span data-ttu-id="c3a8a-524">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-524">Guid</span></span>|  
|<span data-ttu-id="c3a8a-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-525">COLUMN_PROPID</span></span>|<span data-ttu-id="c3a8a-526">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-526">Int64</span></span>|  
|<span data-ttu-id="c3a8a-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-527">COLLATION</span></span>|<span data-ttu-id="c3a8a-528">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-528">Int16</span></span>|  
|<span data-ttu-id="c3a8a-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="c3a8a-529">CARDINALITY</span></span>|<span data-ttu-id="c3a8a-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="c3a8a-530">Decimal</span></span>|  
|<span data-ttu-id="c3a8a-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="c3a8a-531">PAGES</span></span>|<span data-ttu-id="c3a8a-532">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-532">Int32</span></span>|  
|<span data-ttu-id="c3a8a-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-533">FILTER_CONDITION</span></span>|<span data-ttu-id="c3a8a-534">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-534">String</span></span>|  
|<span data-ttu-id="c3a8a-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-535">INTEGRATED</span></span>|<span data-ttu-id="c3a8a-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="c3a8a-537">Microsoft Jet OLE DB</span><span class="sxs-lookup"><span data-stu-id="c3a8a-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="c3a8a-538">除了通用架构集合之外，Microsoft Jet OLE DB 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="c3a8a-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="c3a8a-539">表</span><span class="sxs-lookup"><span data-stu-id="c3a8a-539">Tables</span></span>  
  
- <span data-ttu-id="c3a8a-540">列</span><span class="sxs-lookup"><span data-stu-id="c3a8a-540">Columns</span></span>  
  
- <span data-ttu-id="c3a8a-541">过程</span><span class="sxs-lookup"><span data-stu-id="c3a8a-541">Procedures</span></span>  
  
- <span data-ttu-id="c3a8a-542">Views</span><span class="sxs-lookup"><span data-stu-id="c3a8a-542">Views</span></span>  
  
- <span data-ttu-id="c3a8a-543">索引</span><span class="sxs-lookup"><span data-stu-id="c3a8a-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="c3a8a-544">表</span><span class="sxs-lookup"><span data-stu-id="c3a8a-544">Tables</span></span>  
  
|<span data-ttu-id="c3a8a-545">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-545">ColumnName</span></span>|<span data-ttu-id="c3a8a-546">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-547">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-548">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-548">String</span></span>|  
|<span data-ttu-id="c3a8a-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-550">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-550">String</span></span>|  
|<span data-ttu-id="c3a8a-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-551">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-552">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-552">String</span></span>|  
|<span data-ttu-id="c3a8a-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-553">TABLE_TYPE</span></span>|<span data-ttu-id="c3a8a-554">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-554">String</span></span>|  
|<span data-ttu-id="c3a8a-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-555">TABLE_GUID</span></span>|<span data-ttu-id="c3a8a-556">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-556">Guid</span></span>|  
|<span data-ttu-id="c3a8a-557">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-557">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-558">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-558">String</span></span>|  
|<span data-ttu-id="c3a8a-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-559">TABLE_PROPID</span></span>|<span data-ttu-id="c3a8a-560">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-560">Int64</span></span>|  
|<span data-ttu-id="c3a8a-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-561">DATE_CREATED</span></span>|<span data-ttu-id="c3a8a-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-562">DateTime</span></span>|  
|<span data-ttu-id="c3a8a-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-563">DATE_MODIFIED</span></span>|<span data-ttu-id="c3a8a-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c3a8a-565">列</span><span class="sxs-lookup"><span data-stu-id="c3a8a-565">Columns</span></span>  
  
|<span data-ttu-id="c3a8a-566">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-566">ColumnName</span></span>|<span data-ttu-id="c3a8a-567">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-568">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-569">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-569">String</span></span>|  
|<span data-ttu-id="c3a8a-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-571">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-571">String</span></span>|  
|<span data-ttu-id="c3a8a-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-572">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-573">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-573">String</span></span>|  
|<span data-ttu-id="c3a8a-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-574">COLUMN_NAME</span></span>|<span data-ttu-id="c3a8a-575">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-575">String</span></span>|  
|<span data-ttu-id="c3a8a-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-576">COLUMN_GUID</span></span>|<span data-ttu-id="c3a8a-577">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-577">Guid</span></span>|  
|<span data-ttu-id="c3a8a-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-578">COLUMN_PROPID</span></span>|<span data-ttu-id="c3a8a-579">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-579">Int64</span></span>|  
|<span data-ttu-id="c3a8a-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="c3a8a-581">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-581">Int64</span></span>|  
|<span data-ttu-id="c3a8a-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="c3a8a-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="c3a8a-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-583">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c3a8a-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="c3a8a-585">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-585">String</span></span>|  
|<span data-ttu-id="c3a8a-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="c3a8a-587">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-587">Int64</span></span>|  
|<span data-ttu-id="c3a8a-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-588">IS_NULLABLE</span></span>|<span data-ttu-id="c3a8a-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-589">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-590">DATA_TYPE</span></span>|<span data-ttu-id="c3a8a-591">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-591">Int32</span></span>|  
|<span data-ttu-id="c3a8a-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-592">TYPE_GUID</span></span>|<span data-ttu-id="c3a8a-593">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-593">Guid</span></span>|  
|<span data-ttu-id="c3a8a-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="c3a8a-595">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-595">Int64</span></span>|  
|<span data-ttu-id="c3a8a-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c3a8a-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="c3a8a-597">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-597">Int64</span></span>|  
|<span data-ttu-id="c3a8a-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="c3a8a-599">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-599">Int32</span></span>|  
|<span data-ttu-id="c3a8a-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="c3a8a-601">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-601">Int16</span></span>|  
|<span data-ttu-id="c3a8a-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="c3a8a-603">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-603">Int64</span></span>|  
|<span data-ttu-id="c3a8a-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="c3a8a-605">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-605">String</span></span>|  
|<span data-ttu-id="c3a8a-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="c3a8a-607">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-607">String</span></span>|  
|<span data-ttu-id="c3a8a-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="c3a8a-609">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-609">String</span></span>|  
|<span data-ttu-id="c3a8a-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="c3a8a-611">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-611">String</span></span>|  
|<span data-ttu-id="c3a8a-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="c3a8a-613">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-613">String</span></span>|  
|<span data-ttu-id="c3a8a-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-614">COLLATION_NAME</span></span>|<span data-ttu-id="c3a8a-615">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-615">String</span></span>|  
|<span data-ttu-id="c3a8a-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="c3a8a-617">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-617">String</span></span>|  
|<span data-ttu-id="c3a8a-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="c3a8a-619">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-619">String</span></span>|  
|<span data-ttu-id="c3a8a-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-620">DOMAIN_NAME</span></span>|<span data-ttu-id="c3a8a-621">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-621">String</span></span>|  
|<span data-ttu-id="c3a8a-622">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-622">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-623">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c3a8a-624">过程</span><span class="sxs-lookup"><span data-stu-id="c3a8a-624">Procedures</span></span>  
  
|<span data-ttu-id="c3a8a-625">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-625">ColumnName</span></span>|<span data-ttu-id="c3a8a-626">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="c3a8a-628">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-628">String</span></span>|  
|<span data-ttu-id="c3a8a-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-630">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-630">String</span></span>|  
|<span data-ttu-id="c3a8a-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="c3a8a-632">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-632">String</span></span>|  
|<span data-ttu-id="c3a8a-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c3a8a-634">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-634">Int16</span></span>|  
|<span data-ttu-id="c3a8a-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="c3a8a-636">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-636">String</span></span>|  
|<span data-ttu-id="c3a8a-637">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-637">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-638">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-638">String</span></span>|  
|<span data-ttu-id="c3a8a-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-639">DATE_CREATED</span></span>|<span data-ttu-id="c3a8a-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-640">DateTime</span></span>|  
|<span data-ttu-id="c3a8a-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-641">DATE_MODIFIED</span></span>|<span data-ttu-id="c3a8a-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="c3a8a-643">Views</span><span class="sxs-lookup"><span data-stu-id="c3a8a-643">Views</span></span>  
  
|<span data-ttu-id="c3a8a-644">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-644">ColumnName</span></span>|<span data-ttu-id="c3a8a-645">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-646">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-647">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-647">String</span></span>|  
|<span data-ttu-id="c3a8a-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-649">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-649">String</span></span>|  
|<span data-ttu-id="c3a8a-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-650">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-651">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-651">String</span></span>|  
|<span data-ttu-id="c3a8a-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="c3a8a-653">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-653">String</span></span>|  
|<span data-ttu-id="c3a8a-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-654">CHECK_OPTION</span></span>|<span data-ttu-id="c3a8a-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-655">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-656">IS_UPDATABLE</span></span>|<span data-ttu-id="c3a8a-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-657">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-658">描述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-658">DESCRIPTION</span></span>|<span data-ttu-id="c3a8a-659">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-659">String</span></span>|  
|<span data-ttu-id="c3a8a-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-660">DATE_CREATED</span></span>|<span data-ttu-id="c3a8a-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-661">DateTime</span></span>|  
|<span data-ttu-id="c3a8a-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-662">DATE_MODIFIED</span></span>|<span data-ttu-id="c3a8a-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="c3a8a-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="c3a8a-664">索引</span><span class="sxs-lookup"><span data-stu-id="c3a8a-664">Indexes</span></span>  
  
|<span data-ttu-id="c3a8a-665">列名</span><span class="sxs-lookup"><span data-stu-id="c3a8a-665">ColumnName</span></span>|<span data-ttu-id="c3a8a-666">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3a8a-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c3a8a-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-667">TABLE_CATALOG</span></span>|<span data-ttu-id="c3a8a-668">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-668">String</span></span>|  
|<span data-ttu-id="c3a8a-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="c3a8a-670">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-670">String</span></span>|  
|<span data-ttu-id="c3a8a-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-671">TABLE_NAME</span></span>|<span data-ttu-id="c3a8a-672">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-672">String</span></span>|  
|<span data-ttu-id="c3a8a-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c3a8a-673">INDEX_CATALOG</span></span>|<span data-ttu-id="c3a8a-674">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-674">String</span></span>|  
|<span data-ttu-id="c3a8a-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c3a8a-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="c3a8a-676">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-676">String</span></span>|  
|<span data-ttu-id="c3a8a-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-677">INDEX_NAME</span></span>|<span data-ttu-id="c3a8a-678">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-678">String</span></span>|  
|<span data-ttu-id="c3a8a-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="c3a8a-679">PRIMARY_KEY</span></span>|<span data-ttu-id="c3a8a-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-680">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-681">UNIQUE</span></span>|<span data-ttu-id="c3a8a-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-682">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-683">CLUSTERED</span></span>|<span data-ttu-id="c3a8a-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-684">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-685">TYPE</span></span>|<span data-ttu-id="c3a8a-686">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-686">Int32</span></span>|  
|<span data-ttu-id="c3a8a-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="c3a8a-687">FILL_FACTOR</span></span>|<span data-ttu-id="c3a8a-688">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-688">Int32</span></span>|  
|<span data-ttu-id="c3a8a-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-689">INITIAL_SIZE</span></span>|<span data-ttu-id="c3a8a-690">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-690">Int32</span></span>|  
|<span data-ttu-id="c3a8a-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-691">NULLS</span></span>|<span data-ttu-id="c3a8a-692">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-692">Int32</span></span>|  
|<span data-ttu-id="c3a8a-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="c3a8a-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="c3a8a-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-694">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="c3a8a-695">AUTO_UPDATE</span></span>|<span data-ttu-id="c3a8a-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-696">Boolean</span></span>|  
|<span data-ttu-id="c3a8a-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-697">NULL_COLLATION</span></span>|<span data-ttu-id="c3a8a-698">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-698">Int32</span></span>|  
|<span data-ttu-id="c3a8a-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="c3a8a-700">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-700">Int64</span></span>|  
|<span data-ttu-id="c3a8a-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c3a8a-701">COLUMN_NAME</span></span>|<span data-ttu-id="c3a8a-702">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-702">String</span></span>|  
|<span data-ttu-id="c3a8a-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-703">COLUMN_GUID</span></span>|<span data-ttu-id="c3a8a-704">Guid</span><span class="sxs-lookup"><span data-stu-id="c3a8a-704">Guid</span></span>|  
|<span data-ttu-id="c3a8a-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="c3a8a-705">COLUMN_PROPID</span></span>|<span data-ttu-id="c3a8a-706">Int64</span><span class="sxs-lookup"><span data-stu-id="c3a8a-706">Int64</span></span>|  
|<span data-ttu-id="c3a8a-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-707">COLLATION</span></span>|<span data-ttu-id="c3a8a-708">Int16</span><span class="sxs-lookup"><span data-stu-id="c3a8a-708">Int16</span></span>|  
|<span data-ttu-id="c3a8a-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="c3a8a-709">CARDINALITY</span></span>|<span data-ttu-id="c3a8a-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="c3a8a-710">Decimal</span></span>|  
|<span data-ttu-id="c3a8a-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="c3a8a-711">PAGES</span></span>|<span data-ttu-id="c3a8a-712">Int32</span><span class="sxs-lookup"><span data-stu-id="c3a8a-712">Int32</span></span>|  
|<span data-ttu-id="c3a8a-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="c3a8a-713">FILTER_CONDITION</span></span>|<span data-ttu-id="c3a8a-714">String</span><span class="sxs-lookup"><span data-stu-id="c3a8a-714">String</span></span>|  
|<span data-ttu-id="c3a8a-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="c3a8a-715">INTEGRATED</span></span>|<span data-ttu-id="c3a8a-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="c3a8a-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3a8a-717">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3a8a-717">See also</span></span>

- [<span data-ttu-id="c3a8a-718">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="c3a8a-718">ADO.NET Overview</span></span>](ado-net-overview.md)
