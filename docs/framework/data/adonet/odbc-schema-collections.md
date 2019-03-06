---
title: ODBC 架构集合
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365901"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="ff13e-102">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="ff13e-102">ODBC Schema Collections</span></span>

<span data-ttu-id="ff13e-103">本节讨论对适用于 Microsoft SQL Server、Oracle 和 Microsoft Jet 的 ODBC 驱动程序的架构集合支持。</span><span class="sxs-lookup"><span data-stu-id="ff13e-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="ff13e-104">Microsoft SQL Server ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="ff13e-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="ff13e-105">Microsoft SQL Server ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="ff13e-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="ff13e-106">表</span><span class="sxs-lookup"><span data-stu-id="ff13e-106">Tables</span></span>

- <span data-ttu-id="ff13e-107">索引</span><span class="sxs-lookup"><span data-stu-id="ff13e-107">Indexes</span></span>

- <span data-ttu-id="ff13e-108">Columns</span><span class="sxs-lookup"><span data-stu-id="ff13e-108">Columns</span></span>

- <span data-ttu-id="ff13e-109">过程</span><span class="sxs-lookup"><span data-stu-id="ff13e-109">Procedures</span></span>

- <span data-ttu-id="ff13e-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ff13e-110">ProcedureColumns</span></span>

- <span data-ttu-id="ff13e-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ff13e-111">ProcedureParameters</span></span>

- <span data-ttu-id="ff13e-112">视图</span><span class="sxs-lookup"><span data-stu-id="ff13e-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="ff13e-113">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="ff13e-113">Tables and Views</span></span>

|<span data-ttu-id="ff13e-114">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-114">ColumnName</span></span>|<span data-ttu-id="ff13e-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="ff13e-116">TABLE_CAT</span></span>|<span data-ttu-id="ff13e-117">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-117">String</span></span>|
|<span data-ttu-id="ff13e-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ff13e-118">TABLE_SCHEM</span></span>|<span data-ttu-id="ff13e-119">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-119">String</span></span>|
|<span data-ttu-id="ff13e-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-120">TABLE_NAME</span></span>|<span data-ttu-id="ff13e-121">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-121">String</span></span>|
|<span data-ttu-id="ff13e-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-122">TABLE_TYPE</span></span>|<span data-ttu-id="ff13e-123">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-123">String</span></span>|
|<span data-ttu-id="ff13e-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-124">REMARKS</span></span>|<span data-ttu-id="ff13e-125">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="ff13e-126">索引</span><span class="sxs-lookup"><span data-stu-id="ff13e-126">Indexes</span></span>

|<span data-ttu-id="ff13e-127">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-127">ColumnName</span></span>|<span data-ttu-id="ff13e-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="ff13e-129">TABLE_CAT</span></span>|<span data-ttu-id="ff13e-130">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-130">String</span></span>|
|<span data-ttu-id="ff13e-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ff13e-131">TABLE_SCHEM</span></span>|<span data-ttu-id="ff13e-132">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-132">String</span></span>|
|<span data-ttu-id="ff13e-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-133">TABLE_NAME</span></span>|<span data-ttu-id="ff13e-134">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-134">String</span></span>|
|<span data-ttu-id="ff13e-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="ff13e-135">NON_UNIQUE</span></span>|<span data-ttu-id="ff13e-136">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-136">Int16</span></span>|
|<span data-ttu-id="ff13e-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ff13e-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="ff13e-138">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-138">String</span></span>|
|<span data-ttu-id="ff13e-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-139">INDEX_NAME</span></span>|<span data-ttu-id="ff13e-140">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-140">String</span></span>|
|<span data-ttu-id="ff13e-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-141">TYPE</span></span>|<span data-ttu-id="ff13e-142">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-142">Int16</span></span>|
|<span data-ttu-id="ff13e-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="ff13e-144">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-144">Int16</span></span>|
|<span data-ttu-id="ff13e-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-145">COLUMN_NAME</span></span>|<span data-ttu-id="ff13e-146">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-146">String</span></span>|
|<span data-ttu-id="ff13e-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="ff13e-147">ASC_OR_DESC</span></span>|<span data-ttu-id="ff13e-148">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-148">String</span></span>|
|<span data-ttu-id="ff13e-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="ff13e-149">CARDINALITY</span></span>|<span data-ttu-id="ff13e-150">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-150">Int32</span></span>|
|<span data-ttu-id="ff13e-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="ff13e-151">PAGES</span></span>|<span data-ttu-id="ff13e-152">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-152">Int32</span></span>|
|<span data-ttu-id="ff13e-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-153">FILTER_CONDITION</span></span>|<span data-ttu-id="ff13e-154">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-154">String</span></span>|
|<span data-ttu-id="ff13e-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ff13e-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ff13e-156">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-156">String</span></span>|
|<span data-ttu-id="ff13e-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="ff13e-158">Byte</span><span class="sxs-lookup"><span data-stu-id="ff13e-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="ff13e-159">Columns</span><span class="sxs-lookup"><span data-stu-id="ff13e-159">Columns</span></span>

