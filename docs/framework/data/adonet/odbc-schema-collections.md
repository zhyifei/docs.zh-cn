---
title: ODBC 架构集合
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 36d0859b897bfcea33803c219ade14722ed90421
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="e414e-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="e414e-102">ODBC Schema Collections</span></span>
<span data-ttu-id="e414e-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="e414e-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="e414e-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="e414e-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="e414e-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="e414e-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e414e-106">表</span><span class="sxs-lookup"><span data-stu-id="e414e-106">Tables</span></span>  
  
-   <span data-ttu-id="e414e-107">索引</span><span class="sxs-lookup"><span data-stu-id="e414e-107">Indexes</span></span>  
  
-   <span data-ttu-id="e414e-108">Columns</span><span class="sxs-lookup"><span data-stu-id="e414e-108">Columns</span></span>  
  
-   <span data-ttu-id="e414e-109">过程</span><span class="sxs-lookup"><span data-stu-id="e414e-109">Procedures</span></span>  
  
-   <span data-ttu-id="e414e-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e414e-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e414e-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e414e-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e414e-112">视图</span><span class="sxs-lookup"><span data-stu-id="e414e-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="e414e-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="e414e-113">Tables and Views</span></span>  
  
|<span data-ttu-id="e414e-114">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-114">ColumnName</span></span>|<span data-ttu-id="e414e-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e414e-116">TABLE_CAT</span></span>|<span data-ttu-id="e414e-117">String</span><span class="sxs-lookup"><span data-stu-id="e414e-117">String</span></span>|  
|<span data-ttu-id="e414e-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e414e-118">TABLE_SCHEM</span></span>|<span data-ttu-id="e414e-119">String</span><span class="sxs-lookup"><span data-stu-id="e414e-119">String</span></span>|  
|<span data-ttu-id="e414e-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-120">TABLE_NAME</span></span>|<span data-ttu-id="e414e-121">String</span><span class="sxs-lookup"><span data-stu-id="e414e-121">String</span></span>|  
|<span data-ttu-id="e414e-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-122">TABLE_TYPE</span></span>|<span data-ttu-id="e414e-123">String</span><span class="sxs-lookup"><span data-stu-id="e414e-123">String</span></span>|  
|<span data-ttu-id="e414e-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-124">REMARKS</span></span>|<span data-ttu-id="e414e-125">String</span><span class="sxs-lookup"><span data-stu-id="e414e-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e414e-126">索引</span><span class="sxs-lookup"><span data-stu-id="e414e-126">Indexes</span></span>  
  
|<span data-ttu-id="e414e-127">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-127">ColumnName</span></span>|<span data-ttu-id="e414e-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e414e-129">TABLE_CAT</span></span>|<span data-ttu-id="e414e-130">String</span><span class="sxs-lookup"><span data-stu-id="e414e-130">String</span></span>|  
|<span data-ttu-id="e414e-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e414e-131">TABLE_SCHEM</span></span>|<span data-ttu-id="e414e-132">String</span><span class="sxs-lookup"><span data-stu-id="e414e-132">String</span></span>|  
|<span data-ttu-id="e414e-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-133">TABLE_NAME</span></span>|<span data-ttu-id="e414e-134">String</span><span class="sxs-lookup"><span data-stu-id="e414e-134">String</span></span>|  
|<span data-ttu-id="e414e-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e414e-135">NON_UNIQUE</span></span>|<span data-ttu-id="e414e-136">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-136">Int16</span></span>|  
|<span data-ttu-id="e414e-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e414e-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="e414e-138">String</span><span class="sxs-lookup"><span data-stu-id="e414e-138">String</span></span>|  
|<span data-ttu-id="e414e-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-139">INDEX_NAME</span></span>|<span data-ttu-id="e414e-140">String</span><span class="sxs-lookup"><span data-stu-id="e414e-140">String</span></span>|  
|<span data-ttu-id="e414e-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-141">TYPE</span></span>|<span data-ttu-id="e414e-142">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-142">Int16</span></span>|  
|<span data-ttu-id="e414e-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e414e-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="e414e-144">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-144">Int16</span></span>|  
|<span data-ttu-id="e414e-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-145">COLUMN_NAME</span></span>|<span data-ttu-id="e414e-146">String</span><span class="sxs-lookup"><span data-stu-id="e414e-146">String</span></span>|  
|<span data-ttu-id="e414e-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="e414e-147">ASC_OR_DESC</span></span>|<span data-ttu-id="e414e-148">String</span><span class="sxs-lookup"><span data-stu-id="e414e-148">String</span></span>|  
|<span data-ttu-id="e414e-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="e414e-149">CARDINATLITY</span></span>|<span data-ttu-id="e414e-150">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-150">Int32</span></span>|  
|<span data-ttu-id="e414e-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="e414e-151">PAGES</span></span>|<span data-ttu-id="e414e-152">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-152">Int32</span></span>|  
|<span data-ttu-id="e414e-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e414e-153">FILTER_CONDITION</span></span>|<span data-ttu-id="e414e-154">String</span><span class="sxs-lookup"><span data-stu-id="e414e-154">String</span></span>|  
|<span data-ttu-id="e414e-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e414e-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e414e-156">String</span><span class="sxs-lookup"><span data-stu-id="e414e-156">String</span></span>|  
|<span data-ttu-id="e414e-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="e414e-158">Byte</span><span class="sxs-lookup"><span data-stu-id="e414e-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e414e-159">Columns</span><span class="sxs-lookup"><span data-stu-id="e414e-159">Columns</span></span>  
  
