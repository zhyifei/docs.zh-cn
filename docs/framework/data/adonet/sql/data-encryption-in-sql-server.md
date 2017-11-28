---
title: "SQL Server 中的数据加密"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4428cf8fbfcaa853ca2c877a8cc4902f585b6754
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="data-encryption-in-sql-server"></a><span data-ttu-id="55bf9-102">SQL Server 中的数据加密</span><span class="sxs-lookup"><span data-stu-id="55bf9-102">Data Encryption in SQL Server</span></span>
<span data-ttu-id="55bf9-103">SQL Server 提供了使用证书、非对称密钥或对称密钥对数据进行加密和解密的功能。</span><span class="sxs-lookup"><span data-stu-id="55bf9-103">SQL Server provides functions to encrypt and decrypt data using a certificate, asymmetric key, or symmetric key.</span></span> <span data-ttu-id="55bf9-104">它在一个内部证书存储中管理所有这些证书或密钥。</span><span class="sxs-lookup"><span data-stu-id="55bf9-104">It manages all of these in an internal certificate store.</span></span> <span data-ttu-id="55bf9-105">该存储使用加密层次结构，可在层次结构中的上一层级别保护证书和密钥。</span><span class="sxs-lookup"><span data-stu-id="55bf9-105">The store uses an encryption hierarchy that secures certificates and keys at one level with the layer above it in the hierarchy.</span></span> <span data-ttu-id="55bf9-106">SQL Server 的此功能区域称为“机密存储”。</span><span class="sxs-lookup"><span data-stu-id="55bf9-106">This feature area of SQL Server is called Secret Storage.</span></span>  
  
 <span data-ttu-id="55bf9-107">加密功能支持的最快加密模式是对称密钥加密。</span><span class="sxs-lookup"><span data-stu-id="55bf9-107">The fastest mode of encryption supported by the encryption functions is symmetric key encryption.</span></span> <span data-ttu-id="55bf9-108">此模式适用于处理大量数据。</span><span class="sxs-lookup"><span data-stu-id="55bf9-108">This mode is suitable for handling large volumes of data.</span></span> <span data-ttu-id="55bf9-109">可以通过证书、密码或其他对称密钥加密对称密钥。</span><span class="sxs-lookup"><span data-stu-id="55bf9-109">The symmetric keys can be encrypted by certificates, passwords or other symmetric keys.</span></span>  
  
