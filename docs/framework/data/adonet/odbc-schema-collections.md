---
title: ODBC 架构集合
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772042"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="88d60-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="88d60-102">ODBC Schema Collections</span></span>

<span data-ttu-id="88d60-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="88d60-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="88d60-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="88d60-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="88d60-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="88d60-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="88d60-106">表</span><span class="sxs-lookup"><span data-stu-id="88d60-106">Tables</span></span>

- <span data-ttu-id="88d60-107">索引</span><span class="sxs-lookup"><span data-stu-id="88d60-107">Indexes</span></span>

- <span data-ttu-id="88d60-108">列</span><span class="sxs-lookup"><span data-stu-id="88d60-108">Columns</span></span>

- <span data-ttu-id="88d60-109">过程</span><span class="sxs-lookup"><span data-stu-id="88d60-109">Procedures</span></span>

- <span data-ttu-id="88d60-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="88d60-110">ProcedureColumns</span></span>

- <span data-ttu-id="88d60-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="88d60-111">ProcedureParameters</span></span>

- <span data-ttu-id="88d60-112">Views</span><span class="sxs-lookup"><span data-stu-id="88d60-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="88d60-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="88d60-113">Tables and Views</span></span>

|<span data-ttu-id="88d60-114">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-114">ColumnName</span></span>|<span data-ttu-id="88d60-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="88d60-116">TABLE_CAT</span></span>|<span data-ttu-id="88d60-117">String</span><span class="sxs-lookup"><span data-stu-id="88d60-117">String</span></span>|
|<span data-ttu-id="88d60-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="88d60-118">TABLE_SCHEM</span></span>|<span data-ttu-id="88d60-119">String</span><span class="sxs-lookup"><span data-stu-id="88d60-119">String</span></span>|
|<span data-ttu-id="88d60-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-120">TABLE_NAME</span></span>|<span data-ttu-id="88d60-121">String</span><span class="sxs-lookup"><span data-stu-id="88d60-121">String</span></span>|
|<span data-ttu-id="88d60-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-122">TABLE_TYPE</span></span>|<span data-ttu-id="88d60-123">String</span><span class="sxs-lookup"><span data-stu-id="88d60-123">String</span></span>|
|<span data-ttu-id="88d60-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-124">REMARKS</span></span>|<span data-ttu-id="88d60-125">String</span><span class="sxs-lookup"><span data-stu-id="88d60-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="88d60-126">索引</span><span class="sxs-lookup"><span data-stu-id="88d60-126">Indexes</span></span>

|<span data-ttu-id="88d60-127">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-127">ColumnName</span></span>|<span data-ttu-id="88d60-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="88d60-129">TABLE_CAT</span></span>|<span data-ttu-id="88d60-130">String</span><span class="sxs-lookup"><span data-stu-id="88d60-130">String</span></span>|
|<span data-ttu-id="88d60-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="88d60-131">TABLE_SCHEM</span></span>|<span data-ttu-id="88d60-132">String</span><span class="sxs-lookup"><span data-stu-id="88d60-132">String</span></span>|
|<span data-ttu-id="88d60-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-133">TABLE_NAME</span></span>|<span data-ttu-id="88d60-134">String</span><span class="sxs-lookup"><span data-stu-id="88d60-134">String</span></span>|
|<span data-ttu-id="88d60-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="88d60-135">NON_UNIQUE</span></span>|<span data-ttu-id="88d60-136">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-136">Int16</span></span>|
|<span data-ttu-id="88d60-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="88d60-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="88d60-138">String</span><span class="sxs-lookup"><span data-stu-id="88d60-138">String</span></span>|
|<span data-ttu-id="88d60-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-139">INDEX_NAME</span></span>|<span data-ttu-id="88d60-140">String</span><span class="sxs-lookup"><span data-stu-id="88d60-140">String</span></span>|
|<span data-ttu-id="88d60-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-141">TYPE</span></span>|<span data-ttu-id="88d60-142">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-142">Int16</span></span>|
|<span data-ttu-id="88d60-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="88d60-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="88d60-144">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-144">Int16</span></span>|
|<span data-ttu-id="88d60-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-145">COLUMN_NAME</span></span>|<span data-ttu-id="88d60-146">String</span><span class="sxs-lookup"><span data-stu-id="88d60-146">String</span></span>|
|<span data-ttu-id="88d60-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="88d60-147">ASC_OR_DESC</span></span>|<span data-ttu-id="88d60-148">String</span><span class="sxs-lookup"><span data-stu-id="88d60-148">String</span></span>|
|<span data-ttu-id="88d60-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="88d60-149">CARDINALITY</span></span>|<span data-ttu-id="88d60-150">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-150">Int32</span></span>|
|<span data-ttu-id="88d60-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="88d60-151">PAGES</span></span>|<span data-ttu-id="88d60-152">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-152">Int32</span></span>|
|<span data-ttu-id="88d60-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="88d60-153">FILTER_CONDITION</span></span>|<span data-ttu-id="88d60-154">String</span><span class="sxs-lookup"><span data-stu-id="88d60-154">String</span></span>|
|<span data-ttu-id="88d60-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="88d60-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="88d60-156">String</span><span class="sxs-lookup"><span data-stu-id="88d60-156">String</span></span>|
|<span data-ttu-id="88d60-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="88d60-158">Byte</span><span class="sxs-lookup"><span data-stu-id="88d60-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="88d60-159">列</span><span class="sxs-lookup"><span data-stu-id="88d60-159">Columns</span></span>