|<span data-ttu-id="e414e-160">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-160">ColumnName</span></span>|<span data-ttu-id="e414e-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="e414e-162">TABLE_CAT</span></span>|<span data-ttu-id="e414e-163">String</span><span class="sxs-lookup"><span data-stu-id="e414e-163">String</span></span>|  
|<span data-ttu-id="e414e-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e414e-164">TABLE_SCHEM</span></span>|<span data-ttu-id="e414e-165">String</span><span class="sxs-lookup"><span data-stu-id="e414e-165">String</span></span>|  
|<span data-ttu-id="e414e-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-166">TABLE_NAME</span></span>|<span data-ttu-id="e414e-167">String</span><span class="sxs-lookup"><span data-stu-id="e414e-167">String</span></span>|  
|<span data-ttu-id="e414e-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-168">COLUMN_NAME</span></span>|<span data-ttu-id="e414e-169">String</span><span class="sxs-lookup"><span data-stu-id="e414e-169">String</span></span>|  
|<span data-ttu-id="e414e-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-170">DATA_TYPE</span></span>|<span data-ttu-id="e414e-171">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-171">Int16</span></span>|  
|<span data-ttu-id="e414e-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-172">TYPE_NAME</span></span>|<span data-ttu-id="e414e-173">String</span><span class="sxs-lookup"><span data-stu-id="e414e-173">String</span></span>|  
|<span data-ttu-id="e414e-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e414e-174">COLUMN_SIZE</span></span>|<span data-ttu-id="e414e-175">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-175">Int32</span></span>|  
|<span data-ttu-id="e414e-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="e414e-177">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-177">Int32</span></span>|  
|<span data-ttu-id="e414e-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e414e-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e414e-179">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-179">Int16</span></span>|  
|<span data-ttu-id="e414e-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e414e-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e414e-181">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-181">Int16</span></span>|  
|<span data-ttu-id="e414e-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-182">NULLABLE</span></span>|<span data-ttu-id="e414e-183">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-183">Int16</span></span>|  
|<span data-ttu-id="e414e-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-184">REMARKS</span></span>|<span data-ttu-id="e414e-185">String</span><span class="sxs-lookup"><span data-stu-id="e414e-185">String</span></span>|  
|<span data-ttu-id="e414e-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e414e-186">COLUMN_DEF</span></span>|<span data-ttu-id="e414e-187">String</span><span class="sxs-lookup"><span data-stu-id="e414e-187">String</span></span>|  
|<span data-ttu-id="e414e-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e414e-189">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-189">Int16</span></span>|  
|<span data-ttu-id="e414e-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e414e-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e414e-191">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-191">Int16</span></span>|  
|<span data-ttu-id="e414e-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e414e-193">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-193">Int32</span></span>|  
|<span data-ttu-id="e414e-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e414e-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="e414e-195">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-195">Int32</span></span>|  
|<span data-ttu-id="e414e-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-196">IS_NULLABLE</span></span>|<span data-ttu-id="e414e-197">String</span><span class="sxs-lookup"><span data-stu-id="e414e-197">String</span></span>|  
|<span data-ttu-id="e414e-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e414e-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e414e-199">String</span><span class="sxs-lookup"><span data-stu-id="e414e-199">String</span></span>|  
|<span data-ttu-id="e414e-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e414e-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e414e-201">String</span><span class="sxs-lookup"><span data-stu-id="e414e-201">String</span></span>|  
|<span data-ttu-id="e414e-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="e414e-203">Byte</span><span class="sxs-lookup"><span data-stu-id="e414e-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e414e-204">过程</span><span class="sxs-lookup"><span data-stu-id="e414e-204">Procedures</span></span>  
  
