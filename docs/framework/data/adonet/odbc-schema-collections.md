---
title: ODBC 架构集合
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43750004"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="852a0-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="852a0-102">ODBC Schema Collections</span></span>
<span data-ttu-id="852a0-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="852a0-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="852a0-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="852a0-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="852a0-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="852a0-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="852a0-106">表</span><span class="sxs-lookup"><span data-stu-id="852a0-106">Tables</span></span>  
  
-   <span data-ttu-id="852a0-107">索引</span><span class="sxs-lookup"><span data-stu-id="852a0-107">Indexes</span></span>  
  
-   <span data-ttu-id="852a0-108">Columns</span><span class="sxs-lookup"><span data-stu-id="852a0-108">Columns</span></span>  
  
-   <span data-ttu-id="852a0-109">过程</span><span class="sxs-lookup"><span data-stu-id="852a0-109">Procedures</span></span>  
  
-   <span data-ttu-id="852a0-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="852a0-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="852a0-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="852a0-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="852a0-112">视图</span><span class="sxs-lookup"><span data-stu-id="852a0-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="852a0-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="852a0-113">Tables and Views</span></span>  
  
|<span data-ttu-id="852a0-114">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-114">ColumnName</span></span>|<span data-ttu-id="852a0-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="852a0-116">TABLE_CAT</span></span>|<span data-ttu-id="852a0-117">String</span><span class="sxs-lookup"><span data-stu-id="852a0-117">String</span></span>|  
|<span data-ttu-id="852a0-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="852a0-118">TABLE_SCHEM</span></span>|<span data-ttu-id="852a0-119">String</span><span class="sxs-lookup"><span data-stu-id="852a0-119">String</span></span>|  
|<span data-ttu-id="852a0-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-120">TABLE_NAME</span></span>|<span data-ttu-id="852a0-121">String</span><span class="sxs-lookup"><span data-stu-id="852a0-121">String</span></span>|  
|<span data-ttu-id="852a0-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-122">TABLE_TYPE</span></span>|<span data-ttu-id="852a0-123">String</span><span class="sxs-lookup"><span data-stu-id="852a0-123">String</span></span>|  
|<span data-ttu-id="852a0-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-124">REMARKS</span></span>|<span data-ttu-id="852a0-125">String</span><span class="sxs-lookup"><span data-stu-id="852a0-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="852a0-126">索引</span><span class="sxs-lookup"><span data-stu-id="852a0-126">Indexes</span></span>  
  
|<span data-ttu-id="852a0-127">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-127">ColumnName</span></span>|<span data-ttu-id="852a0-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="852a0-129">TABLE_CAT</span></span>|<span data-ttu-id="852a0-130">String</span><span class="sxs-lookup"><span data-stu-id="852a0-130">String</span></span>|  
|<span data-ttu-id="852a0-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="852a0-131">TABLE_SCHEM</span></span>|<span data-ttu-id="852a0-132">String</span><span class="sxs-lookup"><span data-stu-id="852a0-132">String</span></span>|  
|<span data-ttu-id="852a0-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-133">TABLE_NAME</span></span>|<span data-ttu-id="852a0-134">String</span><span class="sxs-lookup"><span data-stu-id="852a0-134">String</span></span>|  
|<span data-ttu-id="852a0-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="852a0-135">NON_UNIQUE</span></span>|<span data-ttu-id="852a0-136">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-136">Int16</span></span>|  
|<span data-ttu-id="852a0-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="852a0-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="852a0-138">String</span><span class="sxs-lookup"><span data-stu-id="852a0-138">String</span></span>|  
|<span data-ttu-id="852a0-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-139">INDEX_NAME</span></span>|<span data-ttu-id="852a0-140">String</span><span class="sxs-lookup"><span data-stu-id="852a0-140">String</span></span>|  
|<span data-ttu-id="852a0-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-141">TYPE</span></span>|<span data-ttu-id="852a0-142">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-142">Int16</span></span>|  
|<span data-ttu-id="852a0-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="852a0-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="852a0-144">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-144">Int16</span></span>|  
|<span data-ttu-id="852a0-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-145">COLUMN_NAME</span></span>|<span data-ttu-id="852a0-146">String</span><span class="sxs-lookup"><span data-stu-id="852a0-146">String</span></span>|  
|<span data-ttu-id="852a0-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="852a0-147">ASC_OR_DESC</span></span>|<span data-ttu-id="852a0-148">String</span><span class="sxs-lookup"><span data-stu-id="852a0-148">String</span></span>|  
|<span data-ttu-id="852a0-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="852a0-149">CARDINATLITY</span></span>|<span data-ttu-id="852a0-150">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-150">Int32</span></span>|  
|<span data-ttu-id="852a0-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="852a0-151">PAGES</span></span>|<span data-ttu-id="852a0-152">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-152">Int32</span></span>|  
|<span data-ttu-id="852a0-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="852a0-153">FILTER_CONDITION</span></span>|<span data-ttu-id="852a0-154">String</span><span class="sxs-lookup"><span data-stu-id="852a0-154">String</span></span>|  
|<span data-ttu-id="852a0-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="852a0-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="852a0-156">String</span><span class="sxs-lookup"><span data-stu-id="852a0-156">String</span></span>|  
|<span data-ttu-id="852a0-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="852a0-158">Byte</span><span class="sxs-lookup"><span data-stu-id="852a0-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="852a0-159">Columns</span><span class="sxs-lookup"><span data-stu-id="852a0-159">Columns</span></span>  
  