|<span data-ttu-id="88d60-160">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-160">ColumnName</span></span>|<span data-ttu-id="88d60-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="88d60-162">TABLE_CAT</span></span>|<span data-ttu-id="88d60-163">String</span><span class="sxs-lookup"><span data-stu-id="88d60-163">String</span></span>|
|<span data-ttu-id="88d60-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="88d60-164">TABLE_SCHEM</span></span>|<span data-ttu-id="88d60-165">String</span><span class="sxs-lookup"><span data-stu-id="88d60-165">String</span></span>|
|<span data-ttu-id="88d60-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-166">TABLE_NAME</span></span>|<span data-ttu-id="88d60-167">String</span><span class="sxs-lookup"><span data-stu-id="88d60-167">String</span></span>|
|<span data-ttu-id="88d60-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-168">COLUMN_NAME</span></span>|<span data-ttu-id="88d60-169">String</span><span class="sxs-lookup"><span data-stu-id="88d60-169">String</span></span>|
|<span data-ttu-id="88d60-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-170">DATA_TYPE</span></span>|<span data-ttu-id="88d60-171">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-171">Int16</span></span>|
|<span data-ttu-id="88d60-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-172">TYPE_NAME</span></span>|<span data-ttu-id="88d60-173">String</span><span class="sxs-lookup"><span data-stu-id="88d60-173">String</span></span>|
|<span data-ttu-id="88d60-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="88d60-174">COLUMN_SIZE</span></span>|<span data-ttu-id="88d60-175">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-175">Int32</span></span>|
|<span data-ttu-id="88d60-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="88d60-177">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-177">Int32</span></span>|
|<span data-ttu-id="88d60-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="88d60-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="88d60-179">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-179">Int16</span></span>|
|<span data-ttu-id="88d60-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="88d60-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="88d60-181">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-181">Int16</span></span>|
|<span data-ttu-id="88d60-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-182">NULLABLE</span></span>|<span data-ttu-id="88d60-183">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-183">Int16</span></span>|
|<span data-ttu-id="88d60-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-184">REMARKS</span></span>|<span data-ttu-id="88d60-185">String</span><span class="sxs-lookup"><span data-stu-id="88d60-185">String</span></span>|
|<span data-ttu-id="88d60-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="88d60-186">COLUMN_DEF</span></span>|<span data-ttu-id="88d60-187">String</span><span class="sxs-lookup"><span data-stu-id="88d60-187">String</span></span>|
|<span data-ttu-id="88d60-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="88d60-189">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-189">Int16</span></span>|
|<span data-ttu-id="88d60-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="88d60-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="88d60-191">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-191">Int16</span></span>|
|<span data-ttu-id="88d60-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="88d60-193">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-193">Int32</span></span>|
|<span data-ttu-id="88d60-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="88d60-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="88d60-195">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-195">Int32</span></span>|
|<span data-ttu-id="88d60-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-196">IS_NULLABLE</span></span>|<span data-ttu-id="88d60-197">String</span><span class="sxs-lookup"><span data-stu-id="88d60-197">String</span></span>|
|<span data-ttu-id="88d60-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="88d60-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="88d60-199">String</span><span class="sxs-lookup"><span data-stu-id="88d60-199">String</span></span>|
|<span data-ttu-id="88d60-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="88d60-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="88d60-201">String</span><span class="sxs-lookup"><span data-stu-id="88d60-201">String</span></span>|
|<span data-ttu-id="88d60-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="88d60-203">Byte</span><span class="sxs-lookup"><span data-stu-id="88d60-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="88d60-204">过程</span><span class="sxs-lookup"><span data-stu-id="88d60-204">Procedures</span></span>

