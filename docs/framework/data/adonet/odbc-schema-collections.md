---
title: ODBC 架构集合
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 072a9cd365031cd5660d1824bc229d459abc5af8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525828"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="ce250-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="ce250-102">ODBC Schema Collections</span></span>
<span data-ttu-id="ce250-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="ce250-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="ce250-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="ce250-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="ce250-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="ce250-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="ce250-106">表</span><span class="sxs-lookup"><span data-stu-id="ce250-106">Tables</span></span>  
  
-   <span data-ttu-id="ce250-107">索引</span><span class="sxs-lookup"><span data-stu-id="ce250-107">Indexes</span></span>  
  
-   <span data-ttu-id="ce250-108">Columns</span><span class="sxs-lookup"><span data-stu-id="ce250-108">Columns</span></span>  
  
-   <span data-ttu-id="ce250-109">过程</span><span class="sxs-lookup"><span data-stu-id="ce250-109">Procedures</span></span>  
  
-   <span data-ttu-id="ce250-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ce250-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="ce250-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ce250-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="ce250-112">视图</span><span class="sxs-lookup"><span data-stu-id="ce250-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="ce250-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="ce250-113">Tables and Views</span></span>  
  
|<span data-ttu-id="ce250-114">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-114">ColumnName</span></span>|<span data-ttu-id="ce250-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="ce250-116">TABLE_CAT</span></span>|<span data-ttu-id="ce250-117">String</span><span class="sxs-lookup"><span data-stu-id="ce250-117">String</span></span>|  
|<span data-ttu-id="ce250-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ce250-118">TABLE_SCHEM</span></span>|<span data-ttu-id="ce250-119">String</span><span class="sxs-lookup"><span data-stu-id="ce250-119">String</span></span>|  
|<span data-ttu-id="ce250-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-120">TABLE_NAME</span></span>|<span data-ttu-id="ce250-121">String</span><span class="sxs-lookup"><span data-stu-id="ce250-121">String</span></span>|  
|<span data-ttu-id="ce250-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-122">TABLE_TYPE</span></span>|<span data-ttu-id="ce250-123">String</span><span class="sxs-lookup"><span data-stu-id="ce250-123">String</span></span>|  
|<span data-ttu-id="ce250-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-124">REMARKS</span></span>|<span data-ttu-id="ce250-125">String</span><span class="sxs-lookup"><span data-stu-id="ce250-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="ce250-126">索引</span><span class="sxs-lookup"><span data-stu-id="ce250-126">Indexes</span></span>  
  
|<span data-ttu-id="ce250-127">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-127">ColumnName</span></span>|<span data-ttu-id="ce250-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="ce250-129">TABLE_CAT</span></span>|<span data-ttu-id="ce250-130">String</span><span class="sxs-lookup"><span data-stu-id="ce250-130">String</span></span>|  
|<span data-ttu-id="ce250-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ce250-131">TABLE_SCHEM</span></span>|<span data-ttu-id="ce250-132">String</span><span class="sxs-lookup"><span data-stu-id="ce250-132">String</span></span>|  
|<span data-ttu-id="ce250-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-133">TABLE_NAME</span></span>|<span data-ttu-id="ce250-134">String</span><span class="sxs-lookup"><span data-stu-id="ce250-134">String</span></span>|  
|<span data-ttu-id="ce250-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="ce250-135">NON_UNIQUE</span></span>|<span data-ttu-id="ce250-136">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-136">Int16</span></span>|  
|<span data-ttu-id="ce250-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ce250-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="ce250-138">String</span><span class="sxs-lookup"><span data-stu-id="ce250-138">String</span></span>|  
|<span data-ttu-id="ce250-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-139">INDEX_NAME</span></span>|<span data-ttu-id="ce250-140">String</span><span class="sxs-lookup"><span data-stu-id="ce250-140">String</span></span>|  
|<span data-ttu-id="ce250-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-141">TYPE</span></span>|<span data-ttu-id="ce250-142">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-142">Int16</span></span>|  
|<span data-ttu-id="ce250-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ce250-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="ce250-144">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-144">Int16</span></span>|  
|<span data-ttu-id="ce250-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-145">COLUMN_NAME</span></span>|<span data-ttu-id="ce250-146">String</span><span class="sxs-lookup"><span data-stu-id="ce250-146">String</span></span>|  
|<span data-ttu-id="ce250-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="ce250-147">ASC_OR_DESC</span></span>|<span data-ttu-id="ce250-148">String</span><span class="sxs-lookup"><span data-stu-id="ce250-148">String</span></span>|  
|<span data-ttu-id="ce250-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="ce250-149">CARDINATLITY</span></span>|<span data-ttu-id="ce250-150">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-150">Int32</span></span>|  
|<span data-ttu-id="ce250-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="ce250-151">PAGES</span></span>|<span data-ttu-id="ce250-152">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-152">Int32</span></span>|  
|<span data-ttu-id="ce250-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="ce250-153">FILTER_CONDITION</span></span>|<span data-ttu-id="ce250-154">String</span><span class="sxs-lookup"><span data-stu-id="ce250-154">String</span></span>|  
|<span data-ttu-id="ce250-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ce250-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ce250-156">String</span><span class="sxs-lookup"><span data-stu-id="ce250-156">String</span></span>|  
|<span data-ttu-id="ce250-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="ce250-158">Byte</span><span class="sxs-lookup"><span data-stu-id="ce250-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="ce250-159">Columns</span><span class="sxs-lookup"><span data-stu-id="ce250-159">Columns</span></span>  
  
