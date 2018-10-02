---
title: 在 ADO.NET 中的连接字符串
ms.date: 03/30/2017
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 1e6e2b6870195c99279639e1f4576a30b7126d4d
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48029381"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="7505e-102">在 ADO.NET 中的连接字符串</span><span class="sxs-lookup"><span data-stu-id="7505e-102">Connection Strings in ADO.NET</span></span>
<span data-ttu-id="7505e-103">.NET Framework 2.0 引入了用于处理连接字符串的新功能（包括将新的关键字引入到连接字符串生成器类），这将有助于在运行时创建有效的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7505e-103">The .NET Framework 2.0 introduced new capabilities for working with connection strings, including the introduction of new keywords to the connection string builder classes, which facilitate creating valid connection strings at run time.</span></span>  
  
<span data-ttu-id="7505e-104">连接字符串包含作为参数从数据提供程序传递到数据源的初始化信息。</span><span class="sxs-lookup"><span data-stu-id="7505e-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="7505e-105">其语法取决于数据提供程序，并且会在试图打开连接的过程中对连接字符串进行分析。</span><span class="sxs-lookup"><span data-stu-id="7505e-105">The syntax depends on the data provider, and the connection string is parsed during the attempt to open a connection.</span></span> <span data-ttu-id="7505e-106">语法错误会生成运行时异常，但其他错误只有在数据源收到连接信息后才会发生。</span><span class="sxs-lookup"><span data-stu-id="7505e-106">Syntax errors generate a run-time exception, but other errors occur only after the data source receives connection information.</span></span> <span data-ttu-id="7505e-107">经过验证后，数据源将应用连接字符串中指定的选项并打开连接。</span><span class="sxs-lookup"><span data-stu-id="7505e-107">Once validated, the data source applies the options specified in the connection string and opens the connection.</span></span>
  
<span data-ttu-id="7505e-108">连接字符串的格式是使用分号分隔的键/值参数对列表：</span><span class="sxs-lookup"><span data-stu-id="7505e-108">The format of a connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>
  
    keyword1=value; keyword2=value;
  
<span data-ttu-id="7505e-109">关键字不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="7505e-109">Keywords are not case-sensitive.</span></span> <span data-ttu-id="7505e-110">但是，值可能区分大小写，具体取决于数据源。</span><span class="sxs-lookup"><span data-stu-id="7505e-110">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="7505e-111">关键字和值可能包含[空白字符](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)，尽管在关键字中忽略和不带引号的前导和尾随空格的值。</span><span class="sxs-lookup"><span data-stu-id="7505e-111">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode), although leading and trailing whitespace is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="7505e-112">如果值包含分号[Unicode 控制字符](https://en.wikipedia.org/wiki/Unicode_control_characters)、 前导空格或尾随的空格，则必须用单引号或双引号括起来，例如：</span><span class="sxs-lookup"><span data-stu-id="7505e-112">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), leading or trailing whitespace it must be enclosed in single or double quotation marks, e.g.:</span></span>

    Keyword=" whitespace  ";
    Keyword='special;character';

<span data-ttu-id="7505e-113">它包含的值中可能不是封闭字符。</span><span class="sxs-lookup"><span data-stu-id="7505e-113">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="7505e-114">因此，仅在两个双引号，反之亦然，则可以包含一个值，包含单引号引起来：</span><span class="sxs-lookup"><span data-stu-id="7505e-114">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks and vice versa:</span></span>

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

<span data-ttu-id="7505e-115">引号本身，以及等号，不需要转义，因此以下连接字符串有效：</span><span class="sxs-lookup"><span data-stu-id="7505e-115">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

<span data-ttu-id="7505e-116">由于直到下一步分号或字符串的末尾读取每个值，后者的示例中的值是`a=b=c`，并最终分号是可选的。</span><span class="sxs-lookup"><span data-stu-id="7505e-116">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="7505e-117">有效的连接字符串语法因提供程序而异，从早期的 API（如 ODBC）开始，已经过了多年的发展演变。</span><span class="sxs-lookup"><span data-stu-id="7505e-117">Valid connection string syntax depends on the provider, and has evolved over the years from earlier APIs like ODBC.</span></span> <span data-ttu-id="7505e-118">适用于 SQL Server 的 .NET Framework 数据提供程序 (SqlClient) 并入了早期语法中的许多元素，并且在使用通常的连接字符串语法时更具灵活性。</span><span class="sxs-lookup"><span data-stu-id="7505e-118">The .NET Framework Data Provider for SQL Server (SqlClient) incorporates many elements from older syntax and is generally more flexible with common connection string syntax.</span></span> <span data-ttu-id="7505e-119">连接字符串语法元素经常会出现一些同等有效的同义词，但有些语法和拼写错误可能会导致出现问题。</span><span class="sxs-lookup"><span data-stu-id="7505e-119">There are frequently equally valid synonyms for connection string syntax elements, but some syntax and spelling errors can cause problems.</span></span> <span data-ttu-id="7505e-120">例如，“`Integrated Security=true`”是有效的，而“`IntegratedSecurity=true`”则会导致出错。</span><span class="sxs-lookup"><span data-stu-id="7505e-120">For example, "`Integrated Security=true`" is valid, whereas "`IntegratedSecurity=true`" causes an error.</span></span> <span data-ttu-id="7505e-121">另外，在运行时从未验证的用户输入构造的连接字符串可能导致字符串注入式攻击，从而危害数据源的安全。</span><span class="sxs-lookup"><span data-stu-id="7505e-121">In addition, connection strings constructed at run time from unvalidated user input can lead to string injection attacks, jeopardizing security at the data source.</span></span>
  
<span data-ttu-id="7505e-122">为了解决这些问题，ADO.NET 2.0 为每个 .NET Framework 数据提供程序引入了新的连接字符串生成器。</span><span class="sxs-lookup"><span data-stu-id="7505e-122">To address these problems, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="7505e-123">关键字作为属性公开，以便在将连接字符串提交到数据源之前，能够对连接字符串语法进行验证。</span><span class="sxs-lookup"><span data-stu-id="7505e-123">Keywords are exposed as properties, enabling connection string syntax to be validated before submission to the data source.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7505e-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="7505e-124">In This Section</span></span>  
 [<span data-ttu-id="7505e-125">连接字符串生成器</span><span class="sxs-lookup"><span data-stu-id="7505e-125">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 <span data-ttu-id="7505e-126">演示如何使用 `ConnectionStringBuilder` 类在运行时构造有效的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7505e-126">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>
  
 [<span data-ttu-id="7505e-127">连接字符串和配置文件</span><span class="sxs-lookup"><span data-stu-id="7505e-127">Connection Strings and Configuration Files</span></span>](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 <span data-ttu-id="7505e-128">演示如何在配置文件中存储和检索连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7505e-128">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>
  
 [<span data-ttu-id="7505e-129">连接字符串语法</span><span class="sxs-lookup"><span data-stu-id="7505e-129">Connection String Syntax</span></span>](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 <span data-ttu-id="7505e-130">描述如何为 `SqlClient`、`OracleClient`、`OleDb` 和 `Odbc` 配置提供程序专用的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7505e-130">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>
  
 [<span data-ttu-id="7505e-131">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="7505e-131">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 <span data-ttu-id="7505e-132">演示保护用于连接到数据源的信息的各项技术。</span><span class="sxs-lookup"><span data-stu-id="7505e-132">Demonstrates techniques for protecting information used to connect to a data source.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7505e-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="7505e-133">See Also</span></span>  
 [<span data-ttu-id="7505e-134">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="7505e-134">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)  
 [<span data-ttu-id="7505e-135">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="7505e-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