|<span data-ttu-id="88d60-205">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-205">ColumnName</span></span>|<span data-ttu-id="88d60-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="88d60-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="88d60-208">String</span><span class="sxs-lookup"><span data-stu-id="88d60-208">String</span></span>|
|<span data-ttu-id="88d60-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="88d60-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="88d60-210">String</span><span class="sxs-lookup"><span data-stu-id="88d60-210">String</span></span>|
|<span data-ttu-id="88d60-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="88d60-212">String</span><span class="sxs-lookup"><span data-stu-id="88d60-212">String</span></span>|
|<span data-ttu-id="88d60-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="88d60-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="88d60-214">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-214">Int32</span></span>|
|<span data-ttu-id="88d60-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="88d60-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="88d60-216">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-216">Int32</span></span>|
|<span data-ttu-id="88d60-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="88d60-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="88d60-218">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-218">Int32</span></span>|
|<span data-ttu-id="88d60-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-219">REMARKS</span></span>|<span data-ttu-id="88d60-220">String</span><span class="sxs-lookup"><span data-stu-id="88d60-220">String</span></span>|
|<span data-ttu-id="88d60-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="88d60-222">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="88d60-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="88d60-223">ProcedureColumns</span></span>

|<span data-ttu-id="88d60-224">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-224">ColumnName</span></span>|<span data-ttu-id="88d60-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="88d60-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="88d60-227">String</span><span class="sxs-lookup"><span data-stu-id="88d60-227">String</span></span>|
|<span data-ttu-id="88d60-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="88d60-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="88d60-229">String</span><span class="sxs-lookup"><span data-stu-id="88d60-229">String</span></span>|
|<span data-ttu-id="88d60-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="88d60-231">String</span><span class="sxs-lookup"><span data-stu-id="88d60-231">String</span></span>|
|<span data-ttu-id="88d60-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-232">COLUMN_NAME</span></span>|<span data-ttu-id="88d60-233">String</span><span class="sxs-lookup"><span data-stu-id="88d60-233">String</span></span>|
|<span data-ttu-id="88d60-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-234">COLUMN_TYPE</span></span>|<span data-ttu-id="88d60-235">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-235">Int16</span></span>|
|<span data-ttu-id="88d60-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-236">DATA_TYPE</span></span>|<span data-ttu-id="88d60-237">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-237">Int16</span></span>|
|<span data-ttu-id="88d60-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-238">TYPE_NAME</span></span>|<span data-ttu-id="88d60-239">String</span><span class="sxs-lookup"><span data-stu-id="88d60-239">String</span></span>|
|<span data-ttu-id="88d60-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="88d60-240">COLUMN_SIZE</span></span>|<span data-ttu-id="88d60-241">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-241">Int32</span></span>|
|<span data-ttu-id="88d60-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="88d60-243">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-243">Int32</span></span>|
|<span data-ttu-id="88d60-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="88d60-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="88d60-245">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-245">Int16</span></span>|
|<span data-ttu-id="88d60-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="88d60-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="88d60-247">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-247">Int16</span></span>|
|<span data-ttu-id="88d60-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-248">NULLABLE</span></span>|<span data-ttu-id="88d60-249">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-249">Int16</span></span>|
|<span data-ttu-id="88d60-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-250">REMARKS</span></span>|<span data-ttu-id="88d60-251">String</span><span class="sxs-lookup"><span data-stu-id="88d60-251">String</span></span>|
|<span data-ttu-id="88d60-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="88d60-252">COLUMN_DEF</span></span>|<span data-ttu-id="88d60-253">String</span><span class="sxs-lookup"><span data-stu-id="88d60-253">String</span></span>|
|<span data-ttu-id="88d60-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="88d60-255">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-255">Int16</span></span>|
|<span data-ttu-id="88d60-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="88d60-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="88d60-257">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-257">Int16</span></span>|
|<span data-ttu-id="88d60-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="88d60-259">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-259">Int32</span></span>|
|<span data-ttu-id="88d60-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="88d60-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="88d60-261">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-261">Int32</span></span>|
|<span data-ttu-id="88d60-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-262">IS_NULLABLE</span></span>|<span data-ttu-id="88d60-263">String</span><span class="sxs-lookup"><span data-stu-id="88d60-263">String</span></span>|
|<span data-ttu-id="88d60-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="88d60-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="88d60-265">String</span><span class="sxs-lookup"><span data-stu-id="88d60-265">String</span></span>|
|<span data-ttu-id="88d60-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="88d60-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="88d60-267">String</span><span class="sxs-lookup"><span data-stu-id="88d60-267">String</span></span>|
|<span data-ttu-id="88d60-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="88d60-269">Byte</span><span class="sxs-lookup"><span data-stu-id="88d60-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="88d60-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="88d60-270">ProcedureParameters</span></span>