|<span data-ttu-id="ce250-160">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-160">ColumnName</span></span>|<span data-ttu-id="ce250-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="ce250-162">TABLE_CAT</span></span>|<span data-ttu-id="ce250-163">String</span><span class="sxs-lookup"><span data-stu-id="ce250-163">String</span></span>|  
|<span data-ttu-id="ce250-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ce250-164">TABLE_SCHEM</span></span>|<span data-ttu-id="ce250-165">String</span><span class="sxs-lookup"><span data-stu-id="ce250-165">String</span></span>|  
|<span data-ttu-id="ce250-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-166">TABLE_NAME</span></span>|<span data-ttu-id="ce250-167">String</span><span class="sxs-lookup"><span data-stu-id="ce250-167">String</span></span>|  
|<span data-ttu-id="ce250-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-168">COLUMN_NAME</span></span>|<span data-ttu-id="ce250-169">String</span><span class="sxs-lookup"><span data-stu-id="ce250-169">String</span></span>|  
|<span data-ttu-id="ce250-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-170">DATA_TYPE</span></span>|<span data-ttu-id="ce250-171">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-171">Int16</span></span>|  
|<span data-ttu-id="ce250-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-172">TYPE_NAME</span></span>|<span data-ttu-id="ce250-173">String</span><span class="sxs-lookup"><span data-stu-id="ce250-173">String</span></span>|  
|<span data-ttu-id="ce250-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ce250-174">COLUMN_SIZE</span></span>|<span data-ttu-id="ce250-175">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-175">Int32</span></span>|  
|<span data-ttu-id="ce250-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="ce250-177">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-177">Int32</span></span>|  
|<span data-ttu-id="ce250-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ce250-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ce250-179">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-179">Int16</span></span>|  
|<span data-ttu-id="ce250-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ce250-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ce250-181">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-181">Int16</span></span>|  
|<span data-ttu-id="ce250-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-182">NULLABLE</span></span>|<span data-ttu-id="ce250-183">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-183">Int16</span></span>|  
|<span data-ttu-id="ce250-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-184">REMARKS</span></span>|<span data-ttu-id="ce250-185">String</span><span class="sxs-lookup"><span data-stu-id="ce250-185">String</span></span>|  
|<span data-ttu-id="ce250-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ce250-186">COLUMN_DEF</span></span>|<span data-ttu-id="ce250-187">String</span><span class="sxs-lookup"><span data-stu-id="ce250-187">String</span></span>|  
|<span data-ttu-id="ce250-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ce250-189">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-189">Int16</span></span>|  
|<span data-ttu-id="ce250-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ce250-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ce250-191">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-191">Int16</span></span>|  
|<span data-ttu-id="ce250-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ce250-193">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-193">Int32</span></span>|  
|<span data-ttu-id="ce250-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ce250-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="ce250-195">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-195">Int32</span></span>|  
|<span data-ttu-id="ce250-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-196">IS_NULLABLE</span></span>|<span data-ttu-id="ce250-197">String</span><span class="sxs-lookup"><span data-stu-id="ce250-197">String</span></span>|  
|<span data-ttu-id="ce250-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ce250-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="ce250-199">String</span><span class="sxs-lookup"><span data-stu-id="ce250-199">String</span></span>|  
|<span data-ttu-id="ce250-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ce250-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ce250-201">String</span><span class="sxs-lookup"><span data-stu-id="ce250-201">String</span></span>|  
|<span data-ttu-id="ce250-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="ce250-203">Byte</span><span class="sxs-lookup"><span data-stu-id="ce250-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="ce250-204">过程</span><span class="sxs-lookup"><span data-stu-id="ce250-204">Procedures</span></span>  
  
