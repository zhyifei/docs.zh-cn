---
title: ODBC 架构集合
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43479975"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="cf706-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="cf706-102">ODBC Schema Collections</span></span>
<span data-ttu-id="cf706-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="cf706-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="cf706-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="cf706-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="cf706-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="cf706-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="cf706-106">表</span><span class="sxs-lookup"><span data-stu-id="cf706-106">Tables</span></span>  
  
-   <span data-ttu-id="cf706-107">索引</span><span class="sxs-lookup"><span data-stu-id="cf706-107">Indexes</span></span>  
  
-   <span data-ttu-id="cf706-108">Columns</span><span class="sxs-lookup"><span data-stu-id="cf706-108">Columns</span></span>  
  
-   <span data-ttu-id="cf706-109">过程</span><span class="sxs-lookup"><span data-stu-id="cf706-109">Procedures</span></span>  
  
-   <span data-ttu-id="cf706-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="cf706-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="cf706-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="cf706-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="cf706-112">视图</span><span class="sxs-lookup"><span data-stu-id="cf706-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="cf706-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="cf706-113">Tables and Views</span></span>  
  
|<span data-ttu-id="cf706-114">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-114">ColumnName</span></span>|<span data-ttu-id="cf706-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="cf706-116">TABLE_CAT</span></span>|<span data-ttu-id="cf706-117">String</span><span class="sxs-lookup"><span data-stu-id="cf706-117">String</span></span>|  
|<span data-ttu-id="cf706-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="cf706-118">TABLE_SCHEM</span></span>|<span data-ttu-id="cf706-119">String</span><span class="sxs-lookup"><span data-stu-id="cf706-119">String</span></span>|  
|<span data-ttu-id="cf706-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-120">TABLE_NAME</span></span>|<span data-ttu-id="cf706-121">String</span><span class="sxs-lookup"><span data-stu-id="cf706-121">String</span></span>|  
|<span data-ttu-id="cf706-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-122">TABLE_TYPE</span></span>|<span data-ttu-id="cf706-123">String</span><span class="sxs-lookup"><span data-stu-id="cf706-123">String</span></span>|  
|<span data-ttu-id="cf706-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-124">REMARKS</span></span>|<span data-ttu-id="cf706-125">String</span><span class="sxs-lookup"><span data-stu-id="cf706-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="cf706-126">索引</span><span class="sxs-lookup"><span data-stu-id="cf706-126">Indexes</span></span>  
  
|<span data-ttu-id="cf706-127">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-127">ColumnName</span></span>|<span data-ttu-id="cf706-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="cf706-129">TABLE_CAT</span></span>|<span data-ttu-id="cf706-130">String</span><span class="sxs-lookup"><span data-stu-id="cf706-130">String</span></span>|  
|<span data-ttu-id="cf706-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="cf706-131">TABLE_SCHEM</span></span>|<span data-ttu-id="cf706-132">String</span><span class="sxs-lookup"><span data-stu-id="cf706-132">String</span></span>|  
|<span data-ttu-id="cf706-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-133">TABLE_NAME</span></span>|<span data-ttu-id="cf706-134">String</span><span class="sxs-lookup"><span data-stu-id="cf706-134">String</span></span>|  
|<span data-ttu-id="cf706-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="cf706-135">NON_UNIQUE</span></span>|<span data-ttu-id="cf706-136">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-136">Int16</span></span>|  
|<span data-ttu-id="cf706-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="cf706-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="cf706-138">String</span><span class="sxs-lookup"><span data-stu-id="cf706-138">String</span></span>|  
|<span data-ttu-id="cf706-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-139">INDEX_NAME</span></span>|<span data-ttu-id="cf706-140">String</span><span class="sxs-lookup"><span data-stu-id="cf706-140">String</span></span>|  
|<span data-ttu-id="cf706-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-141">TYPE</span></span>|<span data-ttu-id="cf706-142">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-142">Int16</span></span>|  
|<span data-ttu-id="cf706-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cf706-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="cf706-144">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-144">Int16</span></span>|  
|<span data-ttu-id="cf706-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-145">COLUMN_NAME</span></span>|<span data-ttu-id="cf706-146">String</span><span class="sxs-lookup"><span data-stu-id="cf706-146">String</span></span>|  
|<span data-ttu-id="cf706-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="cf706-147">ASC_OR_DESC</span></span>|<span data-ttu-id="cf706-148">String</span><span class="sxs-lookup"><span data-stu-id="cf706-148">String</span></span>|  
|<span data-ttu-id="cf706-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="cf706-149">CARDINATLITY</span></span>|<span data-ttu-id="cf706-150">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-150">Int32</span></span>|  
|<span data-ttu-id="cf706-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="cf706-151">PAGES</span></span>|<span data-ttu-id="cf706-152">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-152">Int32</span></span>|  
|<span data-ttu-id="cf706-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="cf706-153">FILTER_CONDITION</span></span>|<span data-ttu-id="cf706-154">String</span><span class="sxs-lookup"><span data-stu-id="cf706-154">String</span></span>|  
|<span data-ttu-id="cf706-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cf706-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="cf706-156">String</span><span class="sxs-lookup"><span data-stu-id="cf706-156">String</span></span>|  
|<span data-ttu-id="cf706-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="cf706-158">Byte</span><span class="sxs-lookup"><span data-stu-id="cf706-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="cf706-159">Columns</span><span class="sxs-lookup"><span data-stu-id="cf706-159">Columns</span></span>  
  