|<span data-ttu-id="852a0-160">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-160">ColumnName</span></span>|<span data-ttu-id="852a0-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="852a0-162">TABLE_CAT</span></span>|<span data-ttu-id="852a0-163">String</span><span class="sxs-lookup"><span data-stu-id="852a0-163">String</span></span>|  
|<span data-ttu-id="852a0-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="852a0-164">TABLE_SCHEM</span></span>|<span data-ttu-id="852a0-165">String</span><span class="sxs-lookup"><span data-stu-id="852a0-165">String</span></span>|  
|<span data-ttu-id="852a0-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-166">TABLE_NAME</span></span>|<span data-ttu-id="852a0-167">String</span><span class="sxs-lookup"><span data-stu-id="852a0-167">String</span></span>|  
|<span data-ttu-id="852a0-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-168">COLUMN_NAME</span></span>|<span data-ttu-id="852a0-169">String</span><span class="sxs-lookup"><span data-stu-id="852a0-169">String</span></span>|  
|<span data-ttu-id="852a0-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-170">DATA_TYPE</span></span>|<span data-ttu-id="852a0-171">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-171">Int16</span></span>|  
|<span data-ttu-id="852a0-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-172">TYPE_NAME</span></span>|<span data-ttu-id="852a0-173">String</span><span class="sxs-lookup"><span data-stu-id="852a0-173">String</span></span>|  
|<span data-ttu-id="852a0-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="852a0-174">COLUMN_SIZE</span></span>|<span data-ttu-id="852a0-175">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-175">Int32</span></span>|  
|<span data-ttu-id="852a0-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="852a0-177">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-177">Int32</span></span>|  
|<span data-ttu-id="852a0-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="852a0-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="852a0-179">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-179">Int16</span></span>|  
|<span data-ttu-id="852a0-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="852a0-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="852a0-181">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-181">Int16</span></span>|  
|<span data-ttu-id="852a0-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-182">NULLABLE</span></span>|<span data-ttu-id="852a0-183">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-183">Int16</span></span>|  
|<span data-ttu-id="852a0-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-184">REMARKS</span></span>|<span data-ttu-id="852a0-185">String</span><span class="sxs-lookup"><span data-stu-id="852a0-185">String</span></span>|  
|<span data-ttu-id="852a0-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="852a0-186">COLUMN_DEF</span></span>|<span data-ttu-id="852a0-187">String</span><span class="sxs-lookup"><span data-stu-id="852a0-187">String</span></span>|  
|<span data-ttu-id="852a0-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="852a0-189">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-189">Int16</span></span>|  
|<span data-ttu-id="852a0-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="852a0-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="852a0-191">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-191">Int16</span></span>|  
|<span data-ttu-id="852a0-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="852a0-193">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-193">Int32</span></span>|  
|<span data-ttu-id="852a0-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="852a0-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="852a0-195">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-195">Int32</span></span>|  
|<span data-ttu-id="852a0-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-196">IS_NULLABLE</span></span>|<span data-ttu-id="852a0-197">String</span><span class="sxs-lookup"><span data-stu-id="852a0-197">String</span></span>|  
|<span data-ttu-id="852a0-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="852a0-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="852a0-199">String</span><span class="sxs-lookup"><span data-stu-id="852a0-199">String</span></span>|  
|<span data-ttu-id="852a0-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="852a0-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="852a0-201">String</span><span class="sxs-lookup"><span data-stu-id="852a0-201">String</span></span>|  
|<span data-ttu-id="852a0-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="852a0-203">Byte</span><span class="sxs-lookup"><span data-stu-id="852a0-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="852a0-204">过程</span><span class="sxs-lookup"><span data-stu-id="852a0-204">Procedures</span></span>  
  
