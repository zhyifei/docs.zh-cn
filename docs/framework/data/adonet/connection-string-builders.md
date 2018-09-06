---
title: 连接字符串生成器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: 1c65b0c2c9ae19aa008ecd8fb453d8e41b7c4167
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43737498"
---
# <a name="connection-string-builders"></a><span data-ttu-id="d4f6a-102">连接字符串生成器</span><span class="sxs-lookup"><span data-stu-id="d4f6a-102">Connection String Builders</span></span>
<span data-ttu-id="d4f6a-103">在早期版本的[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]的编译时检查的值未出现，串联的字符串包含连接字符串，以便在运行时，不正确的关键字生成<xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-103">In earlier versions of [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], compile-time checking of connection strings with concatenated string values did not occur, so that at run time, an incorrect keyword generated an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="d4f6a-104">每个 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 数据提供程序支持的连接字符串关键字的语法不同，这使得手动构造有效连接字符串变得很困难。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-104">Each of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers supported different syntax for connection string keywords, which made constructing valid connection strings difficult if done manually.</span></span> <span data-ttu-id="d4f6a-105">为了解决这个问题，[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 为每个 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 数据提供程序引入了新的连接字符串生成器。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-105">To address this problem, [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 introduced new connection string builders for each [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="d4f6a-106">每个数据提供程序包括一个从 <xref:System.Data.Common.DbConnectionStringBuilder> 继承的强类型连接字符串生成器类。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-106">Each data provider includes a strongly typed connection string builder class that inherits from <xref:System.Data.Common.DbConnectionStringBuilder>.</span></span> <span data-ttu-id="d4f6a-107">下表列出了 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 数据提供程序及其关联的连接字符串生成器类。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-107">The following table lists the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers and their associated connection string builder classes.</span></span>  
  
|<span data-ttu-id="d4f6a-108">提供程序</span><span class="sxs-lookup"><span data-stu-id="d4f6a-108">Provider</span></span>|<span data-ttu-id="d4f6a-109">ConnectionStringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="d4f6a-109">ConnectionStringBuilder class</span></span>|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a><span data-ttu-id="d4f6a-110">连接字符串注入式攻击</span><span class="sxs-lookup"><span data-stu-id="d4f6a-110">Connection String Injection Attacks</span></span>  
 <span data-ttu-id="d4f6a-111">当使用动态字符串串联根据用户输入生成连接字符串时，可能发生连接字符串注入式攻击。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-111">A connection string injection attack can occur when dynamic string concatenation is used to build connection strings that are based on user input.</span></span> <span data-ttu-id="d4f6a-112">如果未验证字符串并且未转义恶意文本或字符，则攻击者可能会访问服务器上的敏感数据或其他资源。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-112">If the string is not validated and malicious text or characters not escaped, an attacker can potentially access sensitive data or other resources on the server.</span></span> <span data-ttu-id="d4f6a-113">例如，攻击者可以通过提供分号并追加其他值来发起攻击。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-113">For example, an attacker could mount an attack by supplying a semicolon and appending an additional value.</span></span> <span data-ttu-id="d4f6a-114">连接字符串通过“last one wins”算法分析，恶意的输入被替换为合法的值。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-114">The connection string is parsed by using a "last one wins" algorithm, and the hostile input is substituted for a legitimate value.</span></span>  
  
 <span data-ttu-id="d4f6a-115">连接字符串生成器类旨在排除推测，防止出现语法错误和安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-115">The connection string builder classes are designed to eliminate guesswork and protect against syntax errors and security vulnerabilities.</span></span> <span data-ttu-id="d4f6a-116">它们提供与每个数据提供程序允许的已知键/值对相对应的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-116">They provide methods and properties corresponding to the known key/value pairs permitted by each data provider.</span></span> <span data-ttu-id="d4f6a-117">每个类都保持一个固定的同义词集合，可以将同义词转换为相应的已知键名。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-117">Each class maintains a fixed collection of synonyms and can translate from a synonym to the corresponding well-known key name.</span></span> <span data-ttu-id="d4f6a-118">将执行键/值对的有效性检查，无效对会引发异常。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-118">Checks are performed for valid key/value pairs and an invalid pair throws an exception.</span></span> <span data-ttu-id="d4f6a-119">此外，还会以一种安全方式处理插入的值。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-119">In addition, injected values are handled in a safe manner.</span></span>  
  
 <span data-ttu-id="d4f6a-120">下面的示例演示 <xref:System.Data.SqlClient.SqlConnectionStringBuilder> 如何处理为 `Initial Catalog` 设置插入的额外值。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-120">The following example demonstrates how the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handles an inserted extra value for the `Initial Catalog` setting.</span></span>  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 <span data-ttu-id="d4f6a-121">输出结果表明，通过用双引号转义该额外值而不作为新的键/值对将其追加到连接字符串，<xref:System.Data.SqlClient.SqlConnectionStringBuilder> 可以正确处理此额外值。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-121">The output shows that the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handled this correctly by escaping the extra value in double quotation marks instead of appending it to the connection string as a new key/value pair.</span></span>  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a><span data-ttu-id="d4f6a-122">从配置文件生成连接字符串</span><span class="sxs-lookup"><span data-stu-id="d4f6a-122">Building Connection Strings from Configuration Files</span></span>  
 <span data-ttu-id="d4f6a-123">如果事先知道连接字符串的某些元素，则可以将其存储在配置文件中，并在运行时检索它们以构造完整连接字符串。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-123">If certain elements of a connection string are known beforehand, they can be stored in a configuration file and retrieved at run time to construct a complete connection string.</span></span> <span data-ttu-id="d4f6a-124">例如，可能事先知道数据库的名称，但不知道服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-124">For example, the name of the database might be known in advance, but not the name of the server.</span></span> <span data-ttu-id="d4f6a-125">或者，您可能希望用户在运行时提供用户名和密码，而不能在连接字符串中插入其他值。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-125">Or you might want a user to supply a name and password at run time without being able to inject other values into the connection string.</span></span>  
  
 <span data-ttu-id="d4f6a-126">连接字符串生成器的一个重载构造函数将 <xref:System.String> 作为参数，这可让您提供部分连接字符串，然后通过用户输入使这部分连接字符串成为完整字符串。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-126">One of the overloaded constructors for a connection string builder takes a <xref:System.String> as an argument, which enables you to supply a partial connection string that can then be completed from user input.</span></span> <span data-ttu-id="d4f6a-127">该部分连接字符串可以存储在配置文件中并在运行时进行检索。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-127">The partial connection string can be stored in a configuration file and retrieved at run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4f6a-128"><xref:System.Configuration> 命名空间允许通过编程方式访问配置文件（对 Web 应用程序使用 <xref:System.Web.Configuration.WebConfigurationManager>，对 Windows 应用程序使用 <xref:System.Configuration.ConfigurationManager>）。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-128">The <xref:System.Configuration> namespace allows programmatic access to configuration files that use the <xref:System.Web.Configuration.WebConfigurationManager> for Web applications and the <xref:System.Configuration.ConfigurationManager> for Windows applications.</span></span> <span data-ttu-id="d4f6a-129">有关使用连接字符串和配置文件的详细信息，请参阅[连接字符串和配置文件](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-129">For more information about working with connection strings and configuration files, see [Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="d4f6a-130">示例</span><span class="sxs-lookup"><span data-stu-id="d4f6a-130">Example</span></span>  
 <span data-ttu-id="d4f6a-131">此示例演示如何从配置文件中检索部分连接字符串并通过设置 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> 的 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>、<xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> 和 <xref:System.Data.SqlClient.SqlConnectionStringBuilder> 属性完成该连接字符串。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-131">This example demonstrates retrieving a partial connection string from a configuration file and completing it by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, and <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> properties of the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span> <span data-ttu-id="d4f6a-132">配置文件定义如下。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-132">The configuration file is defined as follows.</span></span>  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="d4f6a-133">必须在项目中设置对 `System.Configuration.dll` 的引用，才能运行代码。</span><span class="sxs-lookup"><span data-stu-id="d4f6a-133">You must set a reference to the `System.Configuration.dll` in your project for the code to run.</span></span>  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d4f6a-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4f6a-134">See Also</span></span>  
 [<span data-ttu-id="d4f6a-135">连接字符串</span><span class="sxs-lookup"><span data-stu-id="d4f6a-135">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="d4f6a-136">隐私和数据安全性</span><span class="sxs-lookup"><span data-stu-id="d4f6a-136">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 [<span data-ttu-id="d4f6a-137">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="d4f6a-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