|<span data-ttu-id="ff13e-160">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-160">ColumnName</span></span>|<span data-ttu-id="ff13e-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="ff13e-162">TABLE_CAT</span></span>|<span data-ttu-id="ff13e-163">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-163">String</span></span>|
|<span data-ttu-id="ff13e-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ff13e-164">TABLE_SCHEM</span></span>|<span data-ttu-id="ff13e-165">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-165">String</span></span>|
|<span data-ttu-id="ff13e-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-166">TABLE_NAME</span></span>|<span data-ttu-id="ff13e-167">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-167">String</span></span>|
|<span data-ttu-id="ff13e-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-168">COLUMN_NAME</span></span>|<span data-ttu-id="ff13e-169">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-169">String</span></span>|
|<span data-ttu-id="ff13e-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-170">DATA_TYPE</span></span>|<span data-ttu-id="ff13e-171">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-171">Int16</span></span>|
|<span data-ttu-id="ff13e-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-172">TYPE_NAME</span></span>|<span data-ttu-id="ff13e-173">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-173">String</span></span>|
|<span data-ttu-id="ff13e-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ff13e-174">COLUMN_SIZE</span></span>|<span data-ttu-id="ff13e-175">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-175">Int32</span></span>|
|<span data-ttu-id="ff13e-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="ff13e-177">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-177">Int32</span></span>|
|<span data-ttu-id="ff13e-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ff13e-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ff13e-179">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-179">Int16</span></span>|
|<span data-ttu-id="ff13e-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ff13e-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ff13e-181">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-181">Int16</span></span>|
|<span data-ttu-id="ff13e-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-182">NULLABLE</span></span>|<span data-ttu-id="ff13e-183">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-183">Int16</span></span>|
|<span data-ttu-id="ff13e-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-184">REMARKS</span></span>|<span data-ttu-id="ff13e-185">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-185">String</span></span>|
|<span data-ttu-id="ff13e-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ff13e-186">COLUMN_DEF</span></span>|<span data-ttu-id="ff13e-187">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-187">String</span></span>|
|<span data-ttu-id="ff13e-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ff13e-189">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-189">Int16</span></span>|
|<span data-ttu-id="ff13e-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ff13e-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ff13e-191">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-191">Int16</span></span>|
|<span data-ttu-id="ff13e-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ff13e-193">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-193">Int32</span></span>|
|<span data-ttu-id="ff13e-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="ff13e-195">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-195">Int32</span></span>|
|<span data-ttu-id="ff13e-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-196">IS_NULLABLE</span></span>|<span data-ttu-id="ff13e-197">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-197">String</span></span>|
|<span data-ttu-id="ff13e-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ff13e-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="ff13e-199">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-199">String</span></span>|
|<span data-ttu-id="ff13e-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ff13e-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ff13e-201">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-201">String</span></span>|
|<span data-ttu-id="ff13e-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="ff13e-203">Byte</span><span class="sxs-lookup"><span data-stu-id="ff13e-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="ff13e-204">过程</span><span class="sxs-lookup"><span data-stu-id="ff13e-204">Procedures</span></span>