|<span data-ttu-id="852a0-205">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-205">ColumnName</span></span>|<span data-ttu-id="852a0-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="852a0-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="852a0-208">String</span><span class="sxs-lookup"><span data-stu-id="852a0-208">String</span></span>|  
|<span data-ttu-id="852a0-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="852a0-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="852a0-210">String</span><span class="sxs-lookup"><span data-stu-id="852a0-210">String</span></span>|  
|<span data-ttu-id="852a0-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="852a0-212">String</span><span class="sxs-lookup"><span data-stu-id="852a0-212">String</span></span>|  
|<span data-ttu-id="852a0-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="852a0-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="852a0-214">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-214">Int32</span></span>|  
|<span data-ttu-id="852a0-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="852a0-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="852a0-216">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-216">Int32</span></span>|  
|<span data-ttu-id="852a0-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="852a0-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="852a0-218">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-218">Int32</span></span>|  
|<span data-ttu-id="852a0-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-219">REMARKS</span></span>|<span data-ttu-id="852a0-220">String</span><span class="sxs-lookup"><span data-stu-id="852a0-220">String</span></span>|  
|<span data-ttu-id="852a0-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="852a0-222">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="852a0-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="852a0-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="852a0-224">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-224">ColumnName</span></span>|<span data-ttu-id="852a0-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="852a0-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="852a0-227">String</span><span class="sxs-lookup"><span data-stu-id="852a0-227">String</span></span>|  
|<span data-ttu-id="852a0-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="852a0-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="852a0-229">String</span><span class="sxs-lookup"><span data-stu-id="852a0-229">String</span></span>|  
|<span data-ttu-id="852a0-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="852a0-231">String</span><span class="sxs-lookup"><span data-stu-id="852a0-231">String</span></span>|  
|<span data-ttu-id="852a0-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-232">COLUMN_NAME</span></span>|<span data-ttu-id="852a0-233">String</span><span class="sxs-lookup"><span data-stu-id="852a0-233">String</span></span>|  
|<span data-ttu-id="852a0-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-234">COLUMN_TYPE</span></span>|<span data-ttu-id="852a0-235">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-235">Int16</span></span>|  
|<span data-ttu-id="852a0-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-236">DATA_TYPE</span></span>|<span data-ttu-id="852a0-237">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-237">Int16</span></span>|  
|<span data-ttu-id="852a0-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-238">TYPE_NAME</span></span>|<span data-ttu-id="852a0-239">String</span><span class="sxs-lookup"><span data-stu-id="852a0-239">String</span></span>|  
|<span data-ttu-id="852a0-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="852a0-240">COLUMN_SIZE</span></span>|<span data-ttu-id="852a0-241">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-241">Int32</span></span>|  
|<span data-ttu-id="852a0-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="852a0-243">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-243">Int32</span></span>|  
|<span data-ttu-id="852a0-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="852a0-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="852a0-245">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-245">Int16</span></span>|  
|<span data-ttu-id="852a0-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="852a0-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="852a0-247">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-247">Int16</span></span>|  
|<span data-ttu-id="852a0-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-248">NULLABLE</span></span>|<span data-ttu-id="852a0-249">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-249">Int16</span></span>|  
|<span data-ttu-id="852a0-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-250">REMARKS</span></span>|<span data-ttu-id="852a0-251">String</span><span class="sxs-lookup"><span data-stu-id="852a0-251">String</span></span>|  
|<span data-ttu-id="852a0-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="852a0-252">COLUMN_DEF</span></span>|<span data-ttu-id="852a0-253">String</span><span class="sxs-lookup"><span data-stu-id="852a0-253">String</span></span>|  
|<span data-ttu-id="852a0-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="852a0-255">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-255">Int16</span></span>|  
|<span data-ttu-id="852a0-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="852a0-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="852a0-257">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-257">Int16</span></span>|  
|<span data-ttu-id="852a0-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="852a0-259">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-259">Int32</span></span>|  
|<span data-ttu-id="852a0-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="852a0-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="852a0-261">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-261">Int32</span></span>|  
|<span data-ttu-id="852a0-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-262">IS_NULLABLE</span></span>|<span data-ttu-id="852a0-263">String</span><span class="sxs-lookup"><span data-stu-id="852a0-263">String</span></span>|  
|<span data-ttu-id="852a0-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="852a0-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="852a0-265">String</span><span class="sxs-lookup"><span data-stu-id="852a0-265">String</span></span>|  
|<span data-ttu-id="852a0-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="852a0-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="852a0-267">String</span><span class="sxs-lookup"><span data-stu-id="852a0-267">String</span></span>|  
|<span data-ttu-id="852a0-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="852a0-269">Byte</span><span class="sxs-lookup"><span data-stu-id="852a0-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="852a0-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="852a0-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="852a0-271">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-271">ColumnName</span></span>|<span data-ttu-id="852a0-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="852a0-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="852a0-274">String</span><span class="sxs-lookup"><span data-stu-id="852a0-274">String</span></span>|  
|<span data-ttu-id="852a0-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="852a0-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="852a0-276">String</span><span class="sxs-lookup"><span data-stu-id="852a0-276">String</span></span>|  
|<span data-ttu-id="852a0-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="852a0-278">String</span><span class="sxs-lookup"><span data-stu-id="852a0-278">String</span></span>|  
|<span data-ttu-id="852a0-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-279">COLUMN_NAME</span></span>|<span data-ttu-id="852a0-280">String</span><span class="sxs-lookup"><span data-stu-id="852a0-280">String</span></span>|  
|<span data-ttu-id="852a0-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-281">COLUMN_TYPE</span></span>|<span data-ttu-id="852a0-282">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-282">Int16</span></span>|  
|<span data-ttu-id="852a0-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-283">DATA_TYPE</span></span>|<span data-ttu-id="852a0-284">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-284">Int16</span></span>|  
|<span data-ttu-id="852a0-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-285">TYPE_NAME</span></span>|<span data-ttu-id="852a0-286">String</span><span class="sxs-lookup"><span data-stu-id="852a0-286">String</span></span>|  
|<span data-ttu-id="852a0-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="852a0-287">COLUMN_SIZE</span></span>|<span data-ttu-id="852a0-288">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-288">Int32</span></span>|  
|<span data-ttu-id="852a0-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="852a0-290">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-290">Int32</span></span>|  
|<span data-ttu-id="852a0-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="852a0-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="852a0-292">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-292">Int16</span></span>|  
|<span data-ttu-id="852a0-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="852a0-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="852a0-294">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-294">Int16</span></span>|  
|<span data-ttu-id="852a0-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-295">NULLABLE</span></span>|<span data-ttu-id="852a0-296">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-296">Int16</span></span>|  
|<span data-ttu-id="852a0-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-297">REMARKS</span></span>|<span data-ttu-id="852a0-298">String</span><span class="sxs-lookup"><span data-stu-id="852a0-298">String</span></span>|  
|<span data-ttu-id="852a0-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="852a0-299">COLUMN_DEF</span></span>|<span data-ttu-id="852a0-300">String</span><span class="sxs-lookup"><span data-stu-id="852a0-300">String</span></span>|  
|<span data-ttu-id="852a0-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="852a0-302">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-302">Int16</span></span>|  
|<span data-ttu-id="852a0-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="852a0-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="852a0-304">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-304">Int16</span></span>|  
|<span data-ttu-id="852a0-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="852a0-306">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-306">Int32</span></span>|  
|<span data-ttu-id="852a0-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="852a0-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="852a0-308">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-308">Int32</span></span>|  
|<span data-ttu-id="852a0-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-309">IS_NULLABLE</span></span>|<span data-ttu-id="852a0-310">String</span><span class="sxs-lookup"><span data-stu-id="852a0-310">String</span></span>|  
|<span data-ttu-id="852a0-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="852a0-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="852a0-312">String</span><span class="sxs-lookup"><span data-stu-id="852a0-312">String</span></span>|  
|<span data-ttu-id="852a0-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="852a0-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="852a0-314">String</span><span class="sxs-lookup"><span data-stu-id="852a0-314">String</span></span>|  
|<span data-ttu-id="852a0-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="852a0-316">Byte</span><span class="sxs-lookup"><span data-stu-id="852a0-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="852a0-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="852a0-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="852a0-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="852a0-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="852a0-319">表</span><span class="sxs-lookup"><span data-stu-id="852a0-319">Tables</span></span>  
  