|<span data-ttu-id="cf706-160">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-160">ColumnName</span></span>|<span data-ttu-id="cf706-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="cf706-162">TABLE_CAT</span></span>|<span data-ttu-id="cf706-163">String</span><span class="sxs-lookup"><span data-stu-id="cf706-163">String</span></span>|  
|<span data-ttu-id="cf706-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="cf706-164">TABLE_SCHEM</span></span>|<span data-ttu-id="cf706-165">String</span><span class="sxs-lookup"><span data-stu-id="cf706-165">String</span></span>|  
|<span data-ttu-id="cf706-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-166">TABLE_NAME</span></span>|<span data-ttu-id="cf706-167">String</span><span class="sxs-lookup"><span data-stu-id="cf706-167">String</span></span>|  
|<span data-ttu-id="cf706-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-168">COLUMN_NAME</span></span>|<span data-ttu-id="cf706-169">String</span><span class="sxs-lookup"><span data-stu-id="cf706-169">String</span></span>|  
|<span data-ttu-id="cf706-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-170">DATA_TYPE</span></span>|<span data-ttu-id="cf706-171">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-171">Int16</span></span>|  
|<span data-ttu-id="cf706-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-172">TYPE_NAME</span></span>|<span data-ttu-id="cf706-173">String</span><span class="sxs-lookup"><span data-stu-id="cf706-173">String</span></span>|  
|<span data-ttu-id="cf706-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="cf706-174">COLUMN_SIZE</span></span>|<span data-ttu-id="cf706-175">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-175">Int32</span></span>|  
|<span data-ttu-id="cf706-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="cf706-177">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-177">Int32</span></span>|  
|<span data-ttu-id="cf706-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="cf706-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="cf706-179">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-179">Int16</span></span>|  
|<span data-ttu-id="cf706-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="cf706-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="cf706-181">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-181">Int16</span></span>|  
|<span data-ttu-id="cf706-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-182">NULLABLE</span></span>|<span data-ttu-id="cf706-183">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-183">Int16</span></span>|  
|<span data-ttu-id="cf706-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-184">REMARKS</span></span>|<span data-ttu-id="cf706-185">String</span><span class="sxs-lookup"><span data-stu-id="cf706-185">String</span></span>|  
|<span data-ttu-id="cf706-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="cf706-186">COLUMN_DEF</span></span>|<span data-ttu-id="cf706-187">String</span><span class="sxs-lookup"><span data-stu-id="cf706-187">String</span></span>|  
|<span data-ttu-id="cf706-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="cf706-189">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-189">Int16</span></span>|  
|<span data-ttu-id="cf706-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="cf706-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="cf706-191">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-191">Int16</span></span>|  
|<span data-ttu-id="cf706-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="cf706-193">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-193">Int32</span></span>|  
|<span data-ttu-id="cf706-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cf706-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="cf706-195">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-195">Int32</span></span>|  
|<span data-ttu-id="cf706-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-196">IS_NULLABLE</span></span>|<span data-ttu-id="cf706-197">String</span><span class="sxs-lookup"><span data-stu-id="cf706-197">String</span></span>|  
|<span data-ttu-id="cf706-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cf706-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="cf706-199">String</span><span class="sxs-lookup"><span data-stu-id="cf706-199">String</span></span>|  
|<span data-ttu-id="cf706-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cf706-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="cf706-201">String</span><span class="sxs-lookup"><span data-stu-id="cf706-201">String</span></span>|  
|<span data-ttu-id="cf706-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="cf706-203">Byte</span><span class="sxs-lookup"><span data-stu-id="cf706-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="cf706-204">过程</span><span class="sxs-lookup"><span data-stu-id="cf706-204">Procedures</span></span>  
  