|<span data-ttu-id="88d60-271">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-271">ColumnName</span></span>|<span data-ttu-id="88d60-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="88d60-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="88d60-274">String</span><span class="sxs-lookup"><span data-stu-id="88d60-274">String</span></span>|
|<span data-ttu-id="88d60-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="88d60-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="88d60-276">String</span><span class="sxs-lookup"><span data-stu-id="88d60-276">String</span></span>|
|<span data-ttu-id="88d60-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="88d60-278">String</span><span class="sxs-lookup"><span data-stu-id="88d60-278">String</span></span>|
|<span data-ttu-id="88d60-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-279">COLUMN_NAME</span></span>|<span data-ttu-id="88d60-280">String</span><span class="sxs-lookup"><span data-stu-id="88d60-280">String</span></span>|
|<span data-ttu-id="88d60-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-281">COLUMN_TYPE</span></span>|<span data-ttu-id="88d60-282">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-282">Int16</span></span>|
|<span data-ttu-id="88d60-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-283">DATA_TYPE</span></span>|<span data-ttu-id="88d60-284">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-284">Int16</span></span>|
|<span data-ttu-id="88d60-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-285">TYPE_NAME</span></span>|<span data-ttu-id="88d60-286">String</span><span class="sxs-lookup"><span data-stu-id="88d60-286">String</span></span>|
|<span data-ttu-id="88d60-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="88d60-287">COLUMN_SIZE</span></span>|<span data-ttu-id="88d60-288">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-288">Int32</span></span>|
|<span data-ttu-id="88d60-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="88d60-290">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-290">Int32</span></span>|
|<span data-ttu-id="88d60-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="88d60-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="88d60-292">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-292">Int16</span></span>|
|<span data-ttu-id="88d60-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="88d60-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="88d60-294">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-294">Int16</span></span>|
|<span data-ttu-id="88d60-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-295">NULLABLE</span></span>|<span data-ttu-id="88d60-296">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-296">Int16</span></span>|
|<span data-ttu-id="88d60-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-297">REMARKS</span></span>|<span data-ttu-id="88d60-298">String</span><span class="sxs-lookup"><span data-stu-id="88d60-298">String</span></span>|
|<span data-ttu-id="88d60-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="88d60-299">COLUMN_DEF</span></span>|<span data-ttu-id="88d60-300">String</span><span class="sxs-lookup"><span data-stu-id="88d60-300">String</span></span>|
|<span data-ttu-id="88d60-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="88d60-302">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-302">Int16</span></span>|
|<span data-ttu-id="88d60-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="88d60-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="88d60-304">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-304">Int16</span></span>|
|<span data-ttu-id="88d60-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="88d60-306">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-306">Int32</span></span>|
|<span data-ttu-id="88d60-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="88d60-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="88d60-308">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-308">Int32</span></span>|
|<span data-ttu-id="88d60-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-309">IS_NULLABLE</span></span>|<span data-ttu-id="88d60-310">String</span><span class="sxs-lookup"><span data-stu-id="88d60-310">String</span></span>|
|<span data-ttu-id="88d60-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="88d60-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="88d60-312">String</span><span class="sxs-lookup"><span data-stu-id="88d60-312">String</span></span>|
|<span data-ttu-id="88d60-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="88d60-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="88d60-314">String</span><span class="sxs-lookup"><span data-stu-id="88d60-314">String</span></span>|
|<span data-ttu-id="88d60-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="88d60-316">Byte</span><span class="sxs-lookup"><span data-stu-id="88d60-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="88d60-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="88d60-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="88d60-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="88d60-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="88d60-319">表</span><span class="sxs-lookup"><span data-stu-id="88d60-319">Tables</span></span>

- <span data-ttu-id="88d60-320">列</span><span class="sxs-lookup"><span data-stu-id="88d60-320">Columns</span></span>

- <span data-ttu-id="88d60-321">过程</span><span class="sxs-lookup"><span data-stu-id="88d60-321">Procedures</span></span>

- <span data-ttu-id="88d60-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="88d60-322">ProcedureColumns</span></span>

- <span data-ttu-id="88d60-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="88d60-323">ProcedureParameters</span></span>

- <span data-ttu-id="88d60-324">Views</span><span class="sxs-lookup"><span data-stu-id="88d60-324">Views</span></span>

- <span data-ttu-id="88d60-325">索引</span><span class="sxs-lookup"><span data-stu-id="88d60-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="88d60-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="88d60-326">Tables and Views</span></span>