-   <span data-ttu-id="852a0-320">Columns</span><span class="sxs-lookup"><span data-stu-id="852a0-320">Columns</span></span>  
  
-   <span data-ttu-id="852a0-321">过程</span><span class="sxs-lookup"><span data-stu-id="852a0-321">Procedures</span></span>  
  
-   <span data-ttu-id="852a0-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="852a0-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="852a0-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="852a0-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="852a0-324">视图</span><span class="sxs-lookup"><span data-stu-id="852a0-324">Views</span></span>  
  
-   <span data-ttu-id="852a0-325">索引</span><span class="sxs-lookup"><span data-stu-id="852a0-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="852a0-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="852a0-326">Tables and Views</span></span>  
  
|<span data-ttu-id="852a0-327">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-327">ColumnName</span></span>|<span data-ttu-id="852a0-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="852a0-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="852a0-330">String</span><span class="sxs-lookup"><span data-stu-id="852a0-330">String</span></span>|  
|<span data-ttu-id="852a0-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="852a0-331">TABLE_OWNER</span></span>|<span data-ttu-id="852a0-332">String</span><span class="sxs-lookup"><span data-stu-id="852a0-332">String</span></span>|  
|<span data-ttu-id="852a0-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-333">TABLE_NAME</span></span>|<span data-ttu-id="852a0-334">String</span><span class="sxs-lookup"><span data-stu-id="852a0-334">String</span></span>|  
|<span data-ttu-id="852a0-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-335">TABLE_TYPE</span></span>|<span data-ttu-id="852a0-336">String</span><span class="sxs-lookup"><span data-stu-id="852a0-336">String</span></span>|  
|<span data-ttu-id="852a0-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-337">REMARKS</span></span>|<span data-ttu-id="852a0-338">String</span><span class="sxs-lookup"><span data-stu-id="852a0-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="852a0-339">Columns</span><span class="sxs-lookup"><span data-stu-id="852a0-339">Columns</span></span>  
  