|<span data-ttu-id="cf706-205">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-205">ColumnName</span></span>|<span data-ttu-id="cf706-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="cf706-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="cf706-208">String</span><span class="sxs-lookup"><span data-stu-id="cf706-208">String</span></span>|  
|<span data-ttu-id="cf706-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="cf706-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="cf706-210">String</span><span class="sxs-lookup"><span data-stu-id="cf706-210">String</span></span>|  
|<span data-ttu-id="cf706-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="cf706-212">String</span><span class="sxs-lookup"><span data-stu-id="cf706-212">String</span></span>|  
|<span data-ttu-id="cf706-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="cf706-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="cf706-214">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-214">Int32</span></span>|  
|<span data-ttu-id="cf706-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="cf706-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="cf706-216">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-216">Int32</span></span>|  
|<span data-ttu-id="cf706-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="cf706-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="cf706-218">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-218">Int32</span></span>|  
|<span data-ttu-id="cf706-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-219">REMARKS</span></span>|<span data-ttu-id="cf706-220">String</span><span class="sxs-lookup"><span data-stu-id="cf706-220">String</span></span>|  
|<span data-ttu-id="cf706-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="cf706-222">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="cf706-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="cf706-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="cf706-224">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-224">ColumnName</span></span>|<span data-ttu-id="cf706-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="cf706-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="cf706-227">String</span><span class="sxs-lookup"><span data-stu-id="cf706-227">String</span></span>|  
|<span data-ttu-id="cf706-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="cf706-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="cf706-229">String</span><span class="sxs-lookup"><span data-stu-id="cf706-229">String</span></span>|  
|<span data-ttu-id="cf706-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="cf706-231">String</span><span class="sxs-lookup"><span data-stu-id="cf706-231">String</span></span>|  
|<span data-ttu-id="cf706-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-232">COLUMN_NAME</span></span>|<span data-ttu-id="cf706-233">String</span><span class="sxs-lookup"><span data-stu-id="cf706-233">String</span></span>|  
|<span data-ttu-id="cf706-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-234">COLUMN_TYPE</span></span>|<span data-ttu-id="cf706-235">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-235">Int16</span></span>|  
|<span data-ttu-id="cf706-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-236">DATA_TYPE</span></span>|<span data-ttu-id="cf706-237">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-237">Int16</span></span>|  
|<span data-ttu-id="cf706-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-238">TYPE_NAME</span></span>|<span data-ttu-id="cf706-239">String</span><span class="sxs-lookup"><span data-stu-id="cf706-239">String</span></span>|  
|<span data-ttu-id="cf706-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="cf706-240">COLUMN_SIZE</span></span>|<span data-ttu-id="cf706-241">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-241">Int32</span></span>|  
|<span data-ttu-id="cf706-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="cf706-243">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-243">Int32</span></span>|  
|<span data-ttu-id="cf706-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="cf706-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="cf706-245">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-245">Int16</span></span>|  
|<span data-ttu-id="cf706-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="cf706-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="cf706-247">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-247">Int16</span></span>|  
|<span data-ttu-id="cf706-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-248">NULLABLE</span></span>|<span data-ttu-id="cf706-249">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-249">Int16</span></span>|  
|<span data-ttu-id="cf706-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-250">REMARKS</span></span>|<span data-ttu-id="cf706-251">String</span><span class="sxs-lookup"><span data-stu-id="cf706-251">String</span></span>|  
|<span data-ttu-id="cf706-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="cf706-252">COLUMN_DEF</span></span>|<span data-ttu-id="cf706-253">String</span><span class="sxs-lookup"><span data-stu-id="cf706-253">String</span></span>|  
|<span data-ttu-id="cf706-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="cf706-255">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-255">Int16</span></span>|  
|<span data-ttu-id="cf706-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="cf706-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="cf706-257">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-257">Int16</span></span>|  
|<span data-ttu-id="cf706-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="cf706-259">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-259">Int32</span></span>|  
|<span data-ttu-id="cf706-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cf706-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="cf706-261">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-261">Int32</span></span>|  
|<span data-ttu-id="cf706-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-262">IS_NULLABLE</span></span>|<span data-ttu-id="cf706-263">String</span><span class="sxs-lookup"><span data-stu-id="cf706-263">String</span></span>|  
|<span data-ttu-id="cf706-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cf706-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="cf706-265">String</span><span class="sxs-lookup"><span data-stu-id="cf706-265">String</span></span>|  
|<span data-ttu-id="cf706-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cf706-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="cf706-267">String</span><span class="sxs-lookup"><span data-stu-id="cf706-267">String</span></span>|  
|<span data-ttu-id="cf706-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="cf706-269">Byte</span><span class="sxs-lookup"><span data-stu-id="cf706-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="cf706-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="cf706-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="cf706-271">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-271">ColumnName</span></span>|<span data-ttu-id="cf706-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="cf706-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="cf706-274">String</span><span class="sxs-lookup"><span data-stu-id="cf706-274">String</span></span>|  
|<span data-ttu-id="cf706-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="cf706-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="cf706-276">String</span><span class="sxs-lookup"><span data-stu-id="cf706-276">String</span></span>|  
|<span data-ttu-id="cf706-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="cf706-278">String</span><span class="sxs-lookup"><span data-stu-id="cf706-278">String</span></span>|  
|<span data-ttu-id="cf706-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-279">COLUMN_NAME</span></span>|<span data-ttu-id="cf706-280">String</span><span class="sxs-lookup"><span data-stu-id="cf706-280">String</span></span>|  
|<span data-ttu-id="cf706-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-281">COLUMN_TYPE</span></span>|<span data-ttu-id="cf706-282">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-282">Int16</span></span>|  
|<span data-ttu-id="cf706-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-283">DATA_TYPE</span></span>|<span data-ttu-id="cf706-284">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-284">Int16</span></span>|  
|<span data-ttu-id="cf706-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-285">TYPE_NAME</span></span>|<span data-ttu-id="cf706-286">String</span><span class="sxs-lookup"><span data-stu-id="cf706-286">String</span></span>|  
|<span data-ttu-id="cf706-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="cf706-287">COLUMN_SIZE</span></span>|<span data-ttu-id="cf706-288">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-288">Int32</span></span>|  
|<span data-ttu-id="cf706-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="cf706-290">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-290">Int32</span></span>|  
|<span data-ttu-id="cf706-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="cf706-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="cf706-292">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-292">Int16</span></span>|  
|<span data-ttu-id="cf706-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="cf706-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="cf706-294">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-294">Int16</span></span>|  
|<span data-ttu-id="cf706-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-295">NULLABLE</span></span>|<span data-ttu-id="cf706-296">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-296">Int16</span></span>|  
|<span data-ttu-id="cf706-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-297">REMARKS</span></span>|<span data-ttu-id="cf706-298">String</span><span class="sxs-lookup"><span data-stu-id="cf706-298">String</span></span>|  
|<span data-ttu-id="cf706-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="cf706-299">COLUMN_DEF</span></span>|<span data-ttu-id="cf706-300">String</span><span class="sxs-lookup"><span data-stu-id="cf706-300">String</span></span>|  
|<span data-ttu-id="cf706-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="cf706-302">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-302">Int16</span></span>|  
|<span data-ttu-id="cf706-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="cf706-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="cf706-304">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-304">Int16</span></span>|  
|<span data-ttu-id="cf706-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="cf706-306">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-306">Int32</span></span>|  
|<span data-ttu-id="cf706-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cf706-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="cf706-308">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-308">Int32</span></span>|  
|<span data-ttu-id="cf706-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-309">IS_NULLABLE</span></span>|<span data-ttu-id="cf706-310">String</span><span class="sxs-lookup"><span data-stu-id="cf706-310">String</span></span>|  
|<span data-ttu-id="cf706-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="cf706-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="cf706-312">String</span><span class="sxs-lookup"><span data-stu-id="cf706-312">String</span></span>|  
|<span data-ttu-id="cf706-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="cf706-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="cf706-314">String</span><span class="sxs-lookup"><span data-stu-id="cf706-314">String</span></span>|  
|<span data-ttu-id="cf706-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="cf706-316">Byte</span><span class="sxs-lookup"><span data-stu-id="cf706-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="cf706-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="cf706-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="cf706-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="cf706-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="cf706-319">表</span><span class="sxs-lookup"><span data-stu-id="cf706-319">Tables</span></span>  
  