|<span data-ttu-id="e414e-205">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-205">ColumnName</span></span>|<span data-ttu-id="e414e-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e414e-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="e414e-208">String</span><span class="sxs-lookup"><span data-stu-id="e414e-208">String</span></span>|  
|<span data-ttu-id="e414e-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e414e-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e414e-210">String</span><span class="sxs-lookup"><span data-stu-id="e414e-210">String</span></span>|  
|<span data-ttu-id="e414e-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="e414e-212">String</span><span class="sxs-lookup"><span data-stu-id="e414e-212">String</span></span>|  
|<span data-ttu-id="e414e-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e414e-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e414e-214">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-214">Int32</span></span>|  
|<span data-ttu-id="e414e-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e414e-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e414e-216">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-216">Int32</span></span>|  
|<span data-ttu-id="e414e-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e414e-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e414e-218">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-218">Int32</span></span>|  
|<span data-ttu-id="e414e-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-219">REMARKS</span></span>|<span data-ttu-id="e414e-220">String</span><span class="sxs-lookup"><span data-stu-id="e414e-220">String</span></span>|  
|<span data-ttu-id="e414e-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e414e-222">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e414e-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e414e-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e414e-224">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-224">ColumnName</span></span>|<span data-ttu-id="e414e-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e414e-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="e414e-227">String</span><span class="sxs-lookup"><span data-stu-id="e414e-227">String</span></span>|  
|<span data-ttu-id="e414e-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e414e-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e414e-229">String</span><span class="sxs-lookup"><span data-stu-id="e414e-229">String</span></span>|  
|<span data-ttu-id="e414e-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="e414e-231">String</span><span class="sxs-lookup"><span data-stu-id="e414e-231">String</span></span>|  
|<span data-ttu-id="e414e-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-232">COLUMN_NAME</span></span>|<span data-ttu-id="e414e-233">String</span><span class="sxs-lookup"><span data-stu-id="e414e-233">String</span></span>|  
|<span data-ttu-id="e414e-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-234">COLUMN_TYPE</span></span>|<span data-ttu-id="e414e-235">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-235">Int16</span></span>|  
|<span data-ttu-id="e414e-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-236">DATA_TYPE</span></span>|<span data-ttu-id="e414e-237">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-237">Int16</span></span>|  
|<span data-ttu-id="e414e-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-238">TYPE_NAME</span></span>|<span data-ttu-id="e414e-239">String</span><span class="sxs-lookup"><span data-stu-id="e414e-239">String</span></span>|  
|<span data-ttu-id="e414e-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e414e-240">COLUMN_SIZE</span></span>|<span data-ttu-id="e414e-241">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-241">Int32</span></span>|  
|<span data-ttu-id="e414e-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="e414e-243">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-243">Int32</span></span>|  
|<span data-ttu-id="e414e-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e414e-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e414e-245">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-245">Int16</span></span>|  
|<span data-ttu-id="e414e-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e414e-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e414e-247">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-247">Int16</span></span>|  
|<span data-ttu-id="e414e-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-248">NULLABLE</span></span>|<span data-ttu-id="e414e-249">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-249">Int16</span></span>|  
|<span data-ttu-id="e414e-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-250">REMARKS</span></span>|<span data-ttu-id="e414e-251">String</span><span class="sxs-lookup"><span data-stu-id="e414e-251">String</span></span>|  
|<span data-ttu-id="e414e-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e414e-252">COLUMN_DEF</span></span>|<span data-ttu-id="e414e-253">String</span><span class="sxs-lookup"><span data-stu-id="e414e-253">String</span></span>|  
|<span data-ttu-id="e414e-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e414e-255">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-255">Int16</span></span>|  
|<span data-ttu-id="e414e-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e414e-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e414e-257">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-257">Int16</span></span>|  
|<span data-ttu-id="e414e-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e414e-259">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-259">Int32</span></span>|  
|<span data-ttu-id="e414e-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e414e-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="e414e-261">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-261">Int32</span></span>|  
|<span data-ttu-id="e414e-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-262">IS_NULLABLE</span></span>|<span data-ttu-id="e414e-263">String</span><span class="sxs-lookup"><span data-stu-id="e414e-263">String</span></span>|  
|<span data-ttu-id="e414e-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e414e-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e414e-265">String</span><span class="sxs-lookup"><span data-stu-id="e414e-265">String</span></span>|  
|<span data-ttu-id="e414e-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e414e-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e414e-267">String</span><span class="sxs-lookup"><span data-stu-id="e414e-267">String</span></span>|  
|<span data-ttu-id="e414e-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="e414e-269">Byte</span><span class="sxs-lookup"><span data-stu-id="e414e-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e414e-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e414e-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e414e-271">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-271">ColumnName</span></span>|<span data-ttu-id="e414e-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e414e-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="e414e-274">String</span><span class="sxs-lookup"><span data-stu-id="e414e-274">String</span></span>|  
|<span data-ttu-id="e414e-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e414e-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e414e-276">String</span><span class="sxs-lookup"><span data-stu-id="e414e-276">String</span></span>|  
|<span data-ttu-id="e414e-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="e414e-278">String</span><span class="sxs-lookup"><span data-stu-id="e414e-278">String</span></span>|  
|<span data-ttu-id="e414e-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-279">COLUMN_NAME</span></span>|<span data-ttu-id="e414e-280">String</span><span class="sxs-lookup"><span data-stu-id="e414e-280">String</span></span>|  
|<span data-ttu-id="e414e-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-281">COLUMN_TYPE</span></span>|<span data-ttu-id="e414e-282">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-282">Int16</span></span>|  
|<span data-ttu-id="e414e-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-283">DATA_TYPE</span></span>|<span data-ttu-id="e414e-284">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-284">Int16</span></span>|  
|<span data-ttu-id="e414e-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-285">TYPE_NAME</span></span>|<span data-ttu-id="e414e-286">String</span><span class="sxs-lookup"><span data-stu-id="e414e-286">String</span></span>|  
|<span data-ttu-id="e414e-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e414e-287">COLUMN_SIZE</span></span>|<span data-ttu-id="e414e-288">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-288">Int32</span></span>|  
|<span data-ttu-id="e414e-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="e414e-290">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-290">Int32</span></span>|  
|<span data-ttu-id="e414e-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e414e-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e414e-292">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-292">Int16</span></span>|  
|<span data-ttu-id="e414e-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e414e-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e414e-294">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-294">Int16</span></span>|  
|<span data-ttu-id="e414e-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-295">NULLABLE</span></span>|<span data-ttu-id="e414e-296">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-296">Int16</span></span>|  
|<span data-ttu-id="e414e-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-297">REMARKS</span></span>|<span data-ttu-id="e414e-298">String</span><span class="sxs-lookup"><span data-stu-id="e414e-298">String</span></span>|  
|<span data-ttu-id="e414e-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e414e-299">COLUMN_DEF</span></span>|<span data-ttu-id="e414e-300">String</span><span class="sxs-lookup"><span data-stu-id="e414e-300">String</span></span>|  
|<span data-ttu-id="e414e-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e414e-302">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-302">Int16</span></span>|  
|<span data-ttu-id="e414e-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e414e-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e414e-304">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-304">Int16</span></span>|  
|<span data-ttu-id="e414e-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e414e-306">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-306">Int32</span></span>|  
|<span data-ttu-id="e414e-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e414e-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="e414e-308">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-308">Int32</span></span>|  
|<span data-ttu-id="e414e-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-309">IS_NULLABLE</span></span>|<span data-ttu-id="e414e-310">String</span><span class="sxs-lookup"><span data-stu-id="e414e-310">String</span></span>|  
|<span data-ttu-id="e414e-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e414e-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="e414e-312">String</span><span class="sxs-lookup"><span data-stu-id="e414e-312">String</span></span>|  
|<span data-ttu-id="e414e-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e414e-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="e414e-314">String</span><span class="sxs-lookup"><span data-stu-id="e414e-314">String</span></span>|  
|<span data-ttu-id="e414e-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="e414e-316">Byte</span><span class="sxs-lookup"><span data-stu-id="e414e-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="e414e-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="e414e-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="e414e-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="e414e-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e414e-319">表</span><span class="sxs-lookup"><span data-stu-id="e414e-319">Tables</span></span>  
  