|<span data-ttu-id="88d60-327">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-327">ColumnName</span></span>|<span data-ttu-id="88d60-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="88d60-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="88d60-330">String</span><span class="sxs-lookup"><span data-stu-id="88d60-330">String</span></span>|
|<span data-ttu-id="88d60-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="88d60-331">TABLE_OWNER</span></span>|<span data-ttu-id="88d60-332">String</span><span class="sxs-lookup"><span data-stu-id="88d60-332">String</span></span>|
|<span data-ttu-id="88d60-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-333">TABLE_NAME</span></span>|<span data-ttu-id="88d60-334">String</span><span class="sxs-lookup"><span data-stu-id="88d60-334">String</span></span>|
|<span data-ttu-id="88d60-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-335">TABLE_TYPE</span></span>|<span data-ttu-id="88d60-336">String</span><span class="sxs-lookup"><span data-stu-id="88d60-336">String</span></span>|
|<span data-ttu-id="88d60-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-337">REMARKS</span></span>|<span data-ttu-id="88d60-338">String</span><span class="sxs-lookup"><span data-stu-id="88d60-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="88d60-339">列</span><span class="sxs-lookup"><span data-stu-id="88d60-339">Columns</span></span>

|<span data-ttu-id="88d60-340">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-340">ColumnName</span></span>|<span data-ttu-id="88d60-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="88d60-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="88d60-343">String</span><span class="sxs-lookup"><span data-stu-id="88d60-343">String</span></span>|
|<span data-ttu-id="88d60-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="88d60-344">TABLE_OWNER</span></span>|<span data-ttu-id="88d60-345">String</span><span class="sxs-lookup"><span data-stu-id="88d60-345">String</span></span>|
|<span data-ttu-id="88d60-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-346">TABLE_NAME</span></span>|<span data-ttu-id="88d60-347">String</span><span class="sxs-lookup"><span data-stu-id="88d60-347">String</span></span>|
|<span data-ttu-id="88d60-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-348">COLUMN_NAME</span></span>|<span data-ttu-id="88d60-349">String</span><span class="sxs-lookup"><span data-stu-id="88d60-349">String</span></span>|
|<span data-ttu-id="88d60-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-350">DATA_TYPE</span></span>|<span data-ttu-id="88d60-351">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-351">Int16</span></span>|
|<span data-ttu-id="88d60-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-352">TYPE_NAME</span></span>|<span data-ttu-id="88d60-353">String</span><span class="sxs-lookup"><span data-stu-id="88d60-353">String</span></span>|
|<span data-ttu-id="88d60-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="88d60-354">PRECISION</span></span>|<span data-ttu-id="88d60-355">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-355">Int32</span></span>|
|<span data-ttu-id="88d60-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-356">LENGTH</span></span>|<span data-ttu-id="88d60-357">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-357">Int32</span></span>|
|<span data-ttu-id="88d60-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="88d60-358">SCALE</span></span>|<span data-ttu-id="88d60-359">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-359">Int16</span></span>|
|<span data-ttu-id="88d60-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="88d60-360">RADIX</span></span>|<span data-ttu-id="88d60-361">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-361">Int16</span></span>|
|<span data-ttu-id="88d60-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-362">NULLABLE</span></span>|<span data-ttu-id="88d60-363">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-363">Int16</span></span>|
|<span data-ttu-id="88d60-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-364">REMARKS</span></span>|<span data-ttu-id="88d60-365">String</span><span class="sxs-lookup"><span data-stu-id="88d60-365">String</span></span>|
|<span data-ttu-id="88d60-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="88d60-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="88d60-367">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="88d60-368">过程</span><span class="sxs-lookup"><span data-stu-id="88d60-368">Procedures</span></span>

|<span data-ttu-id="88d60-369">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-369">ColumnName</span></span>|<span data-ttu-id="88d60-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="88d60-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="88d60-372">String</span><span class="sxs-lookup"><span data-stu-id="88d60-372">String</span></span>|
|<span data-ttu-id="88d60-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="88d60-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="88d60-374">String</span><span class="sxs-lookup"><span data-stu-id="88d60-374">String</span></span>|
|<span data-ttu-id="88d60-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="88d60-376">String</span><span class="sxs-lookup"><span data-stu-id="88d60-376">String</span></span>|
|<span data-ttu-id="88d60-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="88d60-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="88d60-378">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-378">Int16</span></span>|
|<span data-ttu-id="88d60-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="88d60-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="88d60-380">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-380">Int16</span></span>|
|<span data-ttu-id="88d60-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="88d60-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="88d60-382">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-382">Int16</span></span>|
|<span data-ttu-id="88d60-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-383">REMARKS</span></span>|<span data-ttu-id="88d60-384">String</span><span class="sxs-lookup"><span data-stu-id="88d60-384">String</span></span>|
|<span data-ttu-id="88d60-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="88d60-386">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="88d60-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="88d60-387">ProcedureColumns</span></span>