|<span data-ttu-id="ff13e-205">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-205">ColumnName</span></span>|<span data-ttu-id="ff13e-206">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ff13e-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="ff13e-208">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-208">String</span></span>|
|<span data-ttu-id="ff13e-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ff13e-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ff13e-210">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-210">String</span></span>|
|<span data-ttu-id="ff13e-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="ff13e-212">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-212">String</span></span>|
|<span data-ttu-id="ff13e-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ff13e-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="ff13e-214">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-214">Int32</span></span>|
|<span data-ttu-id="ff13e-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ff13e-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="ff13e-216">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-216">Int32</span></span>|
|<span data-ttu-id="ff13e-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="ff13e-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="ff13e-218">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-218">Int32</span></span>|
|<span data-ttu-id="ff13e-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-219">REMARKS</span></span>|<span data-ttu-id="ff13e-220">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-220">String</span></span>|
|<span data-ttu-id="ff13e-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="ff13e-222">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="ff13e-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ff13e-223">ProcedureColumns</span></span>

|<span data-ttu-id="ff13e-224">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-224">ColumnName</span></span>|<span data-ttu-id="ff13e-225">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ff13e-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="ff13e-227">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-227">String</span></span>|
|<span data-ttu-id="ff13e-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ff13e-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ff13e-229">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-229">String</span></span>|
|<span data-ttu-id="ff13e-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="ff13e-231">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-231">String</span></span>|
|<span data-ttu-id="ff13e-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-232">COLUMN_NAME</span></span>|<span data-ttu-id="ff13e-233">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-233">String</span></span>|
|<span data-ttu-id="ff13e-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-234">COLUMN_TYPE</span></span>|<span data-ttu-id="ff13e-235">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-235">Int16</span></span>|
|<span data-ttu-id="ff13e-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-236">DATA_TYPE</span></span>|<span data-ttu-id="ff13e-237">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-237">Int16</span></span>|
|<span data-ttu-id="ff13e-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-238">TYPE_NAME</span></span>|<span data-ttu-id="ff13e-239">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-239">String</span></span>|
|<span data-ttu-id="ff13e-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ff13e-240">COLUMN_SIZE</span></span>|<span data-ttu-id="ff13e-241">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-241">Int32</span></span>|
|<span data-ttu-id="ff13e-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="ff13e-243">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-243">Int32</span></span>|
|<span data-ttu-id="ff13e-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ff13e-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ff13e-245">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-245">Int16</span></span>|
|<span data-ttu-id="ff13e-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ff13e-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ff13e-247">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-247">Int16</span></span>|
|<span data-ttu-id="ff13e-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-248">NULLABLE</span></span>|<span data-ttu-id="ff13e-249">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-249">Int16</span></span>|
|<span data-ttu-id="ff13e-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-250">REMARKS</span></span>|<span data-ttu-id="ff13e-251">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-251">String</span></span>|
|<span data-ttu-id="ff13e-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ff13e-252">COLUMN_DEF</span></span>|<span data-ttu-id="ff13e-253">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-253">String</span></span>|
|<span data-ttu-id="ff13e-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ff13e-255">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-255">Int16</span></span>|
|<span data-ttu-id="ff13e-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ff13e-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ff13e-257">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-257">Int16</span></span>|
|<span data-ttu-id="ff13e-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ff13e-259">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-259">Int32</span></span>|
|<span data-ttu-id="ff13e-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="ff13e-261">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-261">Int32</span></span>|
|<span data-ttu-id="ff13e-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-262">IS_NULLABLE</span></span>|<span data-ttu-id="ff13e-263">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-263">String</span></span>|
|<span data-ttu-id="ff13e-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ff13e-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="ff13e-265">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-265">String</span></span>|
|<span data-ttu-id="ff13e-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ff13e-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ff13e-267">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-267">String</span></span>|
|<span data-ttu-id="ff13e-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="ff13e-269">Byte</span><span class="sxs-lookup"><span data-stu-id="ff13e-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="ff13e-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ff13e-270">ProcedureParameters</span></span>