-   <span data-ttu-id="e414e-320">Columns</span><span class="sxs-lookup"><span data-stu-id="e414e-320">Columns</span></span>  
  
-   <span data-ttu-id="e414e-321">过程</span><span class="sxs-lookup"><span data-stu-id="e414e-321">Procedures</span></span>  
  
-   <span data-ttu-id="e414e-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e414e-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e414e-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e414e-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e414e-324">视图</span><span class="sxs-lookup"><span data-stu-id="e414e-324">Views</span></span>  
  
-   <span data-ttu-id="e414e-325">索引</span><span class="sxs-lookup"><span data-stu-id="e414e-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="e414e-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="e414e-326">Tables and Views</span></span>  
  
|<span data-ttu-id="e414e-327">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-327">ColumnName</span></span>|<span data-ttu-id="e414e-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e414e-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e414e-330">String</span><span class="sxs-lookup"><span data-stu-id="e414e-330">String</span></span>|  
|<span data-ttu-id="e414e-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e414e-331">TABLE_OWNER</span></span>|<span data-ttu-id="e414e-332">String</span><span class="sxs-lookup"><span data-stu-id="e414e-332">String</span></span>|  
|<span data-ttu-id="e414e-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-333">TABLE_NAME</span></span>|<span data-ttu-id="e414e-334">String</span><span class="sxs-lookup"><span data-stu-id="e414e-334">String</span></span>|  
|<span data-ttu-id="e414e-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-335">TABLE_TYPE</span></span>|<span data-ttu-id="e414e-336">String</span><span class="sxs-lookup"><span data-stu-id="e414e-336">String</span></span>|  
|<span data-ttu-id="e414e-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-337">REMARKS</span></span>|<span data-ttu-id="e414e-338">String</span><span class="sxs-lookup"><span data-stu-id="e414e-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e414e-339">Columns</span><span class="sxs-lookup"><span data-stu-id="e414e-339">Columns</span></span>  
  