-   <span data-ttu-id="cf706-320">Columns</span><span class="sxs-lookup"><span data-stu-id="cf706-320">Columns</span></span>  
  
-   <span data-ttu-id="cf706-321">过程</span><span class="sxs-lookup"><span data-stu-id="cf706-321">Procedures</span></span>  
  
-   <span data-ttu-id="cf706-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="cf706-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="cf706-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="cf706-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="cf706-324">视图</span><span class="sxs-lookup"><span data-stu-id="cf706-324">Views</span></span>  
  
-   <span data-ttu-id="cf706-325">索引</span><span class="sxs-lookup"><span data-stu-id="cf706-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="cf706-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="cf706-326">Tables and Views</span></span>  
  
|<span data-ttu-id="cf706-327">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-327">ColumnName</span></span>|<span data-ttu-id="cf706-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="cf706-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="cf706-330">String</span><span class="sxs-lookup"><span data-stu-id="cf706-330">String</span></span>|  
|<span data-ttu-id="cf706-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf706-331">TABLE_OWNER</span></span>|<span data-ttu-id="cf706-332">String</span><span class="sxs-lookup"><span data-stu-id="cf706-332">String</span></span>|  
|<span data-ttu-id="cf706-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-333">TABLE_NAME</span></span>|<span data-ttu-id="cf706-334">String</span><span class="sxs-lookup"><span data-stu-id="cf706-334">String</span></span>|  
|<span data-ttu-id="cf706-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-335">TABLE_TYPE</span></span>|<span data-ttu-id="cf706-336">String</span><span class="sxs-lookup"><span data-stu-id="cf706-336">String</span></span>|  
|<span data-ttu-id="cf706-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-337">REMARKS</span></span>|<span data-ttu-id="cf706-338">String</span><span class="sxs-lookup"><span data-stu-id="cf706-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="cf706-339">Columns</span><span class="sxs-lookup"><span data-stu-id="cf706-339">Columns</span></span>  
  