|<span data-ttu-id="ff13e-271">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-271">ColumnName</span></span>|<span data-ttu-id="ff13e-272">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ff13e-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="ff13e-274">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-274">String</span></span>|
|<span data-ttu-id="ff13e-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ff13e-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ff13e-276">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-276">String</span></span>|
|<span data-ttu-id="ff13e-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="ff13e-278">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-278">String</span></span>|
|<span data-ttu-id="ff13e-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-279">COLUMN_NAME</span></span>|<span data-ttu-id="ff13e-280">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-280">String</span></span>|
|<span data-ttu-id="ff13e-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-281">COLUMN_TYPE</span></span>|<span data-ttu-id="ff13e-282">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-282">Int16</span></span>|
|<span data-ttu-id="ff13e-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-283">DATA_TYPE</span></span>|<span data-ttu-id="ff13e-284">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-284">Int16</span></span>|
|<span data-ttu-id="ff13e-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-285">TYPE_NAME</span></span>|<span data-ttu-id="ff13e-286">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-286">String</span></span>|
|<span data-ttu-id="ff13e-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ff13e-287">COLUMN_SIZE</span></span>|<span data-ttu-id="ff13e-288">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-288">Int32</span></span>|
|<span data-ttu-id="ff13e-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="ff13e-290">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-290">Int32</span></span>|
|<span data-ttu-id="ff13e-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ff13e-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ff13e-292">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-292">Int16</span></span>|
|<span data-ttu-id="ff13e-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ff13e-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ff13e-294">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-294">Int16</span></span>|
|<span data-ttu-id="ff13e-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-295">NULLABLE</span></span>|<span data-ttu-id="ff13e-296">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-296">Int16</span></span>|
|<span data-ttu-id="ff13e-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-297">REMARKS</span></span>|<span data-ttu-id="ff13e-298">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-298">String</span></span>|
|<span data-ttu-id="ff13e-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ff13e-299">COLUMN_DEF</span></span>|<span data-ttu-id="ff13e-300">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-300">String</span></span>|
|<span data-ttu-id="ff13e-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ff13e-302">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-302">Int16</span></span>|
|<span data-ttu-id="ff13e-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ff13e-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ff13e-304">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-304">Int16</span></span>|
|<span data-ttu-id="ff13e-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ff13e-306">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-306">Int32</span></span>|
|<span data-ttu-id="ff13e-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="ff13e-308">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-308">Int32</span></span>|
|<span data-ttu-id="ff13e-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-309">IS_NULLABLE</span></span>|<span data-ttu-id="ff13e-310">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-310">String</span></span>|
|<span data-ttu-id="ff13e-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ff13e-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="ff13e-312">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-312">String</span></span>|
|<span data-ttu-id="ff13e-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ff13e-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ff13e-314">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-314">String</span></span>|
|<span data-ttu-id="ff13e-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="ff13e-316">Byte</span><span class="sxs-lookup"><span data-stu-id="ff13e-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="ff13e-317">Microsoft Oracle ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="ff13e-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="ff13e-318">Microsoft SQL Server Oracle ODBC 驱动程序还支持下列特定的架构集合除了通用架构集合：</span><span class="sxs-lookup"><span data-stu-id="ff13e-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="ff13e-319">表</span><span class="sxs-lookup"><span data-stu-id="ff13e-319">Tables</span></span>

- <span data-ttu-id="ff13e-320">Columns</span><span class="sxs-lookup"><span data-stu-id="ff13e-320">Columns</span></span>

- <span data-ttu-id="ff13e-321">过程</span><span class="sxs-lookup"><span data-stu-id="ff13e-321">Procedures</span></span>

- <span data-ttu-id="ff13e-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ff13e-322">ProcedureColumns</span></span>

- <span data-ttu-id="ff13e-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ff13e-323">ProcedureParameters</span></span>

- <span data-ttu-id="ff13e-324">视图</span><span class="sxs-lookup"><span data-stu-id="ff13e-324">Views</span></span>

- <span data-ttu-id="ff13e-325">索引</span><span class="sxs-lookup"><span data-stu-id="ff13e-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="ff13e-326">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="ff13e-326">Tables and Views</span></span>