|<span data-ttu-id="e414e-340">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-340">ColumnName</span></span>|<span data-ttu-id="e414e-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e414e-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e414e-343">String</span><span class="sxs-lookup"><span data-stu-id="e414e-343">String</span></span>|  
|<span data-ttu-id="e414e-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e414e-344">TABLE_OWNER</span></span>|<span data-ttu-id="e414e-345">String</span><span class="sxs-lookup"><span data-stu-id="e414e-345">String</span></span>|  
|<span data-ttu-id="e414e-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-346">TABLE_NAME</span></span>|<span data-ttu-id="e414e-347">String</span><span class="sxs-lookup"><span data-stu-id="e414e-347">String</span></span>|  
|<span data-ttu-id="e414e-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-348">COLUMN_NAME</span></span>|<span data-ttu-id="e414e-349">String</span><span class="sxs-lookup"><span data-stu-id="e414e-349">String</span></span>|  
|<span data-ttu-id="e414e-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-350">DATA_TYPE</span></span>|<span data-ttu-id="e414e-351">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-351">Int16</span></span>|  
|<span data-ttu-id="e414e-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-352">TYPE_NAME</span></span>|<span data-ttu-id="e414e-353">String</span><span class="sxs-lookup"><span data-stu-id="e414e-353">String</span></span>|  
|<span data-ttu-id="e414e-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e414e-354">PRECISION</span></span>|<span data-ttu-id="e414e-355">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-355">Int32</span></span>|  
|<span data-ttu-id="e414e-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-356">LENGTH</span></span>|<span data-ttu-id="e414e-357">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-357">Int32</span></span>|  
|<span data-ttu-id="e414e-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="e414e-358">SCALE</span></span>|<span data-ttu-id="e414e-359">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-359">Int16</span></span>|  
|<span data-ttu-id="e414e-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="e414e-360">RADIX</span></span>|<span data-ttu-id="e414e-361">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-361">Int16</span></span>|  
|<span data-ttu-id="e414e-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-362">NULLABLE</span></span>|<span data-ttu-id="e414e-363">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-363">Int16</span></span>|  
|<span data-ttu-id="e414e-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-364">REMARKS</span></span>|<span data-ttu-id="e414e-365">String</span><span class="sxs-lookup"><span data-stu-id="e414e-365">String</span></span>|  
|<span data-ttu-id="e414e-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e414e-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="e414e-367">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e414e-368">过程</span><span class="sxs-lookup"><span data-stu-id="e414e-368">Procedures</span></span>  
  
