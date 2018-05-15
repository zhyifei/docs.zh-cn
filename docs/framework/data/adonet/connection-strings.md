---
title: 在 ADO.NET 中的连接字符串
ms.date: 03/30/2017
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 03d768430139fa1078f39b470403abcf75dd83a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="392f1-102">在 ADO.NET 中的连接字符串</span><span class="sxs-lookup"><span data-stu-id="392f1-102">Connection Strings in ADO.NET</span></span>
<span data-ttu-id="392f1-103">.NET Framework 2.0 引入了用于处理连接字符串的新功能（包括将新的关键字引入到连接字符串生成器类），这将有助于在运行时创建有效的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="392f1-103">The .NET Framework 2.0 introduced new capabilities for working with connection strings, including the introduction of new keywords to the connection string builder classes, which facilitate creating valid connection strings at run time.</span></span>  
  
 <span data-ttu-id="392f1-104">连接字符串包含作为参数从数据提供程序传递到数据源的初始化信息。</span><span class="sxs-lookup"><span data-stu-id="392f1-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="392f1-105">其语法取决于数据提供程序，并且会在试图打开连接的过程中对连接字符串进行分析。</span><span class="sxs-lookup"><span data-stu-id="392f1-105">The syntax depends on the data provider, and the connection string is parsed during the attempt to open a connection.</span></span> <span data-ttu-id="392f1-106">语法错误会生成运行时异常，但其他错误只有在数据源收到连接信息后才会发生。</span><span class="sxs-lookup"><span data-stu-id="392f1-106">Syntax errors generate a run-time exception, but other errors occur only after the data source receives connection information.</span></span> <span data-ttu-id="392f1-107">经过验证后，数据源将应用连接字符串中指定的选项并打开连接。</span><span class="sxs-lookup"><span data-stu-id="392f1-107">Once validated, the data source applies the options specified in the connection string and opens the connection.</span></span>  
  
 <span data-ttu-id="392f1-108">连接字符串的格式是使用分号分隔的键/值参数对列表：</span><span class="sxs-lookup"><span data-stu-id="392f1-108">The format of a connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>  
  
 `keyword1=value; keyword2=value;`  
  
 <span data-ttu-id="392f1-109">关键字不区分大小写，并将忽略键/值对之间的空格。</span><span class="sxs-lookup"><span data-stu-id="392f1-109">Keywords are not case sensitive, and spaces between key/value pairs are ignored.</span></span> <span data-ttu-id="392f1-110">不过，根据数据源的不同，值可能是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="392f1-110">However, values may be case sensitive, depending on the data source.</span></span> <span data-ttu-id="392f1-111">任何包含分号、单引号或双引号的值必须用双引号引起来。</span><span class="sxs-lookup"><span data-stu-id="392f1-111">Any values containing a semicolon, single quotation marks, or double quotation marks must be enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="392f1-112">有效的连接字符串语法因提供程序而异，从早期的 API（如 ODBC）开始，已经过了多年的发展演变。</span><span class="sxs-lookup"><span data-stu-id="392f1-112">Valid connection string syntax depends on the provider, and has evolved over the years from earlier APIs like ODBC.</span></span> <span data-ttu-id="392f1-113">适用于 SQL Server 的 .NET Framework 数据提供程序 (SqlClient) 并入了早期语法中的许多元素，并且在使用通常的连接字符串语法时更具灵活性。</span><span class="sxs-lookup"><span data-stu-id="392f1-113">The .NET Framework Data Provider for SQL Server (SqlClient) incorporates many elements from older syntax and is generally more flexible with common connection string syntax.</span></span> <span data-ttu-id="392f1-114">连接字符串语法元素经常会出现一些同等有效的同义词，但有些语法和拼写错误可能会导致出现问题。</span><span class="sxs-lookup"><span data-stu-id="392f1-114">There are frequently equally valid synonyms for connection string syntax elements, but some syntax and spelling errors can cause problems.</span></span> <span data-ttu-id="392f1-115">例如，“`Integrated Security=true`”是有效的，而“`IntegratedSecurity=true`”则会导致出错。</span><span class="sxs-lookup"><span data-stu-id="392f1-115">For example, "`Integrated Security=true`" is valid, whereas "`IntegratedSecurity=true`" causes an error.</span></span> <span data-ttu-id="392f1-116">另外，在运行时从未验证的用户输入构造的连接字符串可能导致字符串注入式攻击，从而危害数据源的安全。</span><span class="sxs-lookup"><span data-stu-id="392f1-116">In addition, connection strings constructed at run time from unvalidated user input can lead to string injection attacks, jeopardizing security at the data source.</span></span>  
  
 <span data-ttu-id="392f1-117">为了解决这些问题，ADO.NET 2.0 为每个 .NET Framework 数据提供程序引入了新的连接字符串生成器。</span><span class="sxs-lookup"><span data-stu-id="392f1-117">To address these problems, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="392f1-118">关键字作为属性公开，以便在将连接字符串提交到数据源之前，能够对连接字符串语法进行验证。</span><span class="sxs-lookup"><span data-stu-id="392f1-118">Keywords are exposed as properties, enabling connection string syntax to be validated before submission to the data source.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="392f1-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="392f1-119">In This Section</span></span>  
 [<span data-ttu-id="392f1-120">连接字符串生成器</span><span class="sxs-lookup"><span data-stu-id="392f1-120">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 <span data-ttu-id="392f1-121">演示如何使用 `ConnectionStringBuilder` 类在运行时构造有效的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="392f1-121">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>  
  
 [<span data-ttu-id="392f1-122">连接字符串和配置文件</span><span class="sxs-lookup"><span data-stu-id="392f1-122">Connection Strings and Configuration Files</span></span>](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 <span data-ttu-id="392f1-123">演示如何在配置文件中存储和检索连接字符串。</span><span class="sxs-lookup"><span data-stu-id="392f1-123">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>  
  
 [<span data-ttu-id="392f1-124">连接字符串语法</span><span class="sxs-lookup"><span data-stu-id="392f1-124">Connection String Syntax</span></span>](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 <span data-ttu-id="392f1-125">描述如何为 `SqlClient`、`OracleClient`、`OleDb` 和 `Odbc` 配置提供程序专用的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="392f1-125">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>  
  
 [<span data-ttu-id="392f1-126">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="392f1-126">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 <span data-ttu-id="392f1-127">演示保护用于连接到数据源的信息的各项技术。</span><span class="sxs-lookup"><span data-stu-id="392f1-127">Demonstrates techniques for protecting information used to connect to a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="392f1-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="392f1-128">See Also</span></span>  
 [<span data-ttu-id="392f1-129">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="392f1-129">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)  
 [<span data-ttu-id="392f1-130">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="392f1-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