|<span data-ttu-id="852a0-340">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-340">ColumnName</span></span>|<span data-ttu-id="852a0-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="852a0-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="852a0-343">String</span><span class="sxs-lookup"><span data-stu-id="852a0-343">String</span></span>|  
|<span data-ttu-id="852a0-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="852a0-344">TABLE_OWNER</span></span>|<span data-ttu-id="852a0-345">String</span><span class="sxs-lookup"><span data-stu-id="852a0-345">String</span></span>|  
|<span data-ttu-id="852a0-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-346">TABLE_NAME</span></span>|<span data-ttu-id="852a0-347">String</span><span class="sxs-lookup"><span data-stu-id="852a0-347">String</span></span>|  
|<span data-ttu-id="852a0-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-348">COLUMN_NAME</span></span>|<span data-ttu-id="852a0-349">String</span><span class="sxs-lookup"><span data-stu-id="852a0-349">String</span></span>|  
|<span data-ttu-id="852a0-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-350">DATA_TYPE</span></span>|<span data-ttu-id="852a0-351">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-351">Int16</span></span>|  
|<span data-ttu-id="852a0-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-352">TYPE_NAME</span></span>|<span data-ttu-id="852a0-353">String</span><span class="sxs-lookup"><span data-stu-id="852a0-353">String</span></span>|  
|<span data-ttu-id="852a0-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="852a0-354">PRECISION</span></span>|<span data-ttu-id="852a0-355">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-355">Int32</span></span>|  
|<span data-ttu-id="852a0-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-356">LENGTH</span></span>|<span data-ttu-id="852a0-357">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-357">Int32</span></span>|  
|<span data-ttu-id="852a0-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="852a0-358">SCALE</span></span>|<span data-ttu-id="852a0-359">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-359">Int16</span></span>|  
|<span data-ttu-id="852a0-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="852a0-360">RADIX</span></span>|<span data-ttu-id="852a0-361">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-361">Int16</span></span>|  
|<span data-ttu-id="852a0-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-362">NULLABLE</span></span>|<span data-ttu-id="852a0-363">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-363">Int16</span></span>|  
|<span data-ttu-id="852a0-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-364">REMARKS</span></span>|<span data-ttu-id="852a0-365">String</span><span class="sxs-lookup"><span data-stu-id="852a0-365">String</span></span>|  
|<span data-ttu-id="852a0-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="852a0-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="852a0-367">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="852a0-368">过程</span><span class="sxs-lookup"><span data-stu-id="852a0-368">Procedures</span></span>  
  