|<span data-ttu-id="ff13e-327">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-327">ColumnName</span></span>|<span data-ttu-id="ff13e-328">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ff13e-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ff13e-330">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-330">String</span></span>|
|<span data-ttu-id="ff13e-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff13e-331">TABLE_OWNER</span></span>|<span data-ttu-id="ff13e-332">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-332">String</span></span>|
|<span data-ttu-id="ff13e-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-333">TABLE_NAME</span></span>|<span data-ttu-id="ff13e-334">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-334">String</span></span>|
|<span data-ttu-id="ff13e-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-335">TABLE_TYPE</span></span>|<span data-ttu-id="ff13e-336">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-336">String</span></span>|
|<span data-ttu-id="ff13e-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-337">REMARKS</span></span>|<span data-ttu-id="ff13e-338">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="ff13e-339">Columns</span><span class="sxs-lookup"><span data-stu-id="ff13e-339">Columns</span></span>

|<span data-ttu-id="ff13e-340">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-340">ColumnName</span></span>|<span data-ttu-id="ff13e-341">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ff13e-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ff13e-343">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-343">String</span></span>|
|<span data-ttu-id="ff13e-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff13e-344">TABLE_OWNER</span></span>|<span data-ttu-id="ff13e-345">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-345">String</span></span>|
|<span data-ttu-id="ff13e-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-346">TABLE_NAME</span></span>|<span data-ttu-id="ff13e-347">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-347">String</span></span>|
|<span data-ttu-id="ff13e-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-348">COLUMN_NAME</span></span>|<span data-ttu-id="ff13e-349">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-349">String</span></span>|
|<span data-ttu-id="ff13e-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-350">DATA_TYPE</span></span>|<span data-ttu-id="ff13e-351">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-351">Int16</span></span>|
|<span data-ttu-id="ff13e-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-352">TYPE_NAME</span></span>|<span data-ttu-id="ff13e-353">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-353">String</span></span>|
|<span data-ttu-id="ff13e-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ff13e-354">PRECISION</span></span>|<span data-ttu-id="ff13e-355">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-355">Int32</span></span>|
|<span data-ttu-id="ff13e-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-356">LENGTH</span></span>|<span data-ttu-id="ff13e-357">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-357">Int32</span></span>|
|<span data-ttu-id="ff13e-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="ff13e-358">SCALE</span></span>|<span data-ttu-id="ff13e-359">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-359">Int16</span></span>|
|<span data-ttu-id="ff13e-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="ff13e-360">RADIX</span></span>|<span data-ttu-id="ff13e-361">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-361">Int16</span></span>|
|<span data-ttu-id="ff13e-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-362">NULLABLE</span></span>|<span data-ttu-id="ff13e-363">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-363">Int16</span></span>|
|<span data-ttu-id="ff13e-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-364">REMARKS</span></span>|<span data-ttu-id="ff13e-365">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-365">String</span></span>|
|<span data-ttu-id="ff13e-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="ff13e-367">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="ff13e-368">过程</span><span class="sxs-lookup"><span data-stu-id="ff13e-368">Procedures</span></span>

|<span data-ttu-id="ff13e-369">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-369">ColumnName</span></span>|<span data-ttu-id="ff13e-370">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ff13e-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ff13e-372">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-372">String</span></span>|
|<span data-ttu-id="ff13e-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff13e-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ff13e-374">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-374">String</span></span>|
|<span data-ttu-id="ff13e-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="ff13e-376">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-376">String</span></span>|
|<span data-ttu-id="ff13e-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ff13e-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="ff13e-378">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-378">Int16</span></span>|
|<span data-ttu-id="ff13e-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ff13e-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="ff13e-380">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-380">Int16</span></span>|
|<span data-ttu-id="ff13e-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="ff13e-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="ff13e-382">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-382">Int16</span></span>|
|<span data-ttu-id="ff13e-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-383">REMARKS</span></span>|<span data-ttu-id="ff13e-384">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-384">String</span></span>|
|<span data-ttu-id="ff13e-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="ff13e-386">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="ff13e-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ff13e-387">ProcedureColumns</span></span>