|<span data-ttu-id="e414e-369">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-369">ColumnName</span></span>|<span data-ttu-id="e414e-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e414e-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e414e-372">String</span><span class="sxs-lookup"><span data-stu-id="e414e-372">String</span></span>|  
|<span data-ttu-id="e414e-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e414e-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e414e-374">String</span><span class="sxs-lookup"><span data-stu-id="e414e-374">String</span></span>|  
|<span data-ttu-id="e414e-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="e414e-376">String</span><span class="sxs-lookup"><span data-stu-id="e414e-376">String</span></span>|  
|<span data-ttu-id="e414e-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e414e-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e414e-378">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-378">Int16</span></span>|  
|<span data-ttu-id="e414e-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e414e-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e414e-380">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-380">Int16</span></span>|  
|<span data-ttu-id="e414e-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e414e-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e414e-382">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-382">Int16</span></span>|  
|<span data-ttu-id="e414e-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-383">REMARKS</span></span>|<span data-ttu-id="e414e-384">String</span><span class="sxs-lookup"><span data-stu-id="e414e-384">String</span></span>|  
|<span data-ttu-id="e414e-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e414e-386">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e414e-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e414e-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e414e-388">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-388">ColumnName</span></span>|<span data-ttu-id="e414e-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e414e-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e414e-391">String</span><span class="sxs-lookup"><span data-stu-id="e414e-391">String</span></span>|  
|<span data-ttu-id="e414e-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e414e-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e414e-393">String</span><span class="sxs-lookup"><span data-stu-id="e414e-393">String</span></span>|  
|<span data-ttu-id="e414e-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="e414e-395">String</span><span class="sxs-lookup"><span data-stu-id="e414e-395">String</span></span>|  
|<span data-ttu-id="e414e-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-396">COLUMN_NAME</span></span>|<span data-ttu-id="e414e-397">String</span><span class="sxs-lookup"><span data-stu-id="e414e-397">String</span></span>|  
|<span data-ttu-id="e414e-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-398">COLUMN_TYPE</span></span>|<span data-ttu-id="e414e-399">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-399">Int16</span></span>|  
|<span data-ttu-id="e414e-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-400">DATA_TYPE</span></span>|<span data-ttu-id="e414e-401">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-401">Int16</span></span>|  
|<span data-ttu-id="e414e-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-402">TYPE_NAME</span></span>|<span data-ttu-id="e414e-403">String</span><span class="sxs-lookup"><span data-stu-id="e414e-403">String</span></span>|  
|<span data-ttu-id="e414e-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e414e-404">PRECISION</span></span>|<span data-ttu-id="e414e-405">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-405">Int32</span></span>|  
|<span data-ttu-id="e414e-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-406">LENGTH</span></span>|<span data-ttu-id="e414e-407">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-407">Int32</span></span>|  
|<span data-ttu-id="e414e-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="e414e-408">SCALE</span></span>|<span data-ttu-id="e414e-409">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-409">Int16</span></span>|  
|<span data-ttu-id="e414e-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="e414e-410">RADIX</span></span>|<span data-ttu-id="e414e-411">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-411">Int16</span></span>|  
|<span data-ttu-id="e414e-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-412">NULLABLE</span></span>|<span data-ttu-id="e414e-413">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-413">Int16</span></span>|  
|<span data-ttu-id="e414e-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-414">REMARKS</span></span>|<span data-ttu-id="e414e-415">String</span><span class="sxs-lookup"><span data-stu-id="e414e-415">String</span></span>|  
|<span data-ttu-id="e414e-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e414e-416">OVERLOAD</span></span>|<span data-ttu-id="e414e-417">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-417">Int32</span></span>|  
|<span data-ttu-id="e414e-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e414e-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="e414e-419">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="e414e-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="e414e-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="e414e-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="e414e-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e414e-422">表</span><span class="sxs-lookup"><span data-stu-id="e414e-422">Tables</span></span>  
  
-   <span data-ttu-id="e414e-423">索引</span><span class="sxs-lookup"><span data-stu-id="e414e-423">Indexes</span></span>  
  
-   <span data-ttu-id="e414e-424">Columns</span><span class="sxs-lookup"><span data-stu-id="e414e-424">Columns</span></span>  
  
-   <span data-ttu-id="e414e-425">过程</span><span class="sxs-lookup"><span data-stu-id="e414e-425">Procedures</span></span>  
  
-   <span data-ttu-id="e414e-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e414e-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e414e-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e414e-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e414e-428">视图</span><span class="sxs-lookup"><span data-stu-id="e414e-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="e414e-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="e414e-429">Tables and Views</span></span>  
  
|<span data-ttu-id="e414e-430">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-430">ColumnName</span></span>|<span data-ttu-id="e414e-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e414e-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e414e-433">String</span><span class="sxs-lookup"><span data-stu-id="e414e-433">String</span></span>|  
|<span data-ttu-id="e414e-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e414e-434">TABLE_OWNER</span></span>|<span data-ttu-id="e414e-435">String</span><span class="sxs-lookup"><span data-stu-id="e414e-435">String</span></span>|  
|<span data-ttu-id="e414e-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-436">TABLE_NAME</span></span>|<span data-ttu-id="e414e-437">String</span><span class="sxs-lookup"><span data-stu-id="e414e-437">String</span></span>|  
|<span data-ttu-id="e414e-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-438">TABLE_TYPE</span></span>|<span data-ttu-id="e414e-439">String</span><span class="sxs-lookup"><span data-stu-id="e414e-439">String</span></span>|  
|<span data-ttu-id="e414e-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-440">REMARKS</span></span>|<span data-ttu-id="e414e-441">String</span><span class="sxs-lookup"><span data-stu-id="e414e-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e414e-442">Columns</span><span class="sxs-lookup"><span data-stu-id="e414e-442">Columns</span></span>  
  