|<span data-ttu-id="ce250-205">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-205">ColumnName</span></span>|<span data-ttu-id="ce250-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ce250-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="ce250-208">String</span><span class="sxs-lookup"><span data-stu-id="ce250-208">String</span></span>|  
|<span data-ttu-id="ce250-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ce250-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ce250-210">String</span><span class="sxs-lookup"><span data-stu-id="ce250-210">String</span></span>|  
|<span data-ttu-id="ce250-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="ce250-212">String</span><span class="sxs-lookup"><span data-stu-id="ce250-212">String</span></span>|  
|<span data-ttu-id="ce250-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ce250-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="ce250-214">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-214">Int32</span></span>|  
|<span data-ttu-id="ce250-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ce250-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="ce250-216">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-216">Int32</span></span>|  
|<span data-ttu-id="ce250-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="ce250-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="ce250-218">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-218">Int32</span></span>|  
|<span data-ttu-id="ce250-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-219">REMARKS</span></span>|<span data-ttu-id="ce250-220">String</span><span class="sxs-lookup"><span data-stu-id="ce250-220">String</span></span>|  
|<span data-ttu-id="ce250-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="ce250-222">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="ce250-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ce250-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="ce250-224">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-224">ColumnName</span></span>|<span data-ttu-id="ce250-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ce250-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="ce250-227">String</span><span class="sxs-lookup"><span data-stu-id="ce250-227">String</span></span>|  
|<span data-ttu-id="ce250-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ce250-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ce250-229">String</span><span class="sxs-lookup"><span data-stu-id="ce250-229">String</span></span>|  
|<span data-ttu-id="ce250-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="ce250-231">String</span><span class="sxs-lookup"><span data-stu-id="ce250-231">String</span></span>|  
|<span data-ttu-id="ce250-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-232">COLUMN_NAME</span></span>|<span data-ttu-id="ce250-233">String</span><span class="sxs-lookup"><span data-stu-id="ce250-233">String</span></span>|  
|<span data-ttu-id="ce250-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-234">COLUMN_TYPE</span></span>|<span data-ttu-id="ce250-235">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-235">Int16</span></span>|  
|<span data-ttu-id="ce250-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-236">DATA_TYPE</span></span>|<span data-ttu-id="ce250-237">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-237">Int16</span></span>|  
|<span data-ttu-id="ce250-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-238">TYPE_NAME</span></span>|<span data-ttu-id="ce250-239">String</span><span class="sxs-lookup"><span data-stu-id="ce250-239">String</span></span>|  
|<span data-ttu-id="ce250-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ce250-240">COLUMN_SIZE</span></span>|<span data-ttu-id="ce250-241">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-241">Int32</span></span>|  
|<span data-ttu-id="ce250-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="ce250-243">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-243">Int32</span></span>|  
|<span data-ttu-id="ce250-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ce250-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ce250-245">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-245">Int16</span></span>|  
|<span data-ttu-id="ce250-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ce250-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ce250-247">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-247">Int16</span></span>|  
|<span data-ttu-id="ce250-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-248">NULLABLE</span></span>|<span data-ttu-id="ce250-249">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-249">Int16</span></span>|  
|<span data-ttu-id="ce250-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-250">REMARKS</span></span>|<span data-ttu-id="ce250-251">String</span><span class="sxs-lookup"><span data-stu-id="ce250-251">String</span></span>|  
|<span data-ttu-id="ce250-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ce250-252">COLUMN_DEF</span></span>|<span data-ttu-id="ce250-253">String</span><span class="sxs-lookup"><span data-stu-id="ce250-253">String</span></span>|  
|<span data-ttu-id="ce250-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ce250-255">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-255">Int16</span></span>|  
|<span data-ttu-id="ce250-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ce250-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ce250-257">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-257">Int16</span></span>|  
|<span data-ttu-id="ce250-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ce250-259">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-259">Int32</span></span>|  
|<span data-ttu-id="ce250-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ce250-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="ce250-261">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-261">Int32</span></span>|  
|<span data-ttu-id="ce250-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-262">IS_NULLABLE</span></span>|<span data-ttu-id="ce250-263">String</span><span class="sxs-lookup"><span data-stu-id="ce250-263">String</span></span>|  
|<span data-ttu-id="ce250-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ce250-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="ce250-265">String</span><span class="sxs-lookup"><span data-stu-id="ce250-265">String</span></span>|  
|<span data-ttu-id="ce250-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ce250-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ce250-267">String</span><span class="sxs-lookup"><span data-stu-id="ce250-267">String</span></span>|  
|<span data-ttu-id="ce250-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="ce250-269">Byte</span><span class="sxs-lookup"><span data-stu-id="ce250-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="ce250-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ce250-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="ce250-271">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-271">ColumnName</span></span>|<span data-ttu-id="ce250-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ce250-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="ce250-274">String</span><span class="sxs-lookup"><span data-stu-id="ce250-274">String</span></span>|  
|<span data-ttu-id="ce250-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ce250-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ce250-276">String</span><span class="sxs-lookup"><span data-stu-id="ce250-276">String</span></span>|  
|<span data-ttu-id="ce250-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="ce250-278">String</span><span class="sxs-lookup"><span data-stu-id="ce250-278">String</span></span>|  
|<span data-ttu-id="ce250-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-279">COLUMN_NAME</span></span>|<span data-ttu-id="ce250-280">String</span><span class="sxs-lookup"><span data-stu-id="ce250-280">String</span></span>|  
|<span data-ttu-id="ce250-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-281">COLUMN_TYPE</span></span>|<span data-ttu-id="ce250-282">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-282">Int16</span></span>|  
|<span data-ttu-id="ce250-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-283">DATA_TYPE</span></span>|<span data-ttu-id="ce250-284">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-284">Int16</span></span>|  
|<span data-ttu-id="ce250-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-285">TYPE_NAME</span></span>|<span data-ttu-id="ce250-286">String</span><span class="sxs-lookup"><span data-stu-id="ce250-286">String</span></span>|  
|<span data-ttu-id="ce250-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ce250-287">COLUMN_SIZE</span></span>|<span data-ttu-id="ce250-288">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-288">Int32</span></span>|  
|<span data-ttu-id="ce250-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="ce250-290">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-290">Int32</span></span>|  
|<span data-ttu-id="ce250-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ce250-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ce250-292">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-292">Int16</span></span>|  
|<span data-ttu-id="ce250-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ce250-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ce250-294">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-294">Int16</span></span>|  
|<span data-ttu-id="ce250-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-295">NULLABLE</span></span>|<span data-ttu-id="ce250-296">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-296">Int16</span></span>|  
|<span data-ttu-id="ce250-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-297">REMARKS</span></span>|<span data-ttu-id="ce250-298">String</span><span class="sxs-lookup"><span data-stu-id="ce250-298">String</span></span>|  
|<span data-ttu-id="ce250-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ce250-299">COLUMN_DEF</span></span>|<span data-ttu-id="ce250-300">String</span><span class="sxs-lookup"><span data-stu-id="ce250-300">String</span></span>|  
|<span data-ttu-id="ce250-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ce250-302">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-302">Int16</span></span>|  
|<span data-ttu-id="ce250-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ce250-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ce250-304">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-304">Int16</span></span>|  
|<span data-ttu-id="ce250-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ce250-306">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-306">Int32</span></span>|  
|<span data-ttu-id="ce250-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ce250-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="ce250-308">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-308">Int32</span></span>|  
|<span data-ttu-id="ce250-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-309">IS_NULLABLE</span></span>|<span data-ttu-id="ce250-310">String</span><span class="sxs-lookup"><span data-stu-id="ce250-310">String</span></span>|  
|<span data-ttu-id="ce250-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ce250-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="ce250-312">String</span><span class="sxs-lookup"><span data-stu-id="ce250-312">String</span></span>|  
|<span data-ttu-id="ce250-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ce250-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ce250-314">String</span><span class="sxs-lookup"><span data-stu-id="ce250-314">String</span></span>|  
|<span data-ttu-id="ce250-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="ce250-316">Byte</span><span class="sxs-lookup"><span data-stu-id="ce250-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="ce250-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="ce250-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="ce250-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="ce250-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="ce250-319">表</span><span class="sxs-lookup"><span data-stu-id="ce250-319">Tables</span></span>  
  