|<span data-ttu-id="88d60-388">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-388">ColumnName</span></span>|<span data-ttu-id="88d60-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="88d60-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="88d60-391">String</span><span class="sxs-lookup"><span data-stu-id="88d60-391">String</span></span>|
|<span data-ttu-id="88d60-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="88d60-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="88d60-393">String</span><span class="sxs-lookup"><span data-stu-id="88d60-393">String</span></span>|
|<span data-ttu-id="88d60-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="88d60-395">String</span><span class="sxs-lookup"><span data-stu-id="88d60-395">String</span></span>|
|<span data-ttu-id="88d60-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-396">COLUMN_NAME</span></span>|<span data-ttu-id="88d60-397">String</span><span class="sxs-lookup"><span data-stu-id="88d60-397">String</span></span>|
|<span data-ttu-id="88d60-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-398">COLUMN_TYPE</span></span>|<span data-ttu-id="88d60-399">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-399">Int16</span></span>|
|<span data-ttu-id="88d60-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-400">DATA_TYPE</span></span>|<span data-ttu-id="88d60-401">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-401">Int16</span></span>|
|<span data-ttu-id="88d60-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-402">TYPE_NAME</span></span>|<span data-ttu-id="88d60-403">String</span><span class="sxs-lookup"><span data-stu-id="88d60-403">String</span></span>|
|<span data-ttu-id="88d60-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="88d60-404">PRECISION</span></span>|<span data-ttu-id="88d60-405">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-405">Int32</span></span>|
|<span data-ttu-id="88d60-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-406">LENGTH</span></span>|<span data-ttu-id="88d60-407">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-407">Int32</span></span>|
|<span data-ttu-id="88d60-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="88d60-408">SCALE</span></span>|<span data-ttu-id="88d60-409">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-409">Int16</span></span>|
|<span data-ttu-id="88d60-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="88d60-410">RADIX</span></span>|<span data-ttu-id="88d60-411">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-411">Int16</span></span>|
|<span data-ttu-id="88d60-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-412">NULLABLE</span></span>|<span data-ttu-id="88d60-413">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-413">Int16</span></span>|
|<span data-ttu-id="88d60-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-414">REMARKS</span></span>|<span data-ttu-id="88d60-415">String</span><span class="sxs-lookup"><span data-stu-id="88d60-415">String</span></span>|
|<span data-ttu-id="88d60-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="88d60-416">OVERLOAD</span></span>|<span data-ttu-id="88d60-417">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-417">Int32</span></span>|
|<span data-ttu-id="88d60-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="88d60-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="88d60-419">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="88d60-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="88d60-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="88d60-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="88d60-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="88d60-422">表</span><span class="sxs-lookup"><span data-stu-id="88d60-422">Tables</span></span>

- <span data-ttu-id="88d60-423">索引</span><span class="sxs-lookup"><span data-stu-id="88d60-423">Indexes</span></span>

- <span data-ttu-id="88d60-424">列</span><span class="sxs-lookup"><span data-stu-id="88d60-424">Columns</span></span>

- <span data-ttu-id="88d60-425">过程</span><span class="sxs-lookup"><span data-stu-id="88d60-425">Procedures</span></span>

- <span data-ttu-id="88d60-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="88d60-426">ProcedureColumns</span></span>

- <span data-ttu-id="88d60-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="88d60-427">ProcedureParameters</span></span>

- <span data-ttu-id="88d60-428">Views</span><span class="sxs-lookup"><span data-stu-id="88d60-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="88d60-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="88d60-429">Tables and Views</span></span>

|<span data-ttu-id="88d60-430">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-430">ColumnName</span></span>|<span data-ttu-id="88d60-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="88d60-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="88d60-433">String</span><span class="sxs-lookup"><span data-stu-id="88d60-433">String</span></span>|
|<span data-ttu-id="88d60-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="88d60-434">TABLE_OWNER</span></span>|<span data-ttu-id="88d60-435">String</span><span class="sxs-lookup"><span data-stu-id="88d60-435">String</span></span>|
|<span data-ttu-id="88d60-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-436">TABLE_NAME</span></span>|<span data-ttu-id="88d60-437">String</span><span class="sxs-lookup"><span data-stu-id="88d60-437">String</span></span>|
|<span data-ttu-id="88d60-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-438">TABLE_TYPE</span></span>|<span data-ttu-id="88d60-439">String</span><span class="sxs-lookup"><span data-stu-id="88d60-439">String</span></span>|
|<span data-ttu-id="88d60-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-440">REMARKS</span></span>|<span data-ttu-id="88d60-441">String</span><span class="sxs-lookup"><span data-stu-id="88d60-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="88d60-442">列</span><span class="sxs-lookup"><span data-stu-id="88d60-442">Columns</span></span>