|<span data-ttu-id="cf706-340">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-340">ColumnName</span></span>|<span data-ttu-id="cf706-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="cf706-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="cf706-343">String</span><span class="sxs-lookup"><span data-stu-id="cf706-343">String</span></span>|  
|<span data-ttu-id="cf706-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf706-344">TABLE_OWNER</span></span>|<span data-ttu-id="cf706-345">String</span><span class="sxs-lookup"><span data-stu-id="cf706-345">String</span></span>|  
|<span data-ttu-id="cf706-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-346">TABLE_NAME</span></span>|<span data-ttu-id="cf706-347">String</span><span class="sxs-lookup"><span data-stu-id="cf706-347">String</span></span>|  
|<span data-ttu-id="cf706-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-348">COLUMN_NAME</span></span>|<span data-ttu-id="cf706-349">String</span><span class="sxs-lookup"><span data-stu-id="cf706-349">String</span></span>|  
|<span data-ttu-id="cf706-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-350">DATA_TYPE</span></span>|<span data-ttu-id="cf706-351">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-351">Int16</span></span>|  
|<span data-ttu-id="cf706-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-352">TYPE_NAME</span></span>|<span data-ttu-id="cf706-353">String</span><span class="sxs-lookup"><span data-stu-id="cf706-353">String</span></span>|  
|<span data-ttu-id="cf706-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="cf706-354">PRECISION</span></span>|<span data-ttu-id="cf706-355">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-355">Int32</span></span>|  
|<span data-ttu-id="cf706-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-356">LENGTH</span></span>|<span data-ttu-id="cf706-357">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-357">Int32</span></span>|  
|<span data-ttu-id="cf706-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="cf706-358">SCALE</span></span>|<span data-ttu-id="cf706-359">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-359">Int16</span></span>|  
|<span data-ttu-id="cf706-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="cf706-360">RADIX</span></span>|<span data-ttu-id="cf706-361">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-361">Int16</span></span>|  
|<span data-ttu-id="cf706-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-362">NULLABLE</span></span>|<span data-ttu-id="cf706-363">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-363">Int16</span></span>|  
|<span data-ttu-id="cf706-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-364">REMARKS</span></span>|<span data-ttu-id="cf706-365">String</span><span class="sxs-lookup"><span data-stu-id="cf706-365">String</span></span>|  
|<span data-ttu-id="cf706-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cf706-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="cf706-367">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="cf706-368">过程</span><span class="sxs-lookup"><span data-stu-id="cf706-368">Procedures</span></span>  
  