-   <span data-ttu-id="ce250-320">Columns</span><span class="sxs-lookup"><span data-stu-id="ce250-320">Columns</span></span>  
  
-   <span data-ttu-id="ce250-321">过程</span><span class="sxs-lookup"><span data-stu-id="ce250-321">Procedures</span></span>  
  
-   <span data-ttu-id="ce250-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ce250-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="ce250-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ce250-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="ce250-324">视图</span><span class="sxs-lookup"><span data-stu-id="ce250-324">Views</span></span>  
  
-   <span data-ttu-id="ce250-325">索引</span><span class="sxs-lookup"><span data-stu-id="ce250-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="ce250-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="ce250-326">Tables and Views</span></span>  
  
|<span data-ttu-id="ce250-327">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-327">ColumnName</span></span>|<span data-ttu-id="ce250-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ce250-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ce250-330">String</span><span class="sxs-lookup"><span data-stu-id="ce250-330">String</span></span>|  
|<span data-ttu-id="ce250-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce250-331">TABLE_OWNER</span></span>|<span data-ttu-id="ce250-332">String</span><span class="sxs-lookup"><span data-stu-id="ce250-332">String</span></span>|  
|<span data-ttu-id="ce250-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-333">TABLE_NAME</span></span>|<span data-ttu-id="ce250-334">String</span><span class="sxs-lookup"><span data-stu-id="ce250-334">String</span></span>|  
|<span data-ttu-id="ce250-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-335">TABLE_TYPE</span></span>|<span data-ttu-id="ce250-336">String</span><span class="sxs-lookup"><span data-stu-id="ce250-336">String</span></span>|  
|<span data-ttu-id="ce250-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-337">REMARKS</span></span>|<span data-ttu-id="ce250-338">String</span><span class="sxs-lookup"><span data-stu-id="ce250-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="ce250-339">Columns</span><span class="sxs-lookup"><span data-stu-id="ce250-339">Columns</span></span>  
  