|<span data-ttu-id="88d60-443">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-443">ColumnName</span></span>|<span data-ttu-id="88d60-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="88d60-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="88d60-446">String</span><span class="sxs-lookup"><span data-stu-id="88d60-446">String</span></span>|
|<span data-ttu-id="88d60-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="88d60-447">TABLE_OWNER</span></span>|<span data-ttu-id="88d60-448">String</span><span class="sxs-lookup"><span data-stu-id="88d60-448">String</span></span>|
|<span data-ttu-id="88d60-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-449">TABLE_NAME</span></span>|<span data-ttu-id="88d60-450">String</span><span class="sxs-lookup"><span data-stu-id="88d60-450">String</span></span>|
|<span data-ttu-id="88d60-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-451">COLUMN_NAME</span></span>|<span data-ttu-id="88d60-452">String</span><span class="sxs-lookup"><span data-stu-id="88d60-452">String</span></span>|
|<span data-ttu-id="88d60-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-453">DATA_TYPE</span></span>|<span data-ttu-id="88d60-454">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-454">Int16</span></span>|
|<span data-ttu-id="88d60-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-455">TYPE_NAME</span></span>|<span data-ttu-id="88d60-456">String</span><span class="sxs-lookup"><span data-stu-id="88d60-456">String</span></span>|
|<span data-ttu-id="88d60-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="88d60-457">PRECISION</span></span>|<span data-ttu-id="88d60-458">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-458">Int32</span></span>|
|<span data-ttu-id="88d60-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-459">LENGTH</span></span>|<span data-ttu-id="88d60-460">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-460">Int32</span></span>|
|<span data-ttu-id="88d60-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="88d60-461">SCALE</span></span>|<span data-ttu-id="88d60-462">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-462">Int16</span></span>|
|<span data-ttu-id="88d60-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="88d60-463">RADIX</span></span>|<span data-ttu-id="88d60-464">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-464">Int16</span></span>|
|<span data-ttu-id="88d60-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-465">NULLABLE</span></span>|<span data-ttu-id="88d60-466">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-466">Int16</span></span>|
|<span data-ttu-id="88d60-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-467">REMARKS</span></span>|<span data-ttu-id="88d60-468">String</span><span class="sxs-lookup"><span data-stu-id="88d60-468">String</span></span>|
|<span data-ttu-id="88d60-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="88d60-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="88d60-470">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="88d60-471">过程</span><span class="sxs-lookup"><span data-stu-id="88d60-471">Procedures</span></span>

|<span data-ttu-id="88d60-472">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-472">ColumnName</span></span>|<span data-ttu-id="88d60-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="88d60-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="88d60-475">String</span><span class="sxs-lookup"><span data-stu-id="88d60-475">String</span></span>|
|<span data-ttu-id="88d60-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="88d60-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="88d60-477">String</span><span class="sxs-lookup"><span data-stu-id="88d60-477">String</span></span>|
|<span data-ttu-id="88d60-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="88d60-479">String</span><span class="sxs-lookup"><span data-stu-id="88d60-479">String</span></span>|
|<span data-ttu-id="88d60-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="88d60-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="88d60-481">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-481">Int16</span></span>|
|<span data-ttu-id="88d60-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="88d60-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="88d60-483">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-483">Int16</span></span>|
|<span data-ttu-id="88d60-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="88d60-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="88d60-485">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-485">Int16</span></span>|
|<span data-ttu-id="88d60-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-486">REMARKS</span></span>|<span data-ttu-id="88d60-487">String</span><span class="sxs-lookup"><span data-stu-id="88d60-487">String</span></span>|
|<span data-ttu-id="88d60-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="88d60-489">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="88d60-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="88d60-490">ProcedureColumns</span></span>

