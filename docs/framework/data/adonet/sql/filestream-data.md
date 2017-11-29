---
title: "FILESTREAM 数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2fde543187d1904da93be255878d6c7a99de6bbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="filestream-data"></a><span data-ttu-id="02d30-102">FILESTREAM 数据</span><span class="sxs-lookup"><span data-stu-id="02d30-102">FILESTREAM Data</span></span>
<span data-ttu-id="02d30-103">FILESTREAM 存储特性用于 varbinary(max) 列中存储的二进制 (BLOB) 数据。</span><span class="sxs-lookup"><span data-stu-id="02d30-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="02d30-104">在 FILESTREAM 之前，存储二进制数据需要特殊处理。</span><span class="sxs-lookup"><span data-stu-id="02d30-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="02d30-105">非结构化的数据（例如文本文档、图像和视频）通常存储在数据库之外，从而使得难以管理此类数据。</span><span class="sxs-lookup"><span data-stu-id="02d30-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02d30-106">您必须安装 .NET Framework 3.5 SP1（或更高版本）才能使用 SqlClient 处理 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="02d30-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>  
  
 <span data-ttu-id="02d30-107">在 varbinary(max) 列上指定 FILESTREAM 特性会造成 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 将数据存储在本地 NTFS 文件系统中，而不是存储在数据库文件中。</span><span class="sxs-lookup"><span data-stu-id="02d30-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="02d30-108">虽然数据是单独存储的，但您可以使用所支持的相同 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 语句来处理存储在数据库中的 varbinary(max) 数据。</span><span class="sxs-lookup"><span data-stu-id="02d30-108">Although it is stored separately, you can use the same [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>  
  
## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="02d30-109">SqlClient 对 FILESTREAM 的支持</span><span class="sxs-lookup"><span data-stu-id="02d30-109">SqlClient Support for FILESTREAM</span></span>  
 <span data-ttu-id="02d30-110">用于 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 的 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 数据提供程序 (<xref:System.Data.SqlClient>) 支持使用在 <xref:System.Data.SqlTypes.SqlFileStream> 命名空间中定义的 <xref:System.Data.SqlTypes> 类来读写 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="02d30-110">The [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="02d30-111">`SqlFileStream` 继承自 <xref:System.IO.Stream> 类，该类提供了用于读写数据流的方法。</span><span class="sxs-lookup"><span data-stu-id="02d30-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="02d30-112">从流读取数据可将数据从流传输到一个数据结构，例如一个字节数组。</span><span class="sxs-lookup"><span data-stu-id="02d30-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="02d30-113">写入操作可将数据从该数据结构传输到一个流。</span><span class="sxs-lookup"><span data-stu-id="02d30-113">Writing transfers the data from the data structure into a stream.</span></span>  
  
### <a name="creating-the-includessnoversionincludesssnoversion-mdmd-table"></a><span data-ttu-id="02d30-114">创建 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 表</span><span class="sxs-lookup"><span data-stu-id="02d30-114">Creating the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Table</span></span>  
 <span data-ttu-id="02d30-115">下列 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 语句将创建一个名为 employees 的表并插入一行数据。</span><span class="sxs-lookup"><span data-stu-id="02d30-115">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="02d30-116">启用 FILESTREAM 存储之后，您可以将此表与下面的代码示例结合使用。</span><span class="sxs-lookup"><span data-stu-id="02d30-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="02d30-117">本主题的最后提供了指向 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 联机丛书中资源的链接。</span><span class="sxs-lookup"><span data-stu-id="02d30-117">The links to resources in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online are located at the end of this topic.</span></span>  
  
```  
CREATE TABLE employees  
(  
  EmployeeId INT  NOT NULL  PRIMARY KEY,  
  Photo VARBINARY(MAX) FILESTREAM  NULL,  
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL  
  UNIQUE DEFAULT NEWID()  
)  
GO  
Insert into employees  
Values(1, 0x00, default)  
GO  
```  
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="02d30-118">示例：读取、覆盖和插入 FILESTREAM 数据</span><span class="sxs-lookup"><span data-stu-id="02d30-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>  
 <span data-ttu-id="02d30-119">下面的示例演示如何从 FILESTREAM 读取数据。</span><span class="sxs-lookup"><span data-stu-id="02d30-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="02d30-120">示例代码获取文件的逻辑路径，并将 `FileAccess` 设置为 `Read`，而将 `FileOptions` 设置为 `SequentialScan`。</span><span class="sxs-lookup"><span data-stu-id="02d30-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="02d30-121">然后，示例代码将字节从 SqlFileStream 读入到缓存区中，</span><span class="sxs-lookup"><span data-stu-id="02d30-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="02d30-122">最后将这些字节写入到控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="02d30-122">The bytes are then written to the console window.</span></span>  
  
 <span data-ttu-id="02d30-123">该示例还演示如何将数据写入 FILESTREAM（其中，所有现有的数据都将被覆盖）。</span><span class="sxs-lookup"><span data-stu-id="02d30-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="02d30-124">示例代码获取文件的逻辑路径，然后创建 `SqlFileStream`，并将 `FileAccess` 设置为 `Write`，而将 `FileOptions` 设置为 `SequentialScan`。</span><span class="sxs-lookup"><span data-stu-id="02d30-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="02d30-125">将一个单字节写入到 `SqlFileStream`，从而替换文件中的任何数据。</span><span class="sxs-lookup"><span data-stu-id="02d30-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>  
  
 <span data-ttu-id="02d30-126">该示例还演示了如何通过使用 Seek 方法将数据追加到文件末尾将数据写入 FILESTREAM。</span><span class="sxs-lookup"><span data-stu-id="02d30-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="02d30-127">示例代码获取文件的逻辑路径，然后创建 `SqlFileStream`，并将 `FileAccess` 设置为 `ReadWrite`，而将 `FileOptions` 设置为 `SequentialScan`。</span><span class="sxs-lookup"><span data-stu-id="02d30-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="02d30-128">示例代码使用 Seek 方法找到文件结尾，并将一个单字节追加到现有的文件中。</span><span class="sxs-lookup"><span data-stu-id="02d30-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Data;  
using System.IO;  
  
namespace FileStreamTest  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");  
            ReadFilestream(builder);  
            OverwriteFilestream(builder);  
            InsertFilestream(builder);  
  
            Console.WriteLine("Done");  
        }  
  
        private static void ReadFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for the file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Read the contents as bytes and write them to the console  
                            for (long index = 0; index < fileStream.Length; index++)  
                            {  
                                Console.WriteLine(fileStream.ReadByte());  
                            }  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void OverwriteFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file   
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Write a single byte to the file. This will  
                            // replace any data in the file.  
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void InsertFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Seek to the end of the file  
                            fileStream.Seek(0, SeekOrigin.End);  
  
                            // Append a single byte   
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
  
        }  
    }  
} using (SqlConnection connection = new SqlConnection(  
    connStringBuilder.ToString()))  
{  
    connection.Open();  
  
    SqlCommand command = new SqlCommand("", connection);  
    command.CommandText = "select Top(1) Photo.PathName(), "  
    + "GET_FILESTREAM_TRANSACTION_CONTEXT () from employees";  
  
    SqlTransaction tran = connection.BeginTransaction(  
        System.Data.IsolationLevel.ReadCommitted);  
    command.Transaction = tran;  
  
    using (SqlDataReader reader = command.ExecuteReader())  
    {  
        while (reader.Read())  
        {  
            // Get the pointer for file  
            string path = reader.GetString(0);  
            byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
            FileStream fileStream = new SqlFileStream(path,  
                (byte[])reader.GetValue(1),  
                FileAccess.ReadWrite,  
                FileOptions.SequentialScan, 0);  
  
            // Seek to the end of the file  
            fs.Seek(0, SeekOrigin.End);  
  
            // Append a single byte   
            fileStream.WriteByte(0x01);  
            fileStream.Close();  
        }  
    }  
    tran.Commit();  
}  
```  
  
 <span data-ttu-id="02d30-129">另一个示例，请参阅[如何存储和提取到文件流列的二进制数据](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str)。</span><span class="sxs-lookup"><span data-stu-id="02d30-129">For another sample, see [How to store and fetch binary data into a file stream column](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>  
  
## <a name="resources-in-includessnoversionincludesssnoversion-mdmd-books-online"></a><span data-ttu-id="02d30-130">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 联机丛书中的资源</span><span class="sxs-lookup"><span data-stu-id="02d30-130">Resources in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online</span></span>  
 <span data-ttu-id="02d30-131">FILESTREAM 的完整文档位于 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 联机丛书中的以下各节中。</span><span class="sxs-lookup"><span data-stu-id="02d30-131">The complete documentation for FILESTREAM is located in the following sections in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
|<span data-ttu-id="02d30-132">主题</span><span class="sxs-lookup"><span data-stu-id="02d30-132">Topic</span></span>|<span data-ttu-id="02d30-133">描述</span><span class="sxs-lookup"><span data-stu-id="02d30-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02d30-134">[设计和实现 FILESTREAM 存储](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="02d30-134">[Designing and Implementing FILESTREAM Storage](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span></span>|<span data-ttu-id="02d30-135">提供指向 FILESTREAM 文档和相关主题的链接。</span><span class="sxs-lookup"><span data-stu-id="02d30-135">Provides links to FILESTREAM documentation and related topics.</span></span>|  
|<span data-ttu-id="02d30-136">[FILESTREAM 概述](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="02d30-136">[FILESTREAM Overview](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span></span>|<span data-ttu-id="02d30-137">介绍何时使用 FILESTREAM 存储以及该存储如何将 SQL Server 数据库引擎与 NTFS 文件系统集成。</span><span class="sxs-lookup"><span data-stu-id="02d30-137">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|  
|<span data-ttu-id="02d30-138">[FILESTREAM 存储入门](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="02d30-138">[Getting Started with FILESTREAM Storage](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span></span>|<span data-ttu-id="02d30-139">介绍如何在 SQL Server 的实例上启用 FILESTREAM，如何创建数据库和表以存储 FILESTREAM 数据以及如何操作包含 FILESTREAM 数据的行。</span><span class="sxs-lookup"><span data-stu-id="02d30-139">Describes how to enable FILESTREAM on an instance of SQL Server, how to create a database and a table to stored FILESTREAM data, and how to manipulate rows containing FILESTREAM data.</span></span>|  
|<span data-ttu-id="02d30-140">[在客户端应用程序中使用 FILESTREAM 存储](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="02d30-140">[Using FILESTREAM Storage in Client Applications](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span></span>|<span data-ttu-id="02d30-141">介绍用于处理 FILESTREAM 数据的 Win32 API 函数。</span><span class="sxs-lookup"><span data-stu-id="02d30-141">Describes the Win32 API functions for working with FILESTREAM data.</span></span>|  
|<span data-ttu-id="02d30-142">[FILESTREAM 与其他 SQL Server 功能](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="02d30-142">[FILESTREAM and Other SQL Server Features](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)</span></span>|<span data-ttu-id="02d30-143">提供将 FILESTREAM 数据与 SQL Server 的其他功能一起使用时的注意事项、准则和限制。</span><span class="sxs-lookup"><span data-stu-id="02d30-143">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02d30-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02d30-144">See Also</span></span>  
 [<span data-ttu-id="02d30-145">SQL Server 数据类型和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="02d30-145">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="02d30-146">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="02d30-146">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="02d30-147">代码访问安全性和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="02d30-147">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [<span data-ttu-id="02d30-148">SQL Server 二进制和大值数据</span><span class="sxs-lookup"><span data-stu-id="02d30-148">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="02d30-149">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="02d30-149">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