|<span data-ttu-id="852a0-369">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-369">ColumnName</span></span>|<span data-ttu-id="852a0-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="852a0-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="852a0-372">String</span><span class="sxs-lookup"><span data-stu-id="852a0-372">String</span></span>|  
|<span data-ttu-id="852a0-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="852a0-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="852a0-374">String</span><span class="sxs-lookup"><span data-stu-id="852a0-374">String</span></span>|  
|<span data-ttu-id="852a0-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="852a0-376">String</span><span class="sxs-lookup"><span data-stu-id="852a0-376">String</span></span>|  
|<span data-ttu-id="852a0-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="852a0-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="852a0-378">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-378">Int16</span></span>|  
|<span data-ttu-id="852a0-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="852a0-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="852a0-380">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-380">Int16</span></span>|  
|<span data-ttu-id="852a0-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="852a0-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="852a0-382">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-382">Int16</span></span>|  
|<span data-ttu-id="852a0-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-383">REMARKS</span></span>|<span data-ttu-id="852a0-384">String</span><span class="sxs-lookup"><span data-stu-id="852a0-384">String</span></span>|  
|<span data-ttu-id="852a0-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="852a0-386">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="852a0-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="852a0-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="852a0-388">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-388">ColumnName</span></span>|<span data-ttu-id="852a0-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="852a0-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="852a0-391">String</span><span class="sxs-lookup"><span data-stu-id="852a0-391">String</span></span>|  
|<span data-ttu-id="852a0-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="852a0-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="852a0-393">String</span><span class="sxs-lookup"><span data-stu-id="852a0-393">String</span></span>|  
|<span data-ttu-id="852a0-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="852a0-395">String</span><span class="sxs-lookup"><span data-stu-id="852a0-395">String</span></span>|  
|<span data-ttu-id="852a0-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-396">COLUMN_NAME</span></span>|<span data-ttu-id="852a0-397">String</span><span class="sxs-lookup"><span data-stu-id="852a0-397">String</span></span>|  
|<span data-ttu-id="852a0-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-398">COLUMN_TYPE</span></span>|<span data-ttu-id="852a0-399">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-399">Int16</span></span>|  
|<span data-ttu-id="852a0-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-400">DATA_TYPE</span></span>|<span data-ttu-id="852a0-401">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-401">Int16</span></span>|  
|<span data-ttu-id="852a0-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-402">TYPE_NAME</span></span>|<span data-ttu-id="852a0-403">String</span><span class="sxs-lookup"><span data-stu-id="852a0-403">String</span></span>|  
|<span data-ttu-id="852a0-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="852a0-404">PRECISION</span></span>|<span data-ttu-id="852a0-405">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-405">Int32</span></span>|  
|<span data-ttu-id="852a0-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-406">LENGTH</span></span>|<span data-ttu-id="852a0-407">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-407">Int32</span></span>|  
|<span data-ttu-id="852a0-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="852a0-408">SCALE</span></span>|<span data-ttu-id="852a0-409">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-409">Int16</span></span>|  
|<span data-ttu-id="852a0-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="852a0-410">RADIX</span></span>|<span data-ttu-id="852a0-411">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-411">Int16</span></span>|  
|<span data-ttu-id="852a0-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-412">NULLABLE</span></span>|<span data-ttu-id="852a0-413">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-413">Int16</span></span>|  
|<span data-ttu-id="852a0-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-414">REMARKS</span></span>|<span data-ttu-id="852a0-415">String</span><span class="sxs-lookup"><span data-stu-id="852a0-415">String</span></span>|  
|<span data-ttu-id="852a0-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="852a0-416">OVERLOAD</span></span>|<span data-ttu-id="852a0-417">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-417">Int32</span></span>|  
|<span data-ttu-id="852a0-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="852a0-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="852a0-419">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="852a0-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="852a0-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="852a0-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="852a0-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="852a0-422">表</span><span class="sxs-lookup"><span data-stu-id="852a0-422">Tables</span></span>  
  
-   <span data-ttu-id="852a0-423">索引</span><span class="sxs-lookup"><span data-stu-id="852a0-423">Indexes</span></span>  
  
-   <span data-ttu-id="852a0-424">Columns</span><span class="sxs-lookup"><span data-stu-id="852a0-424">Columns</span></span>  
  
-   <span data-ttu-id="852a0-425">过程</span><span class="sxs-lookup"><span data-stu-id="852a0-425">Procedures</span></span>  
  
-   <span data-ttu-id="852a0-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="852a0-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="852a0-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="852a0-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="852a0-428">视图</span><span class="sxs-lookup"><span data-stu-id="852a0-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="852a0-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="852a0-429">Tables and Views</span></span>  
  
|<span data-ttu-id="852a0-430">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-430">ColumnName</span></span>|<span data-ttu-id="852a0-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="852a0-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="852a0-433">String</span><span class="sxs-lookup"><span data-stu-id="852a0-433">String</span></span>|  
|<span data-ttu-id="852a0-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="852a0-434">TABLE_OWNER</span></span>|<span data-ttu-id="852a0-435">String</span><span class="sxs-lookup"><span data-stu-id="852a0-435">String</span></span>|  
|<span data-ttu-id="852a0-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-436">TABLE_NAME</span></span>|<span data-ttu-id="852a0-437">String</span><span class="sxs-lookup"><span data-stu-id="852a0-437">String</span></span>|  
|<span data-ttu-id="852a0-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-438">TABLE_TYPE</span></span>|<span data-ttu-id="852a0-439">String</span><span class="sxs-lookup"><span data-stu-id="852a0-439">String</span></span>|  
|<span data-ttu-id="852a0-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-440">REMARKS</span></span>|<span data-ttu-id="852a0-441">String</span><span class="sxs-lookup"><span data-stu-id="852a0-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="852a0-442">Columns</span><span class="sxs-lookup"><span data-stu-id="852a0-442">Columns</span></span>  
  