|<span data-ttu-id="cf706-369">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-369">ColumnName</span></span>|<span data-ttu-id="cf706-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="cf706-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="cf706-372">String</span><span class="sxs-lookup"><span data-stu-id="cf706-372">String</span></span>|  
|<span data-ttu-id="cf706-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf706-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="cf706-374">String</span><span class="sxs-lookup"><span data-stu-id="cf706-374">String</span></span>|  
|<span data-ttu-id="cf706-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="cf706-376">String</span><span class="sxs-lookup"><span data-stu-id="cf706-376">String</span></span>|  
|<span data-ttu-id="cf706-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="cf706-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="cf706-378">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-378">Int16</span></span>|  
|<span data-ttu-id="cf706-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="cf706-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="cf706-380">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-380">Int16</span></span>|  
|<span data-ttu-id="cf706-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="cf706-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="cf706-382">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-382">Int16</span></span>|  
|<span data-ttu-id="cf706-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-383">REMARKS</span></span>|<span data-ttu-id="cf706-384">String</span><span class="sxs-lookup"><span data-stu-id="cf706-384">String</span></span>|  
|<span data-ttu-id="cf706-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="cf706-386">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="cf706-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="cf706-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="cf706-388">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-388">ColumnName</span></span>|<span data-ttu-id="cf706-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="cf706-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="cf706-391">String</span><span class="sxs-lookup"><span data-stu-id="cf706-391">String</span></span>|  
|<span data-ttu-id="cf706-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf706-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="cf706-393">String</span><span class="sxs-lookup"><span data-stu-id="cf706-393">String</span></span>|  
|<span data-ttu-id="cf706-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="cf706-395">String</span><span class="sxs-lookup"><span data-stu-id="cf706-395">String</span></span>|  
|<span data-ttu-id="cf706-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-396">COLUMN_NAME</span></span>|<span data-ttu-id="cf706-397">String</span><span class="sxs-lookup"><span data-stu-id="cf706-397">String</span></span>|  
|<span data-ttu-id="cf706-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-398">COLUMN_TYPE</span></span>|<span data-ttu-id="cf706-399">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-399">Int16</span></span>|  
|<span data-ttu-id="cf706-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-400">DATA_TYPE</span></span>|<span data-ttu-id="cf706-401">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-401">Int16</span></span>|  
|<span data-ttu-id="cf706-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-402">TYPE_NAME</span></span>|<span data-ttu-id="cf706-403">String</span><span class="sxs-lookup"><span data-stu-id="cf706-403">String</span></span>|  
|<span data-ttu-id="cf706-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="cf706-404">PRECISION</span></span>|<span data-ttu-id="cf706-405">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-405">Int32</span></span>|  
|<span data-ttu-id="cf706-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-406">LENGTH</span></span>|<span data-ttu-id="cf706-407">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-407">Int32</span></span>|  
|<span data-ttu-id="cf706-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="cf706-408">SCALE</span></span>|<span data-ttu-id="cf706-409">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-409">Int16</span></span>|  
|<span data-ttu-id="cf706-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="cf706-410">RADIX</span></span>|<span data-ttu-id="cf706-411">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-411">Int16</span></span>|  
|<span data-ttu-id="cf706-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-412">NULLABLE</span></span>|<span data-ttu-id="cf706-413">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-413">Int16</span></span>|  
|<span data-ttu-id="cf706-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-414">REMARKS</span></span>|<span data-ttu-id="cf706-415">String</span><span class="sxs-lookup"><span data-stu-id="cf706-415">String</span></span>|  
|<span data-ttu-id="cf706-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="cf706-416">OVERLOAD</span></span>|<span data-ttu-id="cf706-417">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-417">Int32</span></span>|  
|<span data-ttu-id="cf706-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cf706-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="cf706-419">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="cf706-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="cf706-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="cf706-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="cf706-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="cf706-422">表</span><span class="sxs-lookup"><span data-stu-id="cf706-422">Tables</span></span>  
  
-   <span data-ttu-id="cf706-423">索引</span><span class="sxs-lookup"><span data-stu-id="cf706-423">Indexes</span></span>  
  
-   <span data-ttu-id="cf706-424">Columns</span><span class="sxs-lookup"><span data-stu-id="cf706-424">Columns</span></span>  
  
-   <span data-ttu-id="cf706-425">过程</span><span class="sxs-lookup"><span data-stu-id="cf706-425">Procedures</span></span>  
  
-   <span data-ttu-id="cf706-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="cf706-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="cf706-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="cf706-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="cf706-428">视图</span><span class="sxs-lookup"><span data-stu-id="cf706-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="cf706-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="cf706-429">Tables and Views</span></span>  
  
|<span data-ttu-id="cf706-430">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-430">ColumnName</span></span>|<span data-ttu-id="cf706-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="cf706-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="cf706-433">String</span><span class="sxs-lookup"><span data-stu-id="cf706-433">String</span></span>|  
|<span data-ttu-id="cf706-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf706-434">TABLE_OWNER</span></span>|<span data-ttu-id="cf706-435">String</span><span class="sxs-lookup"><span data-stu-id="cf706-435">String</span></span>|  
|<span data-ttu-id="cf706-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-436">TABLE_NAME</span></span>|<span data-ttu-id="cf706-437">String</span><span class="sxs-lookup"><span data-stu-id="cf706-437">String</span></span>|  
|<span data-ttu-id="cf706-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-438">TABLE_TYPE</span></span>|<span data-ttu-id="cf706-439">String</span><span class="sxs-lookup"><span data-stu-id="cf706-439">String</span></span>|  
|<span data-ttu-id="cf706-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-440">REMARKS</span></span>|<span data-ttu-id="cf706-441">String</span><span class="sxs-lookup"><span data-stu-id="cf706-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="cf706-442">Columns</span><span class="sxs-lookup"><span data-stu-id="cf706-442">Columns</span></span>  
  
