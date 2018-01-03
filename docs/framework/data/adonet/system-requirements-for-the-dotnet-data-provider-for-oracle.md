---
title: "Oracle 的 .NET Framework 数据提供程序的系统需求"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054f76b9-1737-43f0-8160-84a00a387217
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: cb21a71a548766ee5439c6a558ea7f23d1f45364
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="system-requirements-for-the-net-framework-data-provider-for-oracle"></a><span data-ttu-id="63b07-102">Oracle 的 .NET Framework 数据提供程序的系统需求</span><span class="sxs-lookup"><span data-stu-id="63b07-102">System Requirements for the .NET Framework Data Provider for Oracle</span></span>
<span data-ttu-id="63b07-103">Oracle .NET Framework 数据提供程序需要 Microsoft 数据访问组件 (MDAC) 2.6 版或更高版本。</span><span class="sxs-lookup"><span data-stu-id="63b07-103">The .NET Framework Data Provider for Oracle requires Microsoft Data Access Components (MDAC) version 2.6 or later.</span></span> <span data-ttu-id="63b07-104">建议使用 MDAC 2.8 SP1。</span><span class="sxs-lookup"><span data-stu-id="63b07-104">MDAC 2.8 SP1 is recommended.</span></span>  
  
 <span data-ttu-id="63b07-105">还必须安装 Oracle 8i Release 3 (8.1.7) 客户端或更高版本。</span><span class="sxs-lookup"><span data-stu-id="63b07-105">You must also have Oracle 8i Release 3 (8.1.7) Client or later installed.</span></span>  
  
 <span data-ttu-id="63b07-106">Oracle 9i 版本之前的 Oracle 客户端软件无法访问 UTF16 数据库，因为 UTF16 是 Oracle 9i 中的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="63b07-106">Oracle Client software prior to version Oracle 9i cannot access UTF16 databases because UTF16 is a new feature in Oracle 9i.</span></span> <span data-ttu-id="63b07-107">要使用此功能，必须将客户端软件升级到 Oracle 9i 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="63b07-107">To use this feature, you must upgrade your client software to Oracle 9i or later.</span></span>  
  
## <a name="working-with-the-data-provider-for-oracle-and-unicode-data"></a><span data-ttu-id="63b07-108">使用 Oracle 数据提供程序和 Unicode 数据</span><span class="sxs-lookup"><span data-stu-id="63b07-108">Working with the Data Provider for Oracle and Unicode Data</span></span>  
 <span data-ttu-id="63b07-109">下表列出在使用 Oracle .NET Framework 数据提供程序和 Oracle 客户端库时，应考虑的与 Unicode 有关的问题。</span><span class="sxs-lookup"><span data-stu-id="63b07-109">Following is a list of Unicode-related issues that you should consider when working with the .NET Framework Data Provider for Oracle and Oracle client libraries.</span></span> <span data-ttu-id="63b07-110">有关更多信息，请参见 Oracle 文档。</span><span class="sxs-lookup"><span data-stu-id="63b07-110">For more information, see your Oracle documentation.</span></span>  
  
### <a name="setting-the-unicode-value-in-a-connection-string-attribute"></a><span data-ttu-id="63b07-111">在连接字符串属性中设置 Unicode 值</span><span class="sxs-lookup"><span data-stu-id="63b07-111">Setting the Unicode Value in a Connection String Attribute</span></span>  
 <span data-ttu-id="63b07-112">在使用 Oracle 时，可以使用连接字符串属性</span><span class="sxs-lookup"><span data-stu-id="63b07-112">When working with Oracle, you can use the connection string attribute</span></span>  
  
```  
Unicode=True   
```  
  
 <span data-ttu-id="63b07-113">在 UTF-16 模式下初始化 Oracle 客户端库。</span><span class="sxs-lookup"><span data-stu-id="63b07-113">to initialize the Oracle client libraries in UTF-16 mode.</span></span> <span data-ttu-id="63b07-114">这样可以使 Oracle 客户端库接受 UTF-16（与 UCS-2 非常类似），而不是多字节字符串。</span><span class="sxs-lookup"><span data-stu-id="63b07-114">This causes the Oracle client libraries to accept UTF-16 (which is very similar to UCS-2) instead of multi-byte strings.</span></span> <span data-ttu-id="63b07-115">这样，Oracle 数据提供程序始终可以使用任何 Oracle 代码页，不需要进行其他转换工作。</span><span class="sxs-lookup"><span data-stu-id="63b07-115">This allows the Data Provider for Oracle to always work with any Oracle code page without additional translation work.</span></span> <span data-ttu-id="63b07-116">只有使用 Oracle 9i 客户端与包含备选字符集 AL16UTF16 的 Oracle 9i 数据库进行通信时，此配置才有效。</span><span class="sxs-lookup"><span data-stu-id="63b07-116">This configuration only works if you are using Oracle 9i clients to communicate with an Oracle 9i database with the alternate character set of AL16UTF16.</span></span> <span data-ttu-id="63b07-117">当 Oracle 9i 客户端与 Oracle 9i 服务器进行通信时，其他资源所需转换 Unicode **CommandText**为相应的多字节字符的值设置为 Oracle9i 服务器使用。</span><span class="sxs-lookup"><span data-stu-id="63b07-117">When an Oracle 9i client communicates with an Oracle 9i server, additional resources are required to convert the Unicode **CommandText** values to the appropriate multi-byte character set that the Oracle9i server uses.</span></span> <span data-ttu-id="63b07-118">如果确定已通过将 `Unicode=True` 添加到连接字符串中而拥有了安全的配置，则可以避免此问题。</span><span class="sxs-lookup"><span data-stu-id="63b07-118">This can be avoided when you know that you have the safe configuration by adding `Unicode=True` to your connection string.</span></span>  
  