|<span data-ttu-id="852a0-443">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-443">ColumnName</span></span>|<span data-ttu-id="852a0-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="852a0-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="852a0-446">String</span><span class="sxs-lookup"><span data-stu-id="852a0-446">String</span></span>|  
|<span data-ttu-id="852a0-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="852a0-447">TABLE_OWNER</span></span>|<span data-ttu-id="852a0-448">String</span><span class="sxs-lookup"><span data-stu-id="852a0-448">String</span></span>|  
|<span data-ttu-id="852a0-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-449">TABLE_NAME</span></span>|<span data-ttu-id="852a0-450">String</span><span class="sxs-lookup"><span data-stu-id="852a0-450">String</span></span>|  
|<span data-ttu-id="852a0-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-451">COLUMN_NAME</span></span>|<span data-ttu-id="852a0-452">String</span><span class="sxs-lookup"><span data-stu-id="852a0-452">String</span></span>|  
|<span data-ttu-id="852a0-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-453">DATA_TYPE</span></span>|<span data-ttu-id="852a0-454">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-454">Int16</span></span>|  
|<span data-ttu-id="852a0-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-455">TYPE_NAME</span></span>|<span data-ttu-id="852a0-456">String</span><span class="sxs-lookup"><span data-stu-id="852a0-456">String</span></span>|  
|<span data-ttu-id="852a0-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="852a0-457">PRECISION</span></span>|<span data-ttu-id="852a0-458">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-458">Int32</span></span>|  
|<span data-ttu-id="852a0-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-459">LENGTH</span></span>|<span data-ttu-id="852a0-460">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-460">Int32</span></span>|  
|<span data-ttu-id="852a0-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="852a0-461">SCALE</span></span>|<span data-ttu-id="852a0-462">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-462">Int16</span></span>|  
|<span data-ttu-id="852a0-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="852a0-463">RADIX</span></span>|<span data-ttu-id="852a0-464">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-464">Int16</span></span>|  
|<span data-ttu-id="852a0-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-465">NULLABLE</span></span>|<span data-ttu-id="852a0-466">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-466">Int16</span></span>|  
|<span data-ttu-id="852a0-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-467">REMARKS</span></span>|<span data-ttu-id="852a0-468">String</span><span class="sxs-lookup"><span data-stu-id="852a0-468">String</span></span>|  
|<span data-ttu-id="852a0-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="852a0-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="852a0-470">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="852a0-471">过程</span><span class="sxs-lookup"><span data-stu-id="852a0-471">Procedures</span></span>  
  