|<span data-ttu-id="e414e-443">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-443">ColumnName</span></span>|<span data-ttu-id="e414e-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e414e-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="e414e-446">String</span><span class="sxs-lookup"><span data-stu-id="e414e-446">String</span></span>|  
|<span data-ttu-id="e414e-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e414e-447">TABLE_OWNER</span></span>|<span data-ttu-id="e414e-448">String</span><span class="sxs-lookup"><span data-stu-id="e414e-448">String</span></span>|  
|<span data-ttu-id="e414e-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-449">TABLE_NAME</span></span>|<span data-ttu-id="e414e-450">String</span><span class="sxs-lookup"><span data-stu-id="e414e-450">String</span></span>|  
|<span data-ttu-id="e414e-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-451">COLUMN_NAME</span></span>|<span data-ttu-id="e414e-452">String</span><span class="sxs-lookup"><span data-stu-id="e414e-452">String</span></span>|  
|<span data-ttu-id="e414e-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-453">DATA_TYPE</span></span>|<span data-ttu-id="e414e-454">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-454">Int16</span></span>|  
|<span data-ttu-id="e414e-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-455">TYPE_NAME</span></span>|<span data-ttu-id="e414e-456">String</span><span class="sxs-lookup"><span data-stu-id="e414e-456">String</span></span>|  
|<span data-ttu-id="e414e-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e414e-457">PRECISION</span></span>|<span data-ttu-id="e414e-458">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-458">Int32</span></span>|  
|<span data-ttu-id="e414e-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-459">LENGTH</span></span>|<span data-ttu-id="e414e-460">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-460">Int32</span></span>|  
|<span data-ttu-id="e414e-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="e414e-461">SCALE</span></span>|<span data-ttu-id="e414e-462">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-462">Int16</span></span>|  
|<span data-ttu-id="e414e-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="e414e-463">RADIX</span></span>|<span data-ttu-id="e414e-464">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-464">Int16</span></span>|  
|<span data-ttu-id="e414e-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-465">NULLABLE</span></span>|<span data-ttu-id="e414e-466">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-466">Int16</span></span>|  
|<span data-ttu-id="e414e-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-467">REMARKS</span></span>|<span data-ttu-id="e414e-468">String</span><span class="sxs-lookup"><span data-stu-id="e414e-468">String</span></span>|  
|<span data-ttu-id="e414e-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e414e-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="e414e-470">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e414e-471">过程</span><span class="sxs-lookup"><span data-stu-id="e414e-471">Procedures</span></span>  
  
