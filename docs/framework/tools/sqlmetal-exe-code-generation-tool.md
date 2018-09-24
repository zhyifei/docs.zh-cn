---
title: SqlMetal.exe（代码生成工具）
ms.date: 03/30/2017
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
ms.openlocfilehash: 94ed6328857f6e77cea150d69719322d3aaaea69
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46002887"
---
# <a name="sqlmetalexe-code-generation-tool"></a><span data-ttu-id="8ad63-102">SqlMetal.exe（代码生成工具）</span><span class="sxs-lookup"><span data-stu-id="8ad63-102">SqlMetal.exe (Code Generation Tool)</span></span>
<span data-ttu-id="8ad63-103">SqlMetal 命令行工具可为 [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] 的 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]组件生成代码和映射。</span><span class="sxs-lookup"><span data-stu-id="8ad63-103">The SqlMetal command-line tool generates code and mapping for the [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)] component of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="8ad63-104">通过应用本主题后面出现的选项，可以指示 SqlMetal 执行若干种不同的操作，其中包括：</span><span class="sxs-lookup"><span data-stu-id="8ad63-104">By applying options that appear later in this topic, you can instruct SqlMetal to perform several different actions that include the following:</span></span>  
  
-   <span data-ttu-id="8ad63-105">从数据库生成源代码和映射特性或映射文件。</span><span class="sxs-lookup"><span data-stu-id="8ad63-105">From a database, generate source code and mapping attributes or a mapping file.</span></span>  
  
-   <span data-ttu-id="8ad63-106">从数据库生成供自定义使用的中间数据库标记语言 (.dbml) 文件。</span><span class="sxs-lookup"><span data-stu-id="8ad63-106">From a database, generate an intermediate database markup language (.dbml) file for customization.</span></span>  
  
