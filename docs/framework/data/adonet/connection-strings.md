---
title: 在 ADO.NET 中的连接字符串
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 078fdab257115296f9ff00330265cb14ff8674c8
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50409452"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="ad932-102">在 ADO.NET 中的连接字符串</span><span class="sxs-lookup"><span data-stu-id="ad932-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="ad932-103">连接字符串包含作为参数从数据提供程序传递到数据源的初始化信息。</span><span class="sxs-lookup"><span data-stu-id="ad932-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="ad932-104">数据提供程序接收的连接字符串的值作为<xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="ad932-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ad932-105">提供程序来分析连接字符串，并确保语法正确，以及支持的关键字。</span><span class="sxs-lookup"><span data-stu-id="ad932-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="ad932-106">然后<xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType>方法将已分析的连接参数传递到数据源。</span><span class="sxs-lookup"><span data-stu-id="ad932-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="ad932-107">数据源执行进一步的验证，并建立的连接。</span><span class="sxs-lookup"><span data-stu-id="ad932-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="ad932-108">连接字符串语法</span><span class="sxs-lookup"><span data-stu-id="ad932-108">Connection string syntax</span></span>

<span data-ttu-id="ad932-109">连接字符串是以分号分隔的键/值参数对的列表：</span><span class="sxs-lookup"><span data-stu-id="ad932-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>
  
    keyword1=value; keyword2=value;
  
<span data-ttu-id="ad932-110">关键字不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ad932-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="ad932-111">但是，值可能区分大小写，具体取决于数据源。</span><span class="sxs-lookup"><span data-stu-id="ad932-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="ad932-112">关键字和值可能包含[空白字符](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)。</span><span class="sxs-lookup"><span data-stu-id="ad932-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="ad932-113">在关键字中忽略和不带引号的前导和尾随空格的值。</span><span class="sxs-lookup"><span data-stu-id="ad932-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="ad932-114">如果值包含分号[Unicode 控制字符](https://en.wikipedia.org/wiki/Unicode_control_characters)，或前导空格或尾随空格，则必须用单引号或双引号括起来。</span><span class="sxs-lookup"><span data-stu-id="ad932-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="ad932-115">例如：</span><span class="sxs-lookup"><span data-stu-id="ad932-115">For example:</span></span>

    Keyword=" whitespace  ";
    Keyword='special;character';

<span data-ttu-id="ad932-116">它包含的值中可能不是封闭字符。</span><span class="sxs-lookup"><span data-stu-id="ad932-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="ad932-117">因此，仅在两个双引号，反之亦然，可以用一个值，包含单引号引起来：</span><span class="sxs-lookup"><span data-stu-id="ad932-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

<span data-ttu-id="ad932-118">引号本身，以及等号，不需要转义，因此以下连接字符串有效：</span><span class="sxs-lookup"><span data-stu-id="ad932-118">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

<span data-ttu-id="ad932-119">由于直到下一步分号或字符串的末尾读取每个值，后者的示例中的值是`a=b=c`，并最终分号是可选的。</span><span class="sxs-lookup"><span data-stu-id="ad932-119">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="ad932-120">所有连接字符串都共享相同的基本语法上面所述。</span><span class="sxs-lookup"><span data-stu-id="ad932-120">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="ad932-121">已识别的关键字集合取决于提供程序，但是，并已发展多年来从早期的 Api 如*ODBC*。</span><span class="sxs-lookup"><span data-stu-id="ad932-121">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="ad932-122">*.NET Framework*的数据提供程序*SQL Server* (`SqlClient`) 支持很多关键字从较旧的 Api，但更具灵活性并接受同义词的许多常见的连接字符串关键字。</span><span class="sxs-lookup"><span data-stu-id="ad932-122">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="ad932-123">键入了错误可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="ad932-123">Typing mistakes can cause errors.</span></span> <span data-ttu-id="ad932-124">例如，`Integrated Security=true`有效，但`IntegratedSecurity=true`将导致错误。</span><span class="sxs-lookup"><span data-stu-id="ad932-124">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="ad932-125">手动构造在运行时从未经验证的用户输入的连接字符串容易受到字符串注入式攻击，并会危及数据源的安全性。</span><span class="sxs-lookup"><span data-stu-id="ad932-125">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="ad932-126">若要解决这些问题*ADO.NET* 2.0 引入[的连接字符串生成器](../../../../docs/framework/data/adonet/connection-string-builders.md)每个 *.NET Framework*数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="ad932-126">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](../../../../docs/framework/data/adonet/connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="ad932-127">这些连接字符串生成器公开作为强类型化属性的参数，并使其可以发送到数据源之前验证的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="ad932-127">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ad932-128">本节内容</span><span class="sxs-lookup"><span data-stu-id="ad932-128">In This Section</span></span>  
 [<span data-ttu-id="ad932-129">连接字符串生成器</span><span class="sxs-lookup"><span data-stu-id="ad932-129">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 <span data-ttu-id="ad932-130">演示如何使用 `ConnectionStringBuilder` 类在运行时构造有效的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="ad932-130">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>
  
 [<span data-ttu-id="ad932-131">连接字符串和配置文件</span><span class="sxs-lookup"><span data-stu-id="ad932-131">Connection Strings and Configuration Files</span></span>](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 <span data-ttu-id="ad932-132">演示如何在配置文件中存储和检索连接字符串。</span><span class="sxs-lookup"><span data-stu-id="ad932-132">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>
  
 [<span data-ttu-id="ad932-133">连接字符串语法</span><span class="sxs-lookup"><span data-stu-id="ad932-133">Connection String Syntax</span></span>](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 <span data-ttu-id="ad932-134">描述如何为 `SqlClient`、`OracleClient`、`OleDb` 和 `Odbc` 配置提供程序专用的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="ad932-134">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>
  
 [<span data-ttu-id="ad932-135">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="ad932-135">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 <span data-ttu-id="ad932-136">演示保护用于连接到数据源的信息的各项技术。</span><span class="sxs-lookup"><span data-stu-id="ad932-136">Demonstrates techniques for protecting information used to connect to a data source.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ad932-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad932-137">See Also</span></span>  
 [<span data-ttu-id="ad932-138">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="ad932-138">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)  
 [<span data-ttu-id="ad932-139">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ad932-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