## <a name="keys-and-algorithms"></a><span data-ttu-id="55bf9-110">密钥和算法</span><span class="sxs-lookup"><span data-stu-id="55bf9-110">Keys and Algorithms</span></span>  
 <span data-ttu-id="55bf9-111">SQL Server 支持多种对称密钥加密算法，包括 DES、Triple DES、RC2、RC4、128 位 RC4、DESX、128 位 AES、192 位 AES 和 256 位 AES。</span><span class="sxs-lookup"><span data-stu-id="55bf9-111">SQL Server supports several symmetric key encryption algorithms, including DES, Triple DES, RC2, RC4, 128-bit RC4, DESX, 128-bit AES, 192-bit AES, and 256-bit AES.</span></span> <span data-ttu-id="55bf9-112">这些算法使用 Windows 加密 API 实现。</span><span class="sxs-lookup"><span data-stu-id="55bf9-112">The algorithms are implemented using the Windows Crypto API.</span></span>  
  
 <span data-ttu-id="55bf9-113">在数据库连接范围内，SQL Server 可以保留多个开放式对称密钥。</span><span class="sxs-lookup"><span data-stu-id="55bf9-113">Within the scope of a database connection, SQL Server can maintain multiple open symmetric keys.</span></span> <span data-ttu-id="55bf9-114">开放式密钥从存储中进行检索，并可用于解密数据。</span><span class="sxs-lookup"><span data-stu-id="55bf9-114">An open key is retrieved from the store and is available for decrypting data.</span></span> <span data-ttu-id="55bf9-115">解密一段数据时，不需要指定要使用的对称密钥。</span><span class="sxs-lookup"><span data-stu-id="55bf9-115">When a piece of data is decrypted, there is no need to specify the symmetric key to use.</span></span> <span data-ttu-id="55bf9-116">每个加密的值均包含用于加密该值的密钥的密钥标识符（密钥 GUID）。</span><span class="sxs-lookup"><span data-stu-id="55bf9-116">Each encrypted value contains the key identifier (key GUID) of the key used to encrypt it.</span></span> <span data-ttu-id="55bf9-117">如果已解密正确的密钥并且该密钥已开放，则引擎会将加密的字节流匹配到开放式对称密钥。</span><span class="sxs-lookup"><span data-stu-id="55bf9-117">The engine matches the encrypted byte stream to an open symmetric key, if the correct key has been decrypted and is open.</span></span> <span data-ttu-id="55bf9-118">然后使用此密钥执行解密并返回数据。</span><span class="sxs-lookup"><span data-stu-id="55bf9-118">This key is then used to perform decryption and return the data.</span></span> <span data-ttu-id="55bf9-119">如果正确的密钥未开放，则返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="55bf9-119">If the correct key is not open, NULL is returned.</span></span>  
  
 <span data-ttu-id="55bf9-120">有关演示如何使用数据库中的加密数据示例，请参阅[How to： 加密列数据](http://go.microsoft.com/fwlink/?LinkID=128559)SQL Server 联机丛书中。</span><span class="sxs-lookup"><span data-stu-id="55bf9-120">For an example that shows how to work with encrypted data in a database, see [How to: Encrypt a Column of Data](http://go.microsoft.com/fwlink/?LinkID=128559) in SQL Server Books Online.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="55bf9-121">外部资源</span><span class="sxs-lookup"><span data-stu-id="55bf9-121">External Resources</span></span>  
 <span data-ttu-id="55bf9-122">有关数据加密的更多信息，请参见以下资源。</span><span class="sxs-lookup"><span data-stu-id="55bf9-122">For more information on data encryption, see the following resources.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55bf9-123">[SQL Server 加密](http://msdn.microsoft.com/library/bb510663.aspx)SQL Server 联机丛书中</span><span class="sxs-lookup"><span data-stu-id="55bf9-123">[SQL Server Encryption](http://msdn.microsoft.com/library/bb510663.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="55bf9-124">概述了 SQL Server 中的加密。</span><span class="sxs-lookup"><span data-stu-id="55bf9-124">Provides an overview of encryption in SQL Serve.</span></span> <span data-ttu-id="55bf9-125">此主题包括到其他主题和帮助主题的链接。</span><span class="sxs-lookup"><span data-stu-id="55bf9-125">This topic includes links to additional topics and how-to's.</span></span>|  
|<span data-ttu-id="55bf9-126">[加密层次结构](http://msdn.microsoft.com/library/ms189586.aspx)和[加密操作指南主题](http://msdn.microsoft.com/library/aa337557.aspx)SQL Server 联机丛书中</span><span class="sxs-lookup"><span data-stu-id="55bf9-126">[Encryption Hierarchy](http://msdn.microsoft.com/library/ms189586.aspx) and [Encryption How-to Topics](http://msdn.microsoft.com/library/aa337557.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="55bf9-127">概述了 SQL Server 中的加密。</span><span class="sxs-lookup"><span data-stu-id="55bf9-127">Provides an overview of encryption in SQL Server.</span></span> <span data-ttu-id="55bf9-128">此主题提供到其他主题和帮助主题的链接。</span><span class="sxs-lookup"><span data-stu-id="55bf9-128">This topic provides links to additional topics and how-to's.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55bf9-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55bf9-129">See Also</span></span>  
 [<span data-ttu-id="55bf9-130">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="55bf9-130">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="55bf9-131">SQL Server 中的应用程序安全方案</span><span class="sxs-lookup"><span data-stu-id="55bf9-131">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="55bf9-132">SQL Server 中的身份验证</span><span class="sxs-lookup"><span data-stu-id="55bf9-132">Authentication in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [<span data-ttu-id="55bf9-133">服务器和 SQL Server 中的数据库角色</span><span class="sxs-lookup"><span data-stu-id="55bf9-133">Server and Database Roles in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 [<span data-ttu-id="55bf9-134">所有权和 SQL Server 中的用户架构分离</span><span class="sxs-lookup"><span data-stu-id="55bf9-134">Ownership and User-Schema Separation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 [<span data-ttu-id="55bf9-135">授权和 SQL Server 中的权限</span><span class="sxs-lookup"><span data-stu-id="55bf9-135">Authorization and Permissions in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 [<span data-ttu-id="55bf9-136">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="55bf9-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