|<span data-ttu-id="ff13e-388">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-388">ColumnName</span></span>|<span data-ttu-id="ff13e-389">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ff13e-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ff13e-391">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-391">String</span></span>|
|<span data-ttu-id="ff13e-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff13e-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ff13e-393">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-393">String</span></span>|
|<span data-ttu-id="ff13e-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="ff13e-395">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-395">String</span></span>|
|<span data-ttu-id="ff13e-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-396">COLUMN_NAME</span></span>|<span data-ttu-id="ff13e-397">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-397">String</span></span>|
|<span data-ttu-id="ff13e-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-398">COLUMN_TYPE</span></span>|<span data-ttu-id="ff13e-399">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-399">Int16</span></span>|
|<span data-ttu-id="ff13e-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-400">DATA_TYPE</span></span>|<span data-ttu-id="ff13e-401">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-401">Int16</span></span>|
|<span data-ttu-id="ff13e-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-402">TYPE_NAME</span></span>|<span data-ttu-id="ff13e-403">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-403">String</span></span>|
|<span data-ttu-id="ff13e-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ff13e-404">PRECISION</span></span>|<span data-ttu-id="ff13e-405">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-405">Int32</span></span>|
|<span data-ttu-id="ff13e-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-406">LENGTH</span></span>|<span data-ttu-id="ff13e-407">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-407">Int32</span></span>|
|<span data-ttu-id="ff13e-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="ff13e-408">SCALE</span></span>|<span data-ttu-id="ff13e-409">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-409">Int16</span></span>|
|<span data-ttu-id="ff13e-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="ff13e-410">RADIX</span></span>|<span data-ttu-id="ff13e-411">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-411">Int16</span></span>|
|<span data-ttu-id="ff13e-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-412">NULLABLE</span></span>|<span data-ttu-id="ff13e-413">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-413">Int16</span></span>|
|<span data-ttu-id="ff13e-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-414">REMARKS</span></span>|<span data-ttu-id="ff13e-415">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-415">String</span></span>|
|<span data-ttu-id="ff13e-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="ff13e-416">OVERLOAD</span></span>|<span data-ttu-id="ff13e-417">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-417">Int32</span></span>|
|<span data-ttu-id="ff13e-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="ff13e-419">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="ff13e-420">Microsoft Jet ODBC 驱动程序</span><span class="sxs-lookup"><span data-stu-id="ff13e-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="ff13e-421">除了通用架构集合之外，Microsoft Jet ODBC 驱动程序还支持下列特定的架构集合：</span><span class="sxs-lookup"><span data-stu-id="ff13e-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="ff13e-422">表</span><span class="sxs-lookup"><span data-stu-id="ff13e-422">Tables</span></span>

- <span data-ttu-id="ff13e-423">索引</span><span class="sxs-lookup"><span data-stu-id="ff13e-423">Indexes</span></span>

- <span data-ttu-id="ff13e-424">Columns</span><span class="sxs-lookup"><span data-stu-id="ff13e-424">Columns</span></span>

- <span data-ttu-id="ff13e-425">过程</span><span class="sxs-lookup"><span data-stu-id="ff13e-425">Procedures</span></span>

- <span data-ttu-id="ff13e-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ff13e-426">ProcedureColumns</span></span>

- <span data-ttu-id="ff13e-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ff13e-427">ProcedureParameters</span></span>

- <span data-ttu-id="ff13e-428">视图</span><span class="sxs-lookup"><span data-stu-id="ff13e-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="ff13e-429">Tables 和 Views</span><span class="sxs-lookup"><span data-stu-id="ff13e-429">Tables and Views</span></span>

|<span data-ttu-id="ff13e-430">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-430">ColumnName</span></span>|<span data-ttu-id="ff13e-431">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ff13e-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ff13e-433">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-433">String</span></span>|
|<span data-ttu-id="ff13e-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff13e-434">TABLE_OWNER</span></span>|<span data-ttu-id="ff13e-435">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-435">String</span></span>|
|<span data-ttu-id="ff13e-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-436">TABLE_NAME</span></span>|<span data-ttu-id="ff13e-437">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-437">String</span></span>|
|<span data-ttu-id="ff13e-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-438">TABLE_TYPE</span></span>|<span data-ttu-id="ff13e-439">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-439">String</span></span>|
|<span data-ttu-id="ff13e-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-440">REMARKS</span></span>|<span data-ttu-id="ff13e-441">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="ff13e-442">Columns</span><span class="sxs-lookup"><span data-stu-id="ff13e-442">Columns</span></span>