|<span data-ttu-id="ce250-340">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-340">ColumnName</span></span>|<span data-ttu-id="ce250-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ce250-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ce250-343">String</span><span class="sxs-lookup"><span data-stu-id="ce250-343">String</span></span>|  
|<span data-ttu-id="ce250-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce250-344">TABLE_OWNER</span></span>|<span data-ttu-id="ce250-345">String</span><span class="sxs-lookup"><span data-stu-id="ce250-345">String</span></span>|  
|<span data-ttu-id="ce250-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-346">TABLE_NAME</span></span>|<span data-ttu-id="ce250-347">String</span><span class="sxs-lookup"><span data-stu-id="ce250-347">String</span></span>|  
|<span data-ttu-id="ce250-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-348">COLUMN_NAME</span></span>|<span data-ttu-id="ce250-349">String</span><span class="sxs-lookup"><span data-stu-id="ce250-349">String</span></span>|  
|<span data-ttu-id="ce250-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-350">DATA_TYPE</span></span>|<span data-ttu-id="ce250-351">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-351">Int16</span></span>|  
|<span data-ttu-id="ce250-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-352">TYPE_NAME</span></span>|<span data-ttu-id="ce250-353">String</span><span class="sxs-lookup"><span data-stu-id="ce250-353">String</span></span>|  
|<span data-ttu-id="ce250-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ce250-354">PRECISION</span></span>|<span data-ttu-id="ce250-355">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-355">Int32</span></span>|  
|<span data-ttu-id="ce250-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-356">LENGTH</span></span>|<span data-ttu-id="ce250-357">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-357">Int32</span></span>|  
|<span data-ttu-id="ce250-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="ce250-358">SCALE</span></span>|<span data-ttu-id="ce250-359">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-359">Int16</span></span>|  
|<span data-ttu-id="ce250-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="ce250-360">RADIX</span></span>|<span data-ttu-id="ce250-361">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-361">Int16</span></span>|  
|<span data-ttu-id="ce250-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-362">NULLABLE</span></span>|<span data-ttu-id="ce250-363">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-363">Int16</span></span>|  
|<span data-ttu-id="ce250-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-364">REMARKS</span></span>|<span data-ttu-id="ce250-365">String</span><span class="sxs-lookup"><span data-stu-id="ce250-365">String</span></span>|  
|<span data-ttu-id="ce250-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ce250-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="ce250-367">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="ce250-368">过程</span><span class="sxs-lookup"><span data-stu-id="ce250-368">Procedures</span></span>  
  