|<span data-ttu-id="e414e-472">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-472">ColumnName</span></span>|<span data-ttu-id="e414e-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e414e-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e414e-475">String</span><span class="sxs-lookup"><span data-stu-id="e414e-475">String</span></span>|  
|<span data-ttu-id="e414e-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e414e-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e414e-477">String</span><span class="sxs-lookup"><span data-stu-id="e414e-477">String</span></span>|  
|<span data-ttu-id="e414e-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="e414e-479">String</span><span class="sxs-lookup"><span data-stu-id="e414e-479">String</span></span>|  
|<span data-ttu-id="e414e-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e414e-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="e414e-481">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-481">Int16</span></span>|  
|<span data-ttu-id="e414e-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="e414e-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="e414e-483">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-483">Int16</span></span>|  
|<span data-ttu-id="e414e-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="e414e-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="e414e-485">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-485">Int16</span></span>|  
|<span data-ttu-id="e414e-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-486">REMARKS</span></span>|<span data-ttu-id="e414e-487">String</span><span class="sxs-lookup"><span data-stu-id="e414e-487">String</span></span>|  
|<span data-ttu-id="e414e-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e414e-489">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e414e-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e414e-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e414e-491">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-491">ColumnName</span></span>|<span data-ttu-id="e414e-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="e414e-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="e414e-494">String</span><span class="sxs-lookup"><span data-stu-id="e414e-494">String</span></span>|  
|<span data-ttu-id="e414e-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="e414e-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="e414e-496">String</span><span class="sxs-lookup"><span data-stu-id="e414e-496">String</span></span>|  
|<span data-ttu-id="e414e-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="e414e-498">String</span><span class="sxs-lookup"><span data-stu-id="e414e-498">String</span></span>|  
|<span data-ttu-id="e414e-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-499">COLUMN_NAME</span></span>|<span data-ttu-id="e414e-500">String</span><span class="sxs-lookup"><span data-stu-id="e414e-500">String</span></span>|  
|<span data-ttu-id="e414e-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-501">COLUMN_TYPE</span></span>|<span data-ttu-id="e414e-502">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-502">Int16</span></span>|  
|<span data-ttu-id="e414e-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-503">DATA_TYPE</span></span>|<span data-ttu-id="e414e-504">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-504">Int16</span></span>|  
|<span data-ttu-id="e414e-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-505">TYPE_NAME</span></span>|<span data-ttu-id="e414e-506">String</span><span class="sxs-lookup"><span data-stu-id="e414e-506">String</span></span>|  
|<span data-ttu-id="e414e-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="e414e-507">PRECISION</span></span>|<span data-ttu-id="e414e-508">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-508">Int32</span></span>|  
|<span data-ttu-id="e414e-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-509">LENGTH</span></span>|<span data-ttu-id="e414e-510">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-510">Int32</span></span>|  
|<span data-ttu-id="e414e-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="e414e-511">SCALE</span></span>|<span data-ttu-id="e414e-512">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-512">Int16</span></span>|  
|<span data-ttu-id="e414e-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="e414e-513">RADIX</span></span>|<span data-ttu-id="e414e-514">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-514">Int16</span></span>|  
|<span data-ttu-id="e414e-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-515">NULLABLE</span></span>|<span data-ttu-id="e414e-516">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-516">Int16</span></span>|  
|<span data-ttu-id="e414e-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-517">REMARKS</span></span>|<span data-ttu-id="e414e-518">String</span><span class="sxs-lookup"><span data-stu-id="e414e-518">String</span></span>|  
|<span data-ttu-id="e414e-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e414e-519">OVERLOAD</span></span>|<span data-ttu-id="e414e-520">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-520">Int32</span></span>|  
|<span data-ttu-id="e414e-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e414e-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="e414e-522">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e414e-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e414e-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e414e-524">列名</span><span class="sxs-lookup"><span data-stu-id="e414e-524">ColumnName</span></span>|<span data-ttu-id="e414e-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="e414e-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e414e-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="e414e-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="e414e-527">String</span><span class="sxs-lookup"><span data-stu-id="e414e-527">String</span></span>|  
|<span data-ttu-id="e414e-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="e414e-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="e414e-529">String</span><span class="sxs-lookup"><span data-stu-id="e414e-529">String</span></span>|  
|<span data-ttu-id="e414e-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="e414e-531">String</span><span class="sxs-lookup"><span data-stu-id="e414e-531">String</span></span>|  
|<span data-ttu-id="e414e-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-532">COLUMN_NAME</span></span>|<span data-ttu-id="e414e-533">String</span><span class="sxs-lookup"><span data-stu-id="e414e-533">String</span></span>|  
|<span data-ttu-id="e414e-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-534">COLUMN_TYPE</span></span>|<span data-ttu-id="e414e-535">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-535">Int16</span></span>|  
|<span data-ttu-id="e414e-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-536">DATA_TYPE</span></span>|<span data-ttu-id="e414e-537">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-537">Int16</span></span>|  
|<span data-ttu-id="e414e-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e414e-538">TYPE_NAME</span></span>|<span data-ttu-id="e414e-539">String</span><span class="sxs-lookup"><span data-stu-id="e414e-539">String</span></span>|  
|<span data-ttu-id="e414e-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="e414e-540">COLUMN_SIZE</span></span>|<span data-ttu-id="e414e-541">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-541">Int32</span></span>|  
|<span data-ttu-id="e414e-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="e414e-543">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-543">Int32</span></span>|  
|<span data-ttu-id="e414e-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="e414e-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="e414e-545">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-545">Int16</span></span>|  
|<span data-ttu-id="e414e-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="e414e-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="e414e-547">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-547">Int16</span></span>|  
|<span data-ttu-id="e414e-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-548">NULLABLE</span></span>|<span data-ttu-id="e414e-549">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-549">Int16</span></span>|  
|<span data-ttu-id="e414e-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="e414e-550">REMARKS</span></span>|<span data-ttu-id="e414e-551">String</span><span class="sxs-lookup"><span data-stu-id="e414e-551">String</span></span>|  
|<span data-ttu-id="e414e-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="e414e-552">COLUMN_DEF</span></span>|<span data-ttu-id="e414e-553">String</span><span class="sxs-lookup"><span data-stu-id="e414e-553">String</span></span>|  
|<span data-ttu-id="e414e-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e414e-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="e414e-555">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-555">Int16</span></span>|  
|<span data-ttu-id="e414e-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="e414e-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="e414e-557">Int16</span><span class="sxs-lookup"><span data-stu-id="e414e-557">Int16</span></span>|  
|<span data-ttu-id="e414e-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e414e-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="e414e-559">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-559">Int32</span></span>|  
|<span data-ttu-id="e414e-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e414e-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="e414e-561">Int32</span><span class="sxs-lookup"><span data-stu-id="e414e-561">Int32</span></span>|  
|<span data-ttu-id="e414e-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e414e-562">IS_NULLABLE</span></span>|<span data-ttu-id="e414e-563">String</span><span class="sxs-lookup"><span data-stu-id="e414e-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e414e-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="e414e-564">See Also</span></span>  
 [<span data-ttu-id="e414e-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e414e-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