|<span data-ttu-id="ff13e-443">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-443">ColumnName</span></span>|<span data-ttu-id="ff13e-444">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ff13e-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ff13e-446">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-446">String</span></span>|
|<span data-ttu-id="ff13e-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff13e-447">TABLE_OWNER</span></span>|<span data-ttu-id="ff13e-448">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-448">String</span></span>|
|<span data-ttu-id="ff13e-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-449">TABLE_NAME</span></span>|<span data-ttu-id="ff13e-450">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-450">String</span></span>|
|<span data-ttu-id="ff13e-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-451">COLUMN_NAME</span></span>|<span data-ttu-id="ff13e-452">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-452">String</span></span>|
|<span data-ttu-id="ff13e-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-453">DATA_TYPE</span></span>|<span data-ttu-id="ff13e-454">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-454">Int16</span></span>|
|<span data-ttu-id="ff13e-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-455">TYPE_NAME</span></span>|<span data-ttu-id="ff13e-456">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-456">String</span></span>|
|<span data-ttu-id="ff13e-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ff13e-457">PRECISION</span></span>|<span data-ttu-id="ff13e-458">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-458">Int32</span></span>|
|<span data-ttu-id="ff13e-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-459">LENGTH</span></span>|<span data-ttu-id="ff13e-460">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-460">Int32</span></span>|
|<span data-ttu-id="ff13e-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="ff13e-461">SCALE</span></span>|<span data-ttu-id="ff13e-462">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-462">Int16</span></span>|
|<span data-ttu-id="ff13e-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="ff13e-463">RADIX</span></span>|<span data-ttu-id="ff13e-464">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-464">Int16</span></span>|
|<span data-ttu-id="ff13e-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-465">NULLABLE</span></span>|<span data-ttu-id="ff13e-466">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-466">Int16</span></span>|
|<span data-ttu-id="ff13e-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-467">REMARKS</span></span>|<span data-ttu-id="ff13e-468">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-468">String</span></span>|
|<span data-ttu-id="ff13e-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="ff13e-470">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="ff13e-471">过程</span><span class="sxs-lookup"><span data-stu-id="ff13e-471">Procedures</span></span>

|<span data-ttu-id="ff13e-472">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-472">ColumnName</span></span>|<span data-ttu-id="ff13e-473">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ff13e-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ff13e-475">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-475">String</span></span>|
|<span data-ttu-id="ff13e-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff13e-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ff13e-477">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-477">String</span></span>|
|<span data-ttu-id="ff13e-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="ff13e-479">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-479">String</span></span>|
|<span data-ttu-id="ff13e-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ff13e-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="ff13e-481">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-481">Int16</span></span>|
|<span data-ttu-id="ff13e-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ff13e-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="ff13e-483">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-483">Int16</span></span>|
|<span data-ttu-id="ff13e-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="ff13e-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="ff13e-485">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-485">Int16</span></span>|
|<span data-ttu-id="ff13e-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-486">REMARKS</span></span>|<span data-ttu-id="ff13e-487">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-487">String</span></span>|
|<span data-ttu-id="ff13e-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="ff13e-489">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="ff13e-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ff13e-490">ProcedureColumns</span></span>

|<span data-ttu-id="ff13e-491">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-491">ColumnName</span></span>|<span data-ttu-id="ff13e-492">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ff13e-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ff13e-494">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-494">String</span></span>|
|<span data-ttu-id="ff13e-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff13e-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ff13e-496">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-496">String</span></span>|
|<span data-ttu-id="ff13e-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="ff13e-498">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-498">String</span></span>|
|<span data-ttu-id="ff13e-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-499">COLUMN_NAME</span></span>|<span data-ttu-id="ff13e-500">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-500">String</span></span>|
|<span data-ttu-id="ff13e-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-501">COLUMN_TYPE</span></span>|<span data-ttu-id="ff13e-502">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-502">Int16</span></span>|
|<span data-ttu-id="ff13e-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-503">DATA_TYPE</span></span>|<span data-ttu-id="ff13e-504">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-504">Int16</span></span>|
|<span data-ttu-id="ff13e-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-505">TYPE_NAME</span></span>|<span data-ttu-id="ff13e-506">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-506">String</span></span>|
|<span data-ttu-id="ff13e-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ff13e-507">PRECISION</span></span>|<span data-ttu-id="ff13e-508">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-508">Int32</span></span>|
|<span data-ttu-id="ff13e-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-509">LENGTH</span></span>|<span data-ttu-id="ff13e-510">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-510">Int32</span></span>|
|<span data-ttu-id="ff13e-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="ff13e-511">SCALE</span></span>|<span data-ttu-id="ff13e-512">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-512">Int16</span></span>|
|<span data-ttu-id="ff13e-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="ff13e-513">RADIX</span></span>|<span data-ttu-id="ff13e-514">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-514">Int16</span></span>|
|<span data-ttu-id="ff13e-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-515">NULLABLE</span></span>|<span data-ttu-id="ff13e-516">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-516">Int16</span></span>|
|<span data-ttu-id="ff13e-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-517">REMARKS</span></span>|<span data-ttu-id="ff13e-518">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-518">String</span></span>|
|<span data-ttu-id="ff13e-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="ff13e-519">OVERLOAD</span></span>|<span data-ttu-id="ff13e-520">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-520">Int32</span></span>|
|<span data-ttu-id="ff13e-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="ff13e-522">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="ff13e-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ff13e-523">ProcedureParameters</span></span>