|<span data-ttu-id="ce250-369">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-369">ColumnName</span></span>|<span data-ttu-id="ce250-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ce250-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ce250-372">String</span><span class="sxs-lookup"><span data-stu-id="ce250-372">String</span></span>|  
|<span data-ttu-id="ce250-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce250-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ce250-374">String</span><span class="sxs-lookup"><span data-stu-id="ce250-374">String</span></span>|  
|<span data-ttu-id="ce250-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="ce250-376">String</span><span class="sxs-lookup"><span data-stu-id="ce250-376">String</span></span>|  
|<span data-ttu-id="ce250-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ce250-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="ce250-378">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-378">Int16</span></span>|  
|<span data-ttu-id="ce250-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ce250-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="ce250-380">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-380">Int16</span></span>|  
|<span data-ttu-id="ce250-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="ce250-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="ce250-382">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-382">Int16</span></span>|  
|<span data-ttu-id="ce250-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-383">REMARKS</span></span>|<span data-ttu-id="ce250-384">String</span><span class="sxs-lookup"><span data-stu-id="ce250-384">String</span></span>|  
|<span data-ttu-id="ce250-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="ce250-386">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="ce250-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ce250-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="ce250-388">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-388">ColumnName</span></span>|<span data-ttu-id="ce250-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ce250-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ce250-391">String</span><span class="sxs-lookup"><span data-stu-id="ce250-391">String</span></span>|  
|<span data-ttu-id="ce250-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce250-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ce250-393">String</span><span class="sxs-lookup"><span data-stu-id="ce250-393">String</span></span>|  
|<span data-ttu-id="ce250-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="ce250-395">String</span><span class="sxs-lookup"><span data-stu-id="ce250-395">String</span></span>|  
|<span data-ttu-id="ce250-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-396">COLUMN_NAME</span></span>|<span data-ttu-id="ce250-397">String</span><span class="sxs-lookup"><span data-stu-id="ce250-397">String</span></span>|  
|<span data-ttu-id="ce250-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-398">COLUMN_TYPE</span></span>|<span data-ttu-id="ce250-399">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-399">Int16</span></span>|  
|<span data-ttu-id="ce250-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-400">DATA_TYPE</span></span>|<span data-ttu-id="ce250-401">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-401">Int16</span></span>|  
|<span data-ttu-id="ce250-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-402">TYPE_NAME</span></span>|<span data-ttu-id="ce250-403">String</span><span class="sxs-lookup"><span data-stu-id="ce250-403">String</span></span>|  
|<span data-ttu-id="ce250-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ce250-404">PRECISION</span></span>|<span data-ttu-id="ce250-405">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-405">Int32</span></span>|  
|<span data-ttu-id="ce250-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-406">LENGTH</span></span>|<span data-ttu-id="ce250-407">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-407">Int32</span></span>|  
|<span data-ttu-id="ce250-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="ce250-408">SCALE</span></span>|<span data-ttu-id="ce250-409">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-409">Int16</span></span>|  
|<span data-ttu-id="ce250-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="ce250-410">RADIX</span></span>|<span data-ttu-id="ce250-411">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-411">Int16</span></span>|  
|<span data-ttu-id="ce250-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-412">NULLABLE</span></span>|<span data-ttu-id="ce250-413">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-413">Int16</span></span>|  
|<span data-ttu-id="ce250-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-414">REMARKS</span></span>|<span data-ttu-id="ce250-415">String</span><span class="sxs-lookup"><span data-stu-id="ce250-415">String</span></span>|  
|<span data-ttu-id="ce250-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="ce250-416">OVERLOAD</span></span>|<span data-ttu-id="ce250-417">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-417">Int32</span></span>|  
|<span data-ttu-id="ce250-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ce250-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="ce250-419">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="ce250-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="ce250-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="ce250-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="ce250-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="ce250-422">表</span><span class="sxs-lookup"><span data-stu-id="ce250-422">Tables</span></span>  
  
-   <span data-ttu-id="ce250-423">索引</span><span class="sxs-lookup"><span data-stu-id="ce250-423">Indexes</span></span>  
  
-   <span data-ttu-id="ce250-424">Columns</span><span class="sxs-lookup"><span data-stu-id="ce250-424">Columns</span></span>  
  
-   <span data-ttu-id="ce250-425">过程</span><span class="sxs-lookup"><span data-stu-id="ce250-425">Procedures</span></span>  
  
-   <span data-ttu-id="ce250-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ce250-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="ce250-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ce250-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="ce250-428">视图</span><span class="sxs-lookup"><span data-stu-id="ce250-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="ce250-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="ce250-429">Tables and Views</span></span>  
  
|<span data-ttu-id="ce250-430">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-430">ColumnName</span></span>|<span data-ttu-id="ce250-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ce250-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ce250-433">String</span><span class="sxs-lookup"><span data-stu-id="ce250-433">String</span></span>|  
|<span data-ttu-id="ce250-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce250-434">TABLE_OWNER</span></span>|<span data-ttu-id="ce250-435">String</span><span class="sxs-lookup"><span data-stu-id="ce250-435">String</span></span>|  
|<span data-ttu-id="ce250-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-436">TABLE_NAME</span></span>|<span data-ttu-id="ce250-437">String</span><span class="sxs-lookup"><span data-stu-id="ce250-437">String</span></span>|  
|<span data-ttu-id="ce250-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-438">TABLE_TYPE</span></span>|<span data-ttu-id="ce250-439">String</span><span class="sxs-lookup"><span data-stu-id="ce250-439">String</span></span>|  
|<span data-ttu-id="ce250-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-440">REMARKS</span></span>|<span data-ttu-id="ce250-441">String</span><span class="sxs-lookup"><span data-stu-id="ce250-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="ce250-442">Columns</span><span class="sxs-lookup"><span data-stu-id="ce250-442">Columns</span></span>  
  