-   <span data-ttu-id="8ad63-107">从 .dbml 文件生成代码和映射特性或映射文件。</span><span class="sxs-lookup"><span data-stu-id="8ad63-107">From a .dbml file, generate code and mapping attributes or a mapping file.</span></span>  
  
 <span data-ttu-id="8ad63-108">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="8ad63-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="8ad63-109">默认情况下，此文件位于 `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin 下。</span><span class="sxs-lookup"><span data-stu-id="8ad63-109">By default, the file is located at `drive`:\Program Files\Microsoft SDKs\Windows\v`n.nn`\bin.</span></span> <span data-ttu-id="8ad63-110">如果没有安装 Visual Studio，也可以通过下载 [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225)获取 SQLMetal 文件。</span><span class="sxs-lookup"><span data-stu-id="8ad63-110">If you do not install Visual Studio, you can also get the SQLMetal file by downloading the [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ad63-111">使用 Visual Studio 的开发人员还可以使用 [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] 生成实体类。</span><span class="sxs-lookup"><span data-stu-id="8ad63-111">Developers who use Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../includes/vs-ordesigner-long-md.md)] to generate entity classes.</span></span> <span data-ttu-id="8ad63-112">对于大型数据库，这种命令行方法具有很好的扩展性。</span><span class="sxs-lookup"><span data-stu-id="8ad63-112">The command-line approach scales well for large databases.</span></span> <span data-ttu-id="8ad63-113">由于 SqlMetal 是一个命令行工具，因此可以在生成过程中使用它。</span><span class="sxs-lookup"><span data-stu-id="8ad63-113">Because SqlMetal is a command-line tool, you can use it in a build process.</span></span>  
  
 <span data-ttu-id="8ad63-114">若要运行此工具，请使用开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="8ad63-114">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="8ad63-115">有关详细信息，请参阅[命令提示符](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="8ad63-115">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ad63-116">语法</span><span class="sxs-lookup"><span data-stu-id="8ad63-116">Syntax</span></span>  
  
```  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a><span data-ttu-id="8ad63-117">选项</span><span class="sxs-lookup"><span data-stu-id="8ad63-117">Options</span></span>  
 <span data-ttu-id="8ad63-118">要查看最新的选项列表，请在安装位置的命令提示符处键入 `sqlmetal /?` 。</span><span class="sxs-lookup"><span data-stu-id="8ad63-118">To view the most current option list, type `sqlmetal /?` at a command prompt from the installed location.</span></span>  
  
 <span data-ttu-id="8ad63-119">**连接选项**</span><span class="sxs-lookup"><span data-stu-id="8ad63-119">**Connection Options**</span></span>  
  
|<span data-ttu-id="8ad63-120">选项</span><span class="sxs-lookup"><span data-stu-id="8ad63-120">Option</span></span>|<span data-ttu-id="8ad63-121">描述</span><span class="sxs-lookup"><span data-stu-id="8ad63-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8ad63-122">/server: \<name></span><span class="sxs-lookup"><span data-stu-id="8ad63-122">**/server:** *\<name>*</span></span>|<span data-ttu-id="8ad63-123">指定数据库服务器名称。</span><span class="sxs-lookup"><span data-stu-id="8ad63-123">Specifies database server name.</span></span>|  
|<span data-ttu-id="8ad63-124">/database: \<name></span><span class="sxs-lookup"><span data-stu-id="8ad63-124">**/database:** *\<name>*</span></span>|<span data-ttu-id="8ad63-125">指定服务器上的数据库目录。</span><span class="sxs-lookup"><span data-stu-id="8ad63-125">Specifies database catalog on server.</span></span>|  
|<span data-ttu-id="8ad63-126">/user: \<name></span><span class="sxs-lookup"><span data-stu-id="8ad63-126">**/user:** *\<name>*</span></span>|<span data-ttu-id="8ad63-127">指定登录用户 ID。默认值：使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="8ad63-127">Specifies logon user id. Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="8ad63-128">/password: \<password></span><span class="sxs-lookup"><span data-stu-id="8ad63-128">**/password:** *\<password>*</span></span>|<span data-ttu-id="8ad63-129">指定登录密码。</span><span class="sxs-lookup"><span data-stu-id="8ad63-129">Specifies logon password.</span></span> <span data-ttu-id="8ad63-130">默认值：使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="8ad63-130">Default value: Use Windows authentication.</span></span>|  
|<span data-ttu-id="8ad63-131">/conn: \<connection string></span><span class="sxs-lookup"><span data-stu-id="8ad63-131">**/conn:** *\<connection string>*</span></span>|<span data-ttu-id="8ad63-132">指定数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="8ad63-132">Specifies database connection string.</span></span> <span data-ttu-id="8ad63-133">不能与 **/server**、 **/database**、 **/user**或 **/password** 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="8ad63-133">Cannot be used with **/server**, **/database**, **/user**, or **/password** options.</span></span><br /><br /> <span data-ttu-id="8ad63-134">不要在连接字符串中包含文件名，</span><span class="sxs-lookup"><span data-stu-id="8ad63-134">Do not include the file name in the connection string.</span></span> <span data-ttu-id="8ad63-135">而应将文件名作为输入文件添加到命令行中。</span><span class="sxs-lookup"><span data-stu-id="8ad63-135">Instead, add the file name to the command line as the input file.</span></span> <span data-ttu-id="8ad63-136">例如，下一行命令将“c:\northwnd.mdf”指定为输入文件： **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**。</span><span class="sxs-lookup"><span data-stu-id="8ad63-136">For example, the following line specifies "c:\northwnd.mdf" as the input file: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"**.</span></span>|  
|<span data-ttu-id="8ad63-137">/timeout: \<seconds></span><span class="sxs-lookup"><span data-stu-id="8ad63-137">**/timeout:** *\<seconds>*</span></span>|<span data-ttu-id="8ad63-138">指定 SqlMetal 访问数据库时的超时值。</span><span class="sxs-lookup"><span data-stu-id="8ad63-138">Specifies time-out value when SqlMetal accesses the database.</span></span> <span data-ttu-id="8ad63-139">默认值：0（即没有时间限制）。</span><span class="sxs-lookup"><span data-stu-id="8ad63-139">Default value: 0 (that is, no time limit).</span></span>|  
  
 <span data-ttu-id="8ad63-140">**提取选项**</span><span class="sxs-lookup"><span data-stu-id="8ad63-140">**Extraction options**</span></span>  
  
|<span data-ttu-id="8ad63-141">选项</span><span class="sxs-lookup"><span data-stu-id="8ad63-141">Option</span></span>|<span data-ttu-id="8ad63-142">描述</span><span class="sxs-lookup"><span data-stu-id="8ad63-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8ad63-143">**/views**</span><span class="sxs-lookup"><span data-stu-id="8ad63-143">**/views**</span></span>|<span data-ttu-id="8ad63-144">提取数据库视图。</span><span class="sxs-lookup"><span data-stu-id="8ad63-144">Extracts database views.</span></span>|  
|<span data-ttu-id="8ad63-145">**/functions**</span><span class="sxs-lookup"><span data-stu-id="8ad63-145">**/functions**</span></span>|<span data-ttu-id="8ad63-146">提取数据库函数。</span><span class="sxs-lookup"><span data-stu-id="8ad63-146">Extracts database functions.</span></span>|  
|<span data-ttu-id="8ad63-147">**/sprocs**</span><span class="sxs-lookup"><span data-stu-id="8ad63-147">**/sprocs**</span></span>|<span data-ttu-id="8ad63-148">提取存储过程。</span><span class="sxs-lookup"><span data-stu-id="8ad63-148">Extracts stored procedures.</span></span>|  
  
 <span data-ttu-id="8ad63-149">**输出选项**</span><span class="sxs-lookup"><span data-stu-id="8ad63-149">**Output options**</span></span>  
  
|<span data-ttu-id="8ad63-150">选项</span><span class="sxs-lookup"><span data-stu-id="8ad63-150">Option</span></span>|<span data-ttu-id="8ad63-151">描述</span><span class="sxs-lookup"><span data-stu-id="8ad63-151">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8ad63-152">**/dbml** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="8ad63-152">**/dbml** *[:file]*</span></span>|<span data-ttu-id="8ad63-153">采用 .dbml 格式发送输出。</span><span class="sxs-lookup"><span data-stu-id="8ad63-153">Sends output as .dbml.</span></span> <span data-ttu-id="8ad63-154">不能与 **/map** 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="8ad63-154">Cannot be used with **/map** option.</span></span>|  
|<span data-ttu-id="8ad63-155">**/code** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="8ad63-155">**/code** *[:file]*</span></span>|<span data-ttu-id="8ad63-156">以源代码形式发送输出。</span><span class="sxs-lookup"><span data-stu-id="8ad63-156">Sends output as source code.</span></span> <span data-ttu-id="8ad63-157">不能与 **/dbml** 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="8ad63-157">Cannot be used with **/dbml** option.</span></span>|  
|<span data-ttu-id="8ad63-158">**/map** *[:file]*</span><span class="sxs-lookup"><span data-stu-id="8ad63-158">**/map** *[:file]*</span></span>|<span data-ttu-id="8ad63-159">生成 XML 映射文件而不是特性。</span><span class="sxs-lookup"><span data-stu-id="8ad63-159">Generates an XML mapping file instead of attributes.</span></span> <span data-ttu-id="8ad63-160">不能与 **/dbml** 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="8ad63-160">Cannot be used with **/dbml** option.</span></span>|  
  
 <span data-ttu-id="8ad63-161">**杂项**</span><span class="sxs-lookup"><span data-stu-id="8ad63-161">**Miscellaneous**</span></span>  
  
|<span data-ttu-id="8ad63-162">选项</span><span class="sxs-lookup"><span data-stu-id="8ad63-162">Option</span></span>|<span data-ttu-id="8ad63-163">描述</span><span class="sxs-lookup"><span data-stu-id="8ad63-163">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8ad63-164">/language: \<language></span><span class="sxs-lookup"><span data-stu-id="8ad63-164">**/language:** *\<language>*</span></span>|<span data-ttu-id="8ad63-165">指定源代码语言。</span><span class="sxs-lookup"><span data-stu-id="8ad63-165">Specifies source code language.</span></span><br /><br /> <span data-ttu-id="8ad63-166">有效 \<language>：vb、csharp。</span><span class="sxs-lookup"><span data-stu-id="8ad63-166">Valid *\<language>*: vb, csharp.</span></span><br /><br /> <span data-ttu-id="8ad63-167">默认值：从代码文件的扩展名派生。</span><span class="sxs-lookup"><span data-stu-id="8ad63-167">Default value: Derived from extension on code file name.</span></span>|  
|<span data-ttu-id="8ad63-168">/namespace: \<name></span><span class="sxs-lookup"><span data-stu-id="8ad63-168">**/namespace:** *\<name>*</span></span>|<span data-ttu-id="8ad63-169">为生成的代码指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="8ad63-169">Specifies namespace of the generated code.</span></span> <span data-ttu-id="8ad63-170">默认值：无命名空间。</span><span class="sxs-lookup"><span data-stu-id="8ad63-170">Default value: no namespace.</span></span>|  
|<span data-ttu-id="8ad63-171">/context: \<type></span><span class="sxs-lookup"><span data-stu-id="8ad63-171">**/context:** *\<type>*</span></span>|<span data-ttu-id="8ad63-172">指定数据上下文类的名称。</span><span class="sxs-lookup"><span data-stu-id="8ad63-172">Specifies name of data context class.</span></span> <span data-ttu-id="8ad63-173">默认值：从数据库名称派生。</span><span class="sxs-lookup"><span data-stu-id="8ad63-173">Default value: Derived from database name.</span></span>|  
|<span data-ttu-id="8ad63-174">/entitybase: \<type></span><span class="sxs-lookup"><span data-stu-id="8ad63-174">**/entitybase:** *\<type>*</span></span>|<span data-ttu-id="8ad63-175">指定生成的代码中的实体类的基类。</span><span class="sxs-lookup"><span data-stu-id="8ad63-175">Specifies the base class of the entity classes in the generated code.</span></span> <span data-ttu-id="8ad63-176">默认值：实体没有基类。</span><span class="sxs-lookup"><span data-stu-id="8ad63-176">Default value: Entities have no base class.</span></span>|  
|<span data-ttu-id="8ad63-177">**/pluralize**</span><span class="sxs-lookup"><span data-stu-id="8ad63-177">**/pluralize**</span></span>|<span data-ttu-id="8ad63-178">自动为类和成员名称应用复数或单数形式。</span><span class="sxs-lookup"><span data-stu-id="8ad63-178">Automatically pluralizes or singularizes class and member names.</span></span><br /><br /> <span data-ttu-id="8ad63-179">此选项仅在美国可用。英文版。</span><span class="sxs-lookup"><span data-stu-id="8ad63-179">This option is available only in the U.S. English version.</span></span>|  
|<span data-ttu-id="8ad63-180">/serialization: \<option></span><span class="sxs-lookup"><span data-stu-id="8ad63-180">**/serialization:** *\<option>*</span></span>|<span data-ttu-id="8ad63-181">生成可序列化类。</span><span class="sxs-lookup"><span data-stu-id="8ad63-181">Generates serializable classes.</span></span><br /><br /> <span data-ttu-id="8ad63-182">有效 \<option>：None、Unidirectional。</span><span class="sxs-lookup"><span data-stu-id="8ad63-182">Valid *\<option>*: None, Unidirectional.</span></span> <span data-ttu-id="8ad63-183">默认值：None。</span><span class="sxs-lookup"><span data-stu-id="8ad63-183">Default value: None.</span></span><br /><br /> <span data-ttu-id="8ad63-184">有关详细信息，请参阅[序列化](../../../docs/framework/data/adonet/sql/linq/serialization.md)。</span><span class="sxs-lookup"><span data-stu-id="8ad63-184">For more information, see [Serialization](../../../docs/framework/data/adonet/sql/linq/serialization.md).</span></span>|  
  
 <span data-ttu-id="8ad63-185">**输入文件**</span><span class="sxs-lookup"><span data-stu-id="8ad63-185">**Input File**</span></span>  
  
|<span data-ttu-id="8ad63-186">选项</span><span class="sxs-lookup"><span data-stu-id="8ad63-186">Option</span></span>|<span data-ttu-id="8ad63-187">描述</span><span class="sxs-lookup"><span data-stu-id="8ad63-187">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8ad63-188">\<input file></span><span class="sxs-lookup"><span data-stu-id="8ad63-188">**\<input file>**</span></span>|<span data-ttu-id="8ad63-189">指定 SQL Server Express .mdf 文件、 [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf 文件或 .dbml 中间文件。</span><span class="sxs-lookup"><span data-stu-id="8ad63-189">Specifies a SQL Server Express .mdf file, a [!INCLUDE[ssEW](../../../includes/ssew-md.md)] .sdf file, or a .dbml intermediate file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ad63-190">备注</span><span class="sxs-lookup"><span data-stu-id="8ad63-190">Remarks</span></span>  
 <span data-ttu-id="8ad63-191">SqlMetal 功能实际涉及两个步骤：</span><span class="sxs-lookup"><span data-stu-id="8ad63-191">SqlMetal functionality actually involves two steps:</span></span>  
  
-   <span data-ttu-id="8ad63-192">将数据库的元数据提取到一个 .dbml 文件中。</span><span class="sxs-lookup"><span data-stu-id="8ad63-192">Extracting the metadata of the database into a .dbml file.</span></span>  
  
-   <span data-ttu-id="8ad63-193">生成一个代码输出文件。</span><span class="sxs-lookup"><span data-stu-id="8ad63-193">Generating a code output file.</span></span>  
  
     <span data-ttu-id="8ad63-194">通过使用适当的命令行选项，可以生成 Visual Basic 或 C# 源代码，也可以生成 XML 映射文件。</span><span class="sxs-lookup"><span data-stu-id="8ad63-194">By using the appropriate command-line options, you can produce Visual Basic or C# source code, or you can produce an XML mapping file.</span></span>  
  
 <span data-ttu-id="8ad63-195">若要从 .mdf 文件中提取元数据，必须在所有其他选项后指定 .mdf 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8ad63-195">To extract the metadata from an .mdf file, you must specify the name of the .mdf file after all other options.</span></span>  
  
 <span data-ttu-id="8ad63-196">如果没有指定 **/server** ，则假定为 **localhost/sqlexpress** 。</span><span class="sxs-lookup"><span data-stu-id="8ad63-196">If no **/server** is specified, **localhost/sqlexpress** is assumed.</span></span>  
  
 <span data-ttu-id="8ad63-197">如果存在下列一种或多种情况，[!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)] 将引发异常：</span><span class="sxs-lookup"><span data-stu-id="8ad63-197">[!INCLUDE[sqprsqext](../../../includes/sqprsqext-md.md)] throws an exception if one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="8ad63-198">SqlMetal 尝试提取进行自我调用的存储过程。</span><span class="sxs-lookup"><span data-stu-id="8ad63-198">SqlMetal tries to extract a stored procedure that calls itself.</span></span>  
  
-   <span data-ttu-id="8ad63-199">存储过程、函数或视图的嵌套级别超过 32。</span><span class="sxs-lookup"><span data-stu-id="8ad63-199">The nesting level of a stored procedure, function, or view exceeds 32.</span></span>  
  
     <span data-ttu-id="8ad63-200">SqlMetal 将捕获此异常并将其报告为警告。</span><span class="sxs-lookup"><span data-stu-id="8ad63-200">SqlMetal catches this exception and reports it as a warning.</span></span>  
  
 <span data-ttu-id="8ad63-201">若要指定一个输入文件名，请将该名称作为输入文件添加到命令行。</span><span class="sxs-lookup"><span data-stu-id="8ad63-201">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="8ad63-202">不支持在连接字符串中包含文件名（使用 **/conn** 选项）。</span><span class="sxs-lookup"><span data-stu-id="8ad63-202">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8ad63-203">示例</span><span class="sxs-lookup"><span data-stu-id="8ad63-203">Examples</span></span>  
 <span data-ttu-id="8ad63-204">生成一个包含提取的 SQL 元数据的 .dbml 文件：</span><span class="sxs-lookup"><span data-stu-id="8ad63-204">Generate a .dbml file that includes extracted SQL metadata:</span></span>  
  
 <span data-ttu-id="8ad63-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span><span class="sxs-lookup"><span data-stu-id="8ad63-205">**sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**</span></span>  
  
 <span data-ttu-id="8ad63-206">使用 SQL Server Express 生成一个包含从 .mdf 文件中提取的 SQL 元数据的 .dbml 文件：</span><span class="sxs-lookup"><span data-stu-id="8ad63-206">Generate a .dbml file that includes extracted SQL metadata from an .mdf file by using SQL Server Express:</span></span>  
  
 <span data-ttu-id="8ad63-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span><span class="sxs-lookup"><span data-stu-id="8ad63-207">**sqlmetal /dbml:mymeta.dbml mydbfile.mdf**</span></span>  
  
 <span data-ttu-id="8ad63-208">生成一个包含从 SQL Server Express 中提取的 SQL 元数据的 .dbml 文件：</span><span class="sxs-lookup"><span data-stu-id="8ad63-208">Generate a .dbml file that includes extracted SQL metadata from SQL Server Express:</span></span>  
  
 <span data-ttu-id="8ad63-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span><span class="sxs-lookup"><span data-stu-id="8ad63-209">**sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**</span></span>  
  
 <span data-ttu-id="8ad63-210">从 .dbml 元数据文件生成源代码：</span><span class="sxs-lookup"><span data-stu-id="8ad63-210">Generate source code from a .dbml metadata file:</span></span>  
  
 <span data-ttu-id="8ad63-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span><span class="sxs-lookup"><span data-stu-id="8ad63-211">**sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**</span></span>  
  
 <span data-ttu-id="8ad63-212">直接从 SQL 元数据生成源代码：</span><span class="sxs-lookup"><span data-stu-id="8ad63-212">Generate source code from SQL metadata directly:</span></span>  
  
 <span data-ttu-id="8ad63-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span><span class="sxs-lookup"><span data-stu-id="8ad63-213">**sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ad63-214">如果对 Northwind 示例数据库应用 **/pluralize** 选项，请注意以下行为。</span><span class="sxs-lookup"><span data-stu-id="8ad63-214">When you use the **/pluralize** option with the Northwind sample database, note the following behavior.</span></span> <span data-ttu-id="8ad63-215">如果 SqlMetal 为表创建了行类型的名称，表名将采用单数形式。</span><span class="sxs-lookup"><span data-stu-id="8ad63-215">When SqlMetal makes row-type names for tables, the table names are singular.</span></span> <span data-ttu-id="8ad63-216">如果它为表创建了 <xref:System.Data.Linq.DataContext> 属性，则表名将采用复数形式。</span><span class="sxs-lookup"><span data-stu-id="8ad63-216">When it makes <xref:System.Data.Linq.DataContext> properties for tables, the table names are plural.</span></span> <span data-ttu-id="8ad63-217">巧合的是，Northwind 示例数据库中的表名已采用复数形式。</span><span class="sxs-lookup"><span data-stu-id="8ad63-217">Coincidentally, the tables in the Northwind sample database are already plural.</span></span> <span data-ttu-id="8ad63-218">因此，你将看不到这种效果。</span><span class="sxs-lookup"><span data-stu-id="8ad63-218">Therefore, you do not see that part working.</span></span> <span data-ttu-id="8ad63-219">尽管数据库表普遍命名为单数形式，但在 .NET 中，将集合命名为复数形式也是一种常见的做法。</span><span class="sxs-lookup"><span data-stu-id="8ad63-219">Although it is common practice to name database tables singular, it is also a common practice in .NET to name collections plural.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad63-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ad63-220">See Also</span></span>  
 [<span data-ttu-id="8ad63-221">如何：在 Visual Basic 或 C# 中生成对象模型</span><span class="sxs-lookup"><span data-stu-id="8ad63-221">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 [<span data-ttu-id="8ad63-222">LINQ to SQL 中的代码生成</span><span class="sxs-lookup"><span data-stu-id="8ad63-222">Code Generation in LINQ to SQL</span></span>](../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="8ad63-223">外部映射</span><span class="sxs-lookup"><span data-stu-id="8ad63-223">External Mapping</span></span>](../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