|<span data-ttu-id="cf706-443">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-443">ColumnName</span></span>|<span data-ttu-id="cf706-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="cf706-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="cf706-446">String</span><span class="sxs-lookup"><span data-stu-id="cf706-446">String</span></span>|  
|<span data-ttu-id="cf706-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf706-447">TABLE_OWNER</span></span>|<span data-ttu-id="cf706-448">String</span><span class="sxs-lookup"><span data-stu-id="cf706-448">String</span></span>|  
|<span data-ttu-id="cf706-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-449">TABLE_NAME</span></span>|<span data-ttu-id="cf706-450">String</span><span class="sxs-lookup"><span data-stu-id="cf706-450">String</span></span>|  
|<span data-ttu-id="cf706-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-451">COLUMN_NAME</span></span>|<span data-ttu-id="cf706-452">String</span><span class="sxs-lookup"><span data-stu-id="cf706-452">String</span></span>|  
|<span data-ttu-id="cf706-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-453">DATA_TYPE</span></span>|<span data-ttu-id="cf706-454">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-454">Int16</span></span>|  
|<span data-ttu-id="cf706-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-455">TYPE_NAME</span></span>|<span data-ttu-id="cf706-456">String</span><span class="sxs-lookup"><span data-stu-id="cf706-456">String</span></span>|  
|<span data-ttu-id="cf706-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="cf706-457">PRECISION</span></span>|<span data-ttu-id="cf706-458">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-458">Int32</span></span>|  
|<span data-ttu-id="cf706-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-459">LENGTH</span></span>|<span data-ttu-id="cf706-460">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-460">Int32</span></span>|  
|<span data-ttu-id="cf706-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="cf706-461">SCALE</span></span>|<span data-ttu-id="cf706-462">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-462">Int16</span></span>|  
|<span data-ttu-id="cf706-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="cf706-463">RADIX</span></span>|<span data-ttu-id="cf706-464">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-464">Int16</span></span>|  
|<span data-ttu-id="cf706-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-465">NULLABLE</span></span>|<span data-ttu-id="cf706-466">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-466">Int16</span></span>|  
|<span data-ttu-id="cf706-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-467">REMARKS</span></span>|<span data-ttu-id="cf706-468">String</span><span class="sxs-lookup"><span data-stu-id="cf706-468">String</span></span>|  
|<span data-ttu-id="cf706-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cf706-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="cf706-470">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="cf706-471">过程</span><span class="sxs-lookup"><span data-stu-id="cf706-471">Procedures</span></span>  
  