|<span data-ttu-id="852a0-472">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-472">ColumnName</span></span>|<span data-ttu-id="852a0-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="852a0-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="852a0-475">String</span><span class="sxs-lookup"><span data-stu-id="852a0-475">String</span></span>|  
|<span data-ttu-id="852a0-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="852a0-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="852a0-477">String</span><span class="sxs-lookup"><span data-stu-id="852a0-477">String</span></span>|  
|<span data-ttu-id="852a0-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="852a0-479">String</span><span class="sxs-lookup"><span data-stu-id="852a0-479">String</span></span>|  
|<span data-ttu-id="852a0-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="852a0-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="852a0-481">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-481">Int16</span></span>|  
|<span data-ttu-id="852a0-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="852a0-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="852a0-483">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-483">Int16</span></span>|  
|<span data-ttu-id="852a0-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="852a0-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="852a0-485">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-485">Int16</span></span>|  
|<span data-ttu-id="852a0-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-486">REMARKS</span></span>|<span data-ttu-id="852a0-487">String</span><span class="sxs-lookup"><span data-stu-id="852a0-487">String</span></span>|  
|<span data-ttu-id="852a0-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="852a0-489">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="852a0-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="852a0-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="852a0-491">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-491">ColumnName</span></span>|<span data-ttu-id="852a0-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="852a0-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="852a0-494">String</span><span class="sxs-lookup"><span data-stu-id="852a0-494">String</span></span>|  
|<span data-ttu-id="852a0-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="852a0-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="852a0-496">String</span><span class="sxs-lookup"><span data-stu-id="852a0-496">String</span></span>|  
|<span data-ttu-id="852a0-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="852a0-498">String</span><span class="sxs-lookup"><span data-stu-id="852a0-498">String</span></span>|  
|<span data-ttu-id="852a0-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-499">COLUMN_NAME</span></span>|<span data-ttu-id="852a0-500">String</span><span class="sxs-lookup"><span data-stu-id="852a0-500">String</span></span>|  
|<span data-ttu-id="852a0-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-501">COLUMN_TYPE</span></span>|<span data-ttu-id="852a0-502">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-502">Int16</span></span>|  
|<span data-ttu-id="852a0-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-503">DATA_TYPE</span></span>|<span data-ttu-id="852a0-504">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-504">Int16</span></span>|  
|<span data-ttu-id="852a0-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-505">TYPE_NAME</span></span>|<span data-ttu-id="852a0-506">String</span><span class="sxs-lookup"><span data-stu-id="852a0-506">String</span></span>|  
|<span data-ttu-id="852a0-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="852a0-507">PRECISION</span></span>|<span data-ttu-id="852a0-508">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-508">Int32</span></span>|  
|<span data-ttu-id="852a0-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-509">LENGTH</span></span>|<span data-ttu-id="852a0-510">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-510">Int32</span></span>|  
|<span data-ttu-id="852a0-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="852a0-511">SCALE</span></span>|<span data-ttu-id="852a0-512">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-512">Int16</span></span>|  
|<span data-ttu-id="852a0-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="852a0-513">RADIX</span></span>|<span data-ttu-id="852a0-514">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-514">Int16</span></span>|  
|<span data-ttu-id="852a0-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-515">NULLABLE</span></span>|<span data-ttu-id="852a0-516">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-516">Int16</span></span>|  
|<span data-ttu-id="852a0-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-517">REMARKS</span></span>|<span data-ttu-id="852a0-518">String</span><span class="sxs-lookup"><span data-stu-id="852a0-518">String</span></span>|  
|<span data-ttu-id="852a0-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="852a0-519">OVERLOAD</span></span>|<span data-ttu-id="852a0-520">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-520">Int32</span></span>|  
|<span data-ttu-id="852a0-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="852a0-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="852a0-522">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="852a0-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="852a0-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="852a0-524">列名</span><span class="sxs-lookup"><span data-stu-id="852a0-524">ColumnName</span></span>|<span data-ttu-id="852a0-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="852a0-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="852a0-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="852a0-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="852a0-527">String</span><span class="sxs-lookup"><span data-stu-id="852a0-527">String</span></span>|  
|<span data-ttu-id="852a0-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="852a0-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="852a0-529">String</span><span class="sxs-lookup"><span data-stu-id="852a0-529">String</span></span>|  
|<span data-ttu-id="852a0-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="852a0-531">String</span><span class="sxs-lookup"><span data-stu-id="852a0-531">String</span></span>|  
|<span data-ttu-id="852a0-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-532">COLUMN_NAME</span></span>|<span data-ttu-id="852a0-533">String</span><span class="sxs-lookup"><span data-stu-id="852a0-533">String</span></span>|  
|<span data-ttu-id="852a0-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-534">COLUMN_TYPE</span></span>|<span data-ttu-id="852a0-535">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-535">Int16</span></span>|  
|<span data-ttu-id="852a0-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-536">DATA_TYPE</span></span>|<span data-ttu-id="852a0-537">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-537">Int16</span></span>|  
|<span data-ttu-id="852a0-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="852a0-538">TYPE_NAME</span></span>|<span data-ttu-id="852a0-539">String</span><span class="sxs-lookup"><span data-stu-id="852a0-539">String</span></span>|  
|<span data-ttu-id="852a0-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="852a0-540">COLUMN_SIZE</span></span>|<span data-ttu-id="852a0-541">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-541">Int32</span></span>|  
|<span data-ttu-id="852a0-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="852a0-543">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-543">Int32</span></span>|  
|<span data-ttu-id="852a0-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="852a0-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="852a0-545">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-545">Int16</span></span>|  
|<span data-ttu-id="852a0-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="852a0-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="852a0-547">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-547">Int16</span></span>|  
|<span data-ttu-id="852a0-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-548">NULLABLE</span></span>|<span data-ttu-id="852a0-549">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-549">Int16</span></span>|  
|<span data-ttu-id="852a0-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="852a0-550">REMARKS</span></span>|<span data-ttu-id="852a0-551">String</span><span class="sxs-lookup"><span data-stu-id="852a0-551">String</span></span>|  
|<span data-ttu-id="852a0-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="852a0-552">COLUMN_DEF</span></span>|<span data-ttu-id="852a0-553">String</span><span class="sxs-lookup"><span data-stu-id="852a0-553">String</span></span>|  
|<span data-ttu-id="852a0-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="852a0-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="852a0-555">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-555">Int16</span></span>|  
|<span data-ttu-id="852a0-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="852a0-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="852a0-557">Int16</span><span class="sxs-lookup"><span data-stu-id="852a0-557">Int16</span></span>|  
|<span data-ttu-id="852a0-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="852a0-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="852a0-559">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-559">Int32</span></span>|  
|<span data-ttu-id="852a0-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="852a0-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="852a0-561">Int32</span><span class="sxs-lookup"><span data-stu-id="852a0-561">Int32</span></span>|  
|<span data-ttu-id="852a0-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="852a0-562">IS_NULLABLE</span></span>|<span data-ttu-id="852a0-563">String</span><span class="sxs-lookup"><span data-stu-id="852a0-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="852a0-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="852a0-564">See Also</span></span>  
 [<span data-ttu-id="852a0-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="852a0-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