|<span data-ttu-id="ce250-443">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-443">ColumnName</span></span>|<span data-ttu-id="ce250-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ce250-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ce250-446">String</span><span class="sxs-lookup"><span data-stu-id="ce250-446">String</span></span>|  
|<span data-ttu-id="ce250-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce250-447">TABLE_OWNER</span></span>|<span data-ttu-id="ce250-448">String</span><span class="sxs-lookup"><span data-stu-id="ce250-448">String</span></span>|  
|<span data-ttu-id="ce250-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-449">TABLE_NAME</span></span>|<span data-ttu-id="ce250-450">String</span><span class="sxs-lookup"><span data-stu-id="ce250-450">String</span></span>|  
|<span data-ttu-id="ce250-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-451">COLUMN_NAME</span></span>|<span data-ttu-id="ce250-452">String</span><span class="sxs-lookup"><span data-stu-id="ce250-452">String</span></span>|  
|<span data-ttu-id="ce250-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-453">DATA_TYPE</span></span>|<span data-ttu-id="ce250-454">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-454">Int16</span></span>|  
|<span data-ttu-id="ce250-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-455">TYPE_NAME</span></span>|<span data-ttu-id="ce250-456">String</span><span class="sxs-lookup"><span data-stu-id="ce250-456">String</span></span>|  
|<span data-ttu-id="ce250-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ce250-457">PRECISION</span></span>|<span data-ttu-id="ce250-458">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-458">Int32</span></span>|  
|<span data-ttu-id="ce250-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-459">LENGTH</span></span>|<span data-ttu-id="ce250-460">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-460">Int32</span></span>|  
|<span data-ttu-id="ce250-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="ce250-461">SCALE</span></span>|<span data-ttu-id="ce250-462">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-462">Int16</span></span>|  
|<span data-ttu-id="ce250-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="ce250-463">RADIX</span></span>|<span data-ttu-id="ce250-464">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-464">Int16</span></span>|  
|<span data-ttu-id="ce250-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-465">NULLABLE</span></span>|<span data-ttu-id="ce250-466">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-466">Int16</span></span>|  
|<span data-ttu-id="ce250-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-467">REMARKS</span></span>|<span data-ttu-id="ce250-468">String</span><span class="sxs-lookup"><span data-stu-id="ce250-468">String</span></span>|  
|<span data-ttu-id="ce250-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ce250-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="ce250-470">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="ce250-471">过程</span><span class="sxs-lookup"><span data-stu-id="ce250-471">Procedures</span></span>  
  