|<span data-ttu-id="88d60-491">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-491">ColumnName</span></span>|<span data-ttu-id="88d60-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="88d60-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="88d60-494">String</span><span class="sxs-lookup"><span data-stu-id="88d60-494">String</span></span>|
|<span data-ttu-id="88d60-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="88d60-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="88d60-496">String</span><span class="sxs-lookup"><span data-stu-id="88d60-496">String</span></span>|
|<span data-ttu-id="88d60-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="88d60-498">String</span><span class="sxs-lookup"><span data-stu-id="88d60-498">String</span></span>|
|<span data-ttu-id="88d60-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-499">COLUMN_NAME</span></span>|<span data-ttu-id="88d60-500">String</span><span class="sxs-lookup"><span data-stu-id="88d60-500">String</span></span>|
|<span data-ttu-id="88d60-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-501">COLUMN_TYPE</span></span>|<span data-ttu-id="88d60-502">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-502">Int16</span></span>|
|<span data-ttu-id="88d60-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-503">DATA_TYPE</span></span>|<span data-ttu-id="88d60-504">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-504">Int16</span></span>|
|<span data-ttu-id="88d60-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-505">TYPE_NAME</span></span>|<span data-ttu-id="88d60-506">String</span><span class="sxs-lookup"><span data-stu-id="88d60-506">String</span></span>|
|<span data-ttu-id="88d60-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="88d60-507">PRECISION</span></span>|<span data-ttu-id="88d60-508">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-508">Int32</span></span>|
|<span data-ttu-id="88d60-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-509">LENGTH</span></span>|<span data-ttu-id="88d60-510">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-510">Int32</span></span>|
|<span data-ttu-id="88d60-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="88d60-511">SCALE</span></span>|<span data-ttu-id="88d60-512">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-512">Int16</span></span>|
|<span data-ttu-id="88d60-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="88d60-513">RADIX</span></span>|<span data-ttu-id="88d60-514">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-514">Int16</span></span>|
|<span data-ttu-id="88d60-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-515">NULLABLE</span></span>|<span data-ttu-id="88d60-516">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-516">Int16</span></span>|
|<span data-ttu-id="88d60-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-517">REMARKS</span></span>|<span data-ttu-id="88d60-518">String</span><span class="sxs-lookup"><span data-stu-id="88d60-518">String</span></span>|
|<span data-ttu-id="88d60-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="88d60-519">OVERLOAD</span></span>|<span data-ttu-id="88d60-520">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-520">Int32</span></span>|
|<span data-ttu-id="88d60-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="88d60-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="88d60-522">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="88d60-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="88d60-523">ProcedureParameters</span></span>

|<span data-ttu-id="88d60-524">列名</span><span class="sxs-lookup"><span data-stu-id="88d60-524">ColumnName</span></span>|<span data-ttu-id="88d60-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="88d60-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="88d60-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="88d60-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="88d60-527">String</span><span class="sxs-lookup"><span data-stu-id="88d60-527">String</span></span>|
|<span data-ttu-id="88d60-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="88d60-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="88d60-529">String</span><span class="sxs-lookup"><span data-stu-id="88d60-529">String</span></span>|
|<span data-ttu-id="88d60-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="88d60-531">String</span><span class="sxs-lookup"><span data-stu-id="88d60-531">String</span></span>|
|<span data-ttu-id="88d60-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-532">COLUMN_NAME</span></span>|<span data-ttu-id="88d60-533">String</span><span class="sxs-lookup"><span data-stu-id="88d60-533">String</span></span>|
|<span data-ttu-id="88d60-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-534">COLUMN_TYPE</span></span>|<span data-ttu-id="88d60-535">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-535">Int16</span></span>|
|<span data-ttu-id="88d60-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-536">DATA_TYPE</span></span>|<span data-ttu-id="88d60-537">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-537">Int16</span></span>|
|<span data-ttu-id="88d60-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="88d60-538">TYPE_NAME</span></span>|<span data-ttu-id="88d60-539">String</span><span class="sxs-lookup"><span data-stu-id="88d60-539">String</span></span>|
|<span data-ttu-id="88d60-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="88d60-540">COLUMN_SIZE</span></span>|<span data-ttu-id="88d60-541">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-541">Int32</span></span>|
|<span data-ttu-id="88d60-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="88d60-543">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-543">Int32</span></span>|
|<span data-ttu-id="88d60-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="88d60-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="88d60-545">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-545">Int16</span></span>|
|<span data-ttu-id="88d60-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="88d60-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="88d60-547">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-547">Int16</span></span>|
|<span data-ttu-id="88d60-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-548">NULLABLE</span></span>|<span data-ttu-id="88d60-549">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-549">Int16</span></span>|
|<span data-ttu-id="88d60-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="88d60-550">REMARKS</span></span>|<span data-ttu-id="88d60-551">String</span><span class="sxs-lookup"><span data-stu-id="88d60-551">String</span></span>|
|<span data-ttu-id="88d60-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="88d60-552">COLUMN_DEF</span></span>|<span data-ttu-id="88d60-553">String</span><span class="sxs-lookup"><span data-stu-id="88d60-553">String</span></span>|
|<span data-ttu-id="88d60-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="88d60-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="88d60-555">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-555">Int16</span></span>|
|<span data-ttu-id="88d60-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="88d60-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="88d60-557">Int16</span><span class="sxs-lookup"><span data-stu-id="88d60-557">Int16</span></span>|
|<span data-ttu-id="88d60-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="88d60-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="88d60-559">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-559">Int32</span></span>|
|<span data-ttu-id="88d60-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="88d60-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="88d60-561">Int32</span><span class="sxs-lookup"><span data-stu-id="88d60-561">Int32</span></span>|
|<span data-ttu-id="88d60-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="88d60-562">IS_NULLABLE</span></span>|<span data-ttu-id="88d60-563">String</span><span class="sxs-lookup"><span data-stu-id="88d60-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="88d60-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="88d60-564">See also</span></span>

- [<span data-ttu-id="88d60-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="88d60-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