### <a name="mixing-versions-of-oracle-client-and-oracle-server"></a><span data-ttu-id="63b07-119">混合版本的 Oracle 客户端和 Oracle 服务器</span><span class="sxs-lookup"><span data-stu-id="63b07-119">Mixing Versions of Oracle Client and Oracle Server</span></span>  
 <span data-ttu-id="63b07-120">Oracle 8i 客户端无法访问**NCHAR**， **NVARCHAR2**，或**NCLOB**时服务器的国家字符集指定为 AL16UTF16 的 Oracle 9i 数据库中的数据 (默认设置对于 Oracle 9i）。</span><span class="sxs-lookup"><span data-stu-id="63b07-120">Oracle 8i clients cannot access **NCHAR**, **NVARCHAR2**, or **NCLOB** data in Oracle 9i databases when the server's national character set is specified as AL16UTF16 (the default setting for Oracle 9i).</span></span> <span data-ttu-id="63b07-121">因为直到 Oracle 9i 才引入对 UTF-16 字符集的支持，Oracle 8i 客户端无法读取。</span><span class="sxs-lookup"><span data-stu-id="63b07-121">Because support for the UTF-16 character set was not introduced until Oracle 9i, Oracle 8i clients cannot read it.</span></span>  
  
### <a name="working-with-utf-8-data"></a><span data-ttu-id="63b07-122">使用 UTF-8 数据</span><span class="sxs-lookup"><span data-stu-id="63b07-122">Working with UTF-8 Data</span></span>  
 <span data-ttu-id="63b07-123">要设置备选字符集，将注册表项 HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE\HOMEID\NLS_LANG 设置为 UTF8。</span><span class="sxs-lookup"><span data-stu-id="63b07-123">To set the alternate character set, set the Registry Key HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE\HOMEID\NLS_LANG to UTF8.</span></span> <span data-ttu-id="63b07-124">有关更多信息，请参见适合您的平台的 Oracle 安装说明。</span><span class="sxs-lookup"><span data-stu-id="63b07-124">See the Oracle Installation notes on your platform for more information.</span></span> <span data-ttu-id="63b07-125">默认设置为安装 Oracle 客户端软件所使用的语言的主要字符集。</span><span class="sxs-lookup"><span data-stu-id="63b07-125">The default setting is the primary character set of the language from which you are installing the Oracle Client software.</span></span> <span data-ttu-id="63b07-126">如果设置的语言与所连接的数据库的国家语言字符集不匹配，将使参数和列绑定使用主要数据库字符集发送或接收数据，而不是使用国家字符集。</span><span class="sxs-lookup"><span data-stu-id="63b07-126">Not setting the language to match the national language character set of the database to which you are connecting will cause parameter and column bindings to send or receive data in your primary database character set, not the national character set.</span></span>  
  
### <a name="oraclelob-can-only-update-full-characters"></a><span data-ttu-id="63b07-127">OracleLob 只能更新完整字符。</span><span class="sxs-lookup"><span data-stu-id="63b07-127">OracleLob Can Only Update Full Characters.</span></span>  
 <span data-ttu-id="63b07-128">出于可用性原因，<xref:System.Data.OracleClient.OracleLob>对象继承自.NET Framework 流的类，并提供**ReadByte**和**WriteByte**方法。</span><span class="sxs-lookup"><span data-stu-id="63b07-128">For usability reasons, the <xref:System.Data.OracleClient.OracleLob> object inherits from the .NET Framework Stream class, and provides **ReadByte** and **WriteByte** methods.</span></span> <span data-ttu-id="63b07-129">它还实现方法，如**CopyTo**和**擦除**，则该工作上的 Oracle 部分**LOB**对象。</span><span class="sxs-lookup"><span data-stu-id="63b07-129">It also implements methods, such as **CopyTo** and **Erase**, that work on sections of Oracle **LOB** objects.</span></span> <span data-ttu-id="63b07-130">与此相反，Oracle 客户端软件提供大量的 Api 来使用字符**LOB**s (**CLOB**和**NCLOB**)。</span><span class="sxs-lookup"><span data-stu-id="63b07-130">In contrast, Oracle client software provides a number of APIs to work with character **LOB**s (**CLOB** and **NCLOB**).</span></span> <span data-ttu-id="63b07-131">但是，这些 API 只适用于完整字符。</span><span class="sxs-lookup"><span data-stu-id="63b07-131">However, these APIs work on full characters only.</span></span> <span data-ttu-id="63b07-132">因为这一区别，Oracle 数据提供程序实现支持**读取**和**ReadByte**以便以便方式使用 utf-16 数据。</span><span class="sxs-lookup"><span data-stu-id="63b07-132">Because of this difference, the Data Provider for Oracle implements support for **Read** and **ReadByte** to work with UTF-16 data in a byte-wise manner.</span></span> <span data-ttu-id="63b07-133">但是，其他方法的**OracleLob**对象只允许完整字符操作。</span><span class="sxs-lookup"><span data-stu-id="63b07-133">However, the other methods of the **OracleLob** object only allow full-character operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b07-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="63b07-134">See Also</span></span>  
 [<span data-ttu-id="63b07-135">Oracle 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="63b07-135">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="63b07-136">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="63b07-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