|<span data-ttu-id="cf706-472">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-472">ColumnName</span></span>|<span data-ttu-id="cf706-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="cf706-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="cf706-475">String</span><span class="sxs-lookup"><span data-stu-id="cf706-475">String</span></span>|  
|<span data-ttu-id="cf706-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf706-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="cf706-477">String</span><span class="sxs-lookup"><span data-stu-id="cf706-477">String</span></span>|  
|<span data-ttu-id="cf706-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="cf706-479">String</span><span class="sxs-lookup"><span data-stu-id="cf706-479">String</span></span>|  
|<span data-ttu-id="cf706-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="cf706-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="cf706-481">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-481">Int16</span></span>|  
|<span data-ttu-id="cf706-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="cf706-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="cf706-483">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-483">Int16</span></span>|  
|<span data-ttu-id="cf706-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="cf706-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="cf706-485">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-485">Int16</span></span>|  
|<span data-ttu-id="cf706-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-486">REMARKS</span></span>|<span data-ttu-id="cf706-487">String</span><span class="sxs-lookup"><span data-stu-id="cf706-487">String</span></span>|  
|<span data-ttu-id="cf706-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="cf706-489">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="cf706-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="cf706-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="cf706-491">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-491">ColumnName</span></span>|<span data-ttu-id="cf706-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="cf706-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="cf706-494">String</span><span class="sxs-lookup"><span data-stu-id="cf706-494">String</span></span>|  
|<span data-ttu-id="cf706-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf706-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="cf706-496">String</span><span class="sxs-lookup"><span data-stu-id="cf706-496">String</span></span>|  
|<span data-ttu-id="cf706-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="cf706-498">String</span><span class="sxs-lookup"><span data-stu-id="cf706-498">String</span></span>|  
|<span data-ttu-id="cf706-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-499">COLUMN_NAME</span></span>|<span data-ttu-id="cf706-500">String</span><span class="sxs-lookup"><span data-stu-id="cf706-500">String</span></span>|  
|<span data-ttu-id="cf706-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-501">COLUMN_TYPE</span></span>|<span data-ttu-id="cf706-502">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-502">Int16</span></span>|  
|<span data-ttu-id="cf706-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-503">DATA_TYPE</span></span>|<span data-ttu-id="cf706-504">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-504">Int16</span></span>|  
|<span data-ttu-id="cf706-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-505">TYPE_NAME</span></span>|<span data-ttu-id="cf706-506">String</span><span class="sxs-lookup"><span data-stu-id="cf706-506">String</span></span>|  
|<span data-ttu-id="cf706-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="cf706-507">PRECISION</span></span>|<span data-ttu-id="cf706-508">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-508">Int32</span></span>|  
|<span data-ttu-id="cf706-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-509">LENGTH</span></span>|<span data-ttu-id="cf706-510">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-510">Int32</span></span>|  
|<span data-ttu-id="cf706-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="cf706-511">SCALE</span></span>|<span data-ttu-id="cf706-512">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-512">Int16</span></span>|  
|<span data-ttu-id="cf706-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="cf706-513">RADIX</span></span>|<span data-ttu-id="cf706-514">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-514">Int16</span></span>|  
|<span data-ttu-id="cf706-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-515">NULLABLE</span></span>|<span data-ttu-id="cf706-516">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-516">Int16</span></span>|  
|<span data-ttu-id="cf706-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-517">REMARKS</span></span>|<span data-ttu-id="cf706-518">String</span><span class="sxs-lookup"><span data-stu-id="cf706-518">String</span></span>|  
|<span data-ttu-id="cf706-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="cf706-519">OVERLOAD</span></span>|<span data-ttu-id="cf706-520">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-520">Int32</span></span>|  
|<span data-ttu-id="cf706-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cf706-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="cf706-522">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="cf706-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="cf706-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="cf706-524">列名</span><span class="sxs-lookup"><span data-stu-id="cf706-524">ColumnName</span></span>|<span data-ttu-id="cf706-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf706-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="cf706-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="cf706-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="cf706-527">String</span><span class="sxs-lookup"><span data-stu-id="cf706-527">String</span></span>|  
|<span data-ttu-id="cf706-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="cf706-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="cf706-529">String</span><span class="sxs-lookup"><span data-stu-id="cf706-529">String</span></span>|  
|<span data-ttu-id="cf706-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="cf706-531">String</span><span class="sxs-lookup"><span data-stu-id="cf706-531">String</span></span>|  
|<span data-ttu-id="cf706-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-532">COLUMN_NAME</span></span>|<span data-ttu-id="cf706-533">String</span><span class="sxs-lookup"><span data-stu-id="cf706-533">String</span></span>|  
|<span data-ttu-id="cf706-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-534">COLUMN_TYPE</span></span>|<span data-ttu-id="cf706-535">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-535">Int16</span></span>|  
|<span data-ttu-id="cf706-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-536">DATA_TYPE</span></span>|<span data-ttu-id="cf706-537">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-537">Int16</span></span>|  
|<span data-ttu-id="cf706-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="cf706-538">TYPE_NAME</span></span>|<span data-ttu-id="cf706-539">String</span><span class="sxs-lookup"><span data-stu-id="cf706-539">String</span></span>|  
|<span data-ttu-id="cf706-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="cf706-540">COLUMN_SIZE</span></span>|<span data-ttu-id="cf706-541">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-541">Int32</span></span>|  
|<span data-ttu-id="cf706-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="cf706-543">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-543">Int32</span></span>|  
|<span data-ttu-id="cf706-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="cf706-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="cf706-545">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-545">Int16</span></span>|  
|<span data-ttu-id="cf706-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="cf706-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="cf706-547">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-547">Int16</span></span>|  
|<span data-ttu-id="cf706-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-548">NULLABLE</span></span>|<span data-ttu-id="cf706-549">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-549">Int16</span></span>|  
|<span data-ttu-id="cf706-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="cf706-550">REMARKS</span></span>|<span data-ttu-id="cf706-551">String</span><span class="sxs-lookup"><span data-stu-id="cf706-551">String</span></span>|  
|<span data-ttu-id="cf706-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="cf706-552">COLUMN_DEF</span></span>|<span data-ttu-id="cf706-553">String</span><span class="sxs-lookup"><span data-stu-id="cf706-553">String</span></span>|  
|<span data-ttu-id="cf706-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="cf706-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="cf706-555">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-555">Int16</span></span>|  
|<span data-ttu-id="cf706-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="cf706-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="cf706-557">Int16</span><span class="sxs-lookup"><span data-stu-id="cf706-557">Int16</span></span>|  
|<span data-ttu-id="cf706-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="cf706-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="cf706-559">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-559">Int32</span></span>|  
|<span data-ttu-id="cf706-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="cf706-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="cf706-561">Int32</span><span class="sxs-lookup"><span data-stu-id="cf706-561">Int32</span></span>|  
|<span data-ttu-id="cf706-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="cf706-562">IS_NULLABLE</span></span>|<span data-ttu-id="cf706-563">String</span><span class="sxs-lookup"><span data-stu-id="cf706-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf706-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf706-564">See Also</span></span>  
 [<span data-ttu-id="cf706-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="cf706-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