|<span data-ttu-id="ff13e-524">列名</span><span class="sxs-lookup"><span data-stu-id="ff13e-524">ColumnName</span></span>|<span data-ttu-id="ff13e-525">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff13e-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="ff13e-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ff13e-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="ff13e-527">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-527">String</span></span>|
|<span data-ttu-id="ff13e-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ff13e-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ff13e-529">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-529">String</span></span>|
|<span data-ttu-id="ff13e-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="ff13e-531">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-531">String</span></span>|
|<span data-ttu-id="ff13e-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-532">COLUMN_NAME</span></span>|<span data-ttu-id="ff13e-533">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-533">String</span></span>|
|<span data-ttu-id="ff13e-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-534">COLUMN_TYPE</span></span>|<span data-ttu-id="ff13e-535">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-535">Int16</span></span>|
|<span data-ttu-id="ff13e-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-536">DATA_TYPE</span></span>|<span data-ttu-id="ff13e-537">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-537">Int16</span></span>|
|<span data-ttu-id="ff13e-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ff13e-538">TYPE_NAME</span></span>|<span data-ttu-id="ff13e-539">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-539">String</span></span>|
|<span data-ttu-id="ff13e-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ff13e-540">COLUMN_SIZE</span></span>|<span data-ttu-id="ff13e-541">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-541">Int32</span></span>|
|<span data-ttu-id="ff13e-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="ff13e-543">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-543">Int32</span></span>|
|<span data-ttu-id="ff13e-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ff13e-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ff13e-545">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-545">Int16</span></span>|
|<span data-ttu-id="ff13e-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ff13e-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ff13e-547">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-547">Int16</span></span>|
|<span data-ttu-id="ff13e-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-548">NULLABLE</span></span>|<span data-ttu-id="ff13e-549">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-549">Int16</span></span>|
|<span data-ttu-id="ff13e-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ff13e-550">REMARKS</span></span>|<span data-ttu-id="ff13e-551">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-551">String</span></span>|
|<span data-ttu-id="ff13e-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ff13e-552">COLUMN_DEF</span></span>|<span data-ttu-id="ff13e-553">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-553">String</span></span>|
|<span data-ttu-id="ff13e-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ff13e-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ff13e-555">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-555">Int16</span></span>|
|<span data-ttu-id="ff13e-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ff13e-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ff13e-557">Int16</span><span class="sxs-lookup"><span data-stu-id="ff13e-557">Int16</span></span>|
|<span data-ttu-id="ff13e-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ff13e-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ff13e-559">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-559">Int32</span></span>|
|<span data-ttu-id="ff13e-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ff13e-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="ff13e-561">Int32</span><span class="sxs-lookup"><span data-stu-id="ff13e-561">Int32</span></span>|
|<span data-ttu-id="ff13e-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ff13e-562">IS_NULLABLE</span></span>|<span data-ttu-id="ff13e-563">String</span><span class="sxs-lookup"><span data-stu-id="ff13e-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="ff13e-564">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff13e-564">See also</span></span>

- [<span data-ttu-id="ff13e-565">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ff13e-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