|<span data-ttu-id="ce250-472">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-472">ColumnName</span></span>|<span data-ttu-id="ce250-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ce250-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ce250-475">String</span><span class="sxs-lookup"><span data-stu-id="ce250-475">String</span></span>|  
|<span data-ttu-id="ce250-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce250-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ce250-477">String</span><span class="sxs-lookup"><span data-stu-id="ce250-477">String</span></span>|  
|<span data-ttu-id="ce250-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="ce250-479">String</span><span class="sxs-lookup"><span data-stu-id="ce250-479">String</span></span>|  
|<span data-ttu-id="ce250-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ce250-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="ce250-481">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-481">Int16</span></span>|  
|<span data-ttu-id="ce250-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ce250-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="ce250-483">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-483">Int16</span></span>|  
|<span data-ttu-id="ce250-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="ce250-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="ce250-485">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-485">Int16</span></span>|  
|<span data-ttu-id="ce250-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-486">REMARKS</span></span>|<span data-ttu-id="ce250-487">String</span><span class="sxs-lookup"><span data-stu-id="ce250-487">String</span></span>|  
|<span data-ttu-id="ce250-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="ce250-489">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="ce250-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ce250-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="ce250-491">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-491">ColumnName</span></span>|<span data-ttu-id="ce250-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ce250-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ce250-494">String</span><span class="sxs-lookup"><span data-stu-id="ce250-494">String</span></span>|  
|<span data-ttu-id="ce250-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce250-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ce250-496">String</span><span class="sxs-lookup"><span data-stu-id="ce250-496">String</span></span>|  
|<span data-ttu-id="ce250-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="ce250-498">String</span><span class="sxs-lookup"><span data-stu-id="ce250-498">String</span></span>|  
|<span data-ttu-id="ce250-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-499">COLUMN_NAME</span></span>|<span data-ttu-id="ce250-500">String</span><span class="sxs-lookup"><span data-stu-id="ce250-500">String</span></span>|  
|<span data-ttu-id="ce250-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-501">COLUMN_TYPE</span></span>|<span data-ttu-id="ce250-502">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-502">Int16</span></span>|  
|<span data-ttu-id="ce250-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-503">DATA_TYPE</span></span>|<span data-ttu-id="ce250-504">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-504">Int16</span></span>|  
|<span data-ttu-id="ce250-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-505">TYPE_NAME</span></span>|<span data-ttu-id="ce250-506">String</span><span class="sxs-lookup"><span data-stu-id="ce250-506">String</span></span>|  
|<span data-ttu-id="ce250-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ce250-507">PRECISION</span></span>|<span data-ttu-id="ce250-508">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-508">Int32</span></span>|  
|<span data-ttu-id="ce250-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-509">LENGTH</span></span>|<span data-ttu-id="ce250-510">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-510">Int32</span></span>|  
|<span data-ttu-id="ce250-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="ce250-511">SCALE</span></span>|<span data-ttu-id="ce250-512">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-512">Int16</span></span>|  
|<span data-ttu-id="ce250-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="ce250-513">RADIX</span></span>|<span data-ttu-id="ce250-514">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-514">Int16</span></span>|  
|<span data-ttu-id="ce250-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-515">NULLABLE</span></span>|<span data-ttu-id="ce250-516">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-516">Int16</span></span>|  
|<span data-ttu-id="ce250-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-517">REMARKS</span></span>|<span data-ttu-id="ce250-518">String</span><span class="sxs-lookup"><span data-stu-id="ce250-518">String</span></span>|  
|<span data-ttu-id="ce250-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="ce250-519">OVERLOAD</span></span>|<span data-ttu-id="ce250-520">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-520">Int32</span></span>|  
|<span data-ttu-id="ce250-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ce250-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="ce250-522">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="ce250-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ce250-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="ce250-524">列名</span><span class="sxs-lookup"><span data-stu-id="ce250-524">ColumnName</span></span>|<span data-ttu-id="ce250-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="ce250-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ce250-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ce250-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="ce250-527">String</span><span class="sxs-lookup"><span data-stu-id="ce250-527">String</span></span>|  
|<span data-ttu-id="ce250-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ce250-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ce250-529">String</span><span class="sxs-lookup"><span data-stu-id="ce250-529">String</span></span>|  
|<span data-ttu-id="ce250-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="ce250-531">String</span><span class="sxs-lookup"><span data-stu-id="ce250-531">String</span></span>|  
|<span data-ttu-id="ce250-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-532">COLUMN_NAME</span></span>|<span data-ttu-id="ce250-533">String</span><span class="sxs-lookup"><span data-stu-id="ce250-533">String</span></span>|  
|<span data-ttu-id="ce250-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-534">COLUMN_TYPE</span></span>|<span data-ttu-id="ce250-535">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-535">Int16</span></span>|  
|<span data-ttu-id="ce250-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-536">DATA_TYPE</span></span>|<span data-ttu-id="ce250-537">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-537">Int16</span></span>|  
|<span data-ttu-id="ce250-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ce250-538">TYPE_NAME</span></span>|<span data-ttu-id="ce250-539">String</span><span class="sxs-lookup"><span data-stu-id="ce250-539">String</span></span>|  
|<span data-ttu-id="ce250-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ce250-540">COLUMN_SIZE</span></span>|<span data-ttu-id="ce250-541">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-541">Int32</span></span>|  
|<span data-ttu-id="ce250-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="ce250-543">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-543">Int32</span></span>|  
|<span data-ttu-id="ce250-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ce250-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ce250-545">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-545">Int16</span></span>|  
|<span data-ttu-id="ce250-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ce250-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ce250-547">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-547">Int16</span></span>|  
|<span data-ttu-id="ce250-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-548">NULLABLE</span></span>|<span data-ttu-id="ce250-549">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-549">Int16</span></span>|  
|<span data-ttu-id="ce250-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ce250-550">REMARKS</span></span>|<span data-ttu-id="ce250-551">String</span><span class="sxs-lookup"><span data-stu-id="ce250-551">String</span></span>|  
|<span data-ttu-id="ce250-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ce250-552">COLUMN_DEF</span></span>|<span data-ttu-id="ce250-553">String</span><span class="sxs-lookup"><span data-stu-id="ce250-553">String</span></span>|  
|<span data-ttu-id="ce250-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ce250-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ce250-555">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-555">Int16</span></span>|  
|<span data-ttu-id="ce250-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ce250-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ce250-557">Int16</span><span class="sxs-lookup"><span data-stu-id="ce250-557">Int16</span></span>|  
|<span data-ttu-id="ce250-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ce250-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ce250-559">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-559">Int32</span></span>|  
|<span data-ttu-id="ce250-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ce250-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="ce250-561">Int32</span><span class="sxs-lookup"><span data-stu-id="ce250-561">Int32</span></span>|  
|<span data-ttu-id="ce250-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ce250-562">IS_NULLABLE</span></span>|<span data-ttu-id="ce250-563">String</span><span class="sxs-lookup"><span data-stu-id="ce250-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce250-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce250-564">See also</span></span>
- [<span data-ttu-id="ce250-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ce250-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
