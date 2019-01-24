---
title: FILESTREAM 数据
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 4002f95e47b3c1ac7d8415d590b8c4c8a5d95a91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701087"
---
# <a name="filestream-data"></a><span data-ttu-id="40d0d-102">FILESTREAM 数据</span><span class="sxs-lookup"><span data-stu-id="40d0d-102">FILESTREAM Data</span></span>
<span data-ttu-id="40d0d-103">FILESTREAM 存储特性用于 varbinary(max) 列中存储的二进制 (BLOB) 数据。</span><span class="sxs-lookup"><span data-stu-id="40d0d-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="40d0d-104">在 FILESTREAM 之前，存储二进制数据需要特殊处理。</span><span class="sxs-lookup"><span data-stu-id="40d0d-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="40d0d-105">非结构化的数据（例如文本文档、图像和视频）通常存储在数据库之外，从而使得难以管理此类数据。</span><span class="sxs-lookup"><span data-stu-id="40d0d-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40d0d-106">您必须安装 .NET Framework 3.5 SP1（或更高版本）才能使用 SqlClient 处理 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="40d0d-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>  
  
 <span data-ttu-id="40d0d-107">在 varbinary(max) 列上指定 FILESTREAM 属性可使 SQL Server 将数据存储在本地 NTFS 文件系统中，而不是存储在数据库文件中。</span><span class="sxs-lookup"><span data-stu-id="40d0d-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes SQL Server to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="40d0d-108">虽然数据是单独存储的，但您可以使用所支持的相同 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 语句来处理存储在数据库中的 varbinary(max) 数据。</span><span class="sxs-lookup"><span data-stu-id="40d0d-108">Although it is stored separately, you can use the same [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>  
  
## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="40d0d-109">SqlClient 对 FILESTREAM 的支持</span><span class="sxs-lookup"><span data-stu-id="40d0d-109">SqlClient Support for FILESTREAM</span></span>  
 <span data-ttu-id="40d0d-110">[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] SQL Server 数据提供程序<xref:System.Data.SqlClient>，支持对 FILESTREAM 数据使用读取和写入<xref:System.Data.SqlTypes.SqlFileStream>类中定义<xref:System.Data.SqlTypes>命名空间。</span><span class="sxs-lookup"><span data-stu-id="40d0d-110">The [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server, <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="40d0d-111">`SqlFileStream` 继承自 <xref:System.IO.Stream> 类，该类提供了用于读写数据流的方法。</span><span class="sxs-lookup"><span data-stu-id="40d0d-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="40d0d-112">从流读取数据可将数据从流传输到一个数据结构，例如一个字节数组。</span><span class="sxs-lookup"><span data-stu-id="40d0d-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="40d0d-113">写入操作可将数据从该数据结构传输到一个流。</span><span class="sxs-lookup"><span data-stu-id="40d0d-113">Writing transfers the data from the data structure into a stream.</span></span>  
  
### <a name="creating-the-sql-server-table"></a><span data-ttu-id="40d0d-114">创建 SQL Server 表</span><span class="sxs-lookup"><span data-stu-id="40d0d-114">Creating the SQL Server Table</span></span>  
 <span data-ttu-id="40d0d-115">下列 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 语句将创建一个名为 employees 的表并插入一行数据。</span><span class="sxs-lookup"><span data-stu-id="40d0d-115">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="40d0d-116">启用 FILESTREAM 存储之后，你可以将此表与下面的代码示例结合使用。</span><span class="sxs-lookup"><span data-stu-id="40d0d-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="40d0d-117">SQL Server 联机丛书中的资源的链接位于本主题末尾处。</span><span class="sxs-lookup"><span data-stu-id="40d0d-117">The links to resources in SQL Server Books Online are located at the end of this topic.</span></span>  
  
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
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="40d0d-118">示例:读取、 覆盖和插入 FILESTREAM 数据</span><span class="sxs-lookup"><span data-stu-id="40d0d-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>  
 <span data-ttu-id="40d0d-119">下面的示例演示如何从 FILESTREAM 读取数据。</span><span class="sxs-lookup"><span data-stu-id="40d0d-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="40d0d-120">示例代码获取文件的逻辑路径，并将 `FileAccess` 设置为 `Read`，而将 `FileOptions` 设置为 `SequentialScan`。</span><span class="sxs-lookup"><span data-stu-id="40d0d-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="40d0d-121">然后，示例代码将字节从 SqlFileStream 读入到缓存区中，</span><span class="sxs-lookup"><span data-stu-id="40d0d-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="40d0d-122">最后将这些字节写入到控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="40d0d-122">The bytes are then written to the console window.</span></span>  
  
 <span data-ttu-id="40d0d-123">该示例还演示如何将数据写入 FILESTREAM（其中，所有现有的数据都将被覆盖）。</span><span class="sxs-lookup"><span data-stu-id="40d0d-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="40d0d-124">示例代码获取文件的逻辑路径，然后创建 `SqlFileStream`，并将 `FileAccess` 设置为 `Write`，而将 `FileOptions` 设置为 `SequentialScan`。</span><span class="sxs-lookup"><span data-stu-id="40d0d-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="40d0d-125">将一个单字节写入到 `SqlFileStream`，从而替换文件中的任何数据。</span><span class="sxs-lookup"><span data-stu-id="40d0d-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>  
  
 <span data-ttu-id="40d0d-126">该示例还演示了如何通过使用 Seek 方法将数据追加到文件末尾将数据写入 FILESTREAM。</span><span class="sxs-lookup"><span data-stu-id="40d0d-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="40d0d-127">示例代码获取文件的逻辑路径，然后创建 `SqlFileStream`，并将 `FileAccess` 设置为 `ReadWrite`，而将 `FileOptions` 设置为 `SequentialScan`。</span><span class="sxs-lookup"><span data-stu-id="40d0d-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="40d0d-128">示例代码使用 Seek 方法找到文件结尾，并将一个单字节追加到现有的文件中。</span><span class="sxs-lookup"><span data-stu-id="40d0d-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>  
  
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
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))  
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
}
```  
  
 <span data-ttu-id="40d0d-129">另一个示例，请参阅[如何存储和二进制数据提取到文件流列](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str)。</span><span class="sxs-lookup"><span data-stu-id="40d0d-129">For another sample, see [How to store and fetch binary data into a file stream column](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>  
  
## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="40d0d-130">SQL Server 联机丛书中的资源</span><span class="sxs-lookup"><span data-stu-id="40d0d-130">Resources in SQL Server Books Online</span></span>  
 <span data-ttu-id="40d0d-131">FILESTREAM 的完整文档位于 SQL Server 联机丛书中的下列部分中。</span><span class="sxs-lookup"><span data-stu-id="40d0d-131">The complete documentation for FILESTREAM is located in the following sections in SQL Server Books Online.</span></span>  
  
|<span data-ttu-id="40d0d-132">主题</span><span class="sxs-lookup"><span data-stu-id="40d0d-132">Topic</span></span>|<span data-ttu-id="40d0d-133">描述</span><span class="sxs-lookup"><span data-stu-id="40d0d-133">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="40d0d-134">FILESTREAM (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="40d0d-134">FILESTREAM (SQL Server)</span></span>](/sql/relational-databases/blob/filestream-sql-server)|<span data-ttu-id="40d0d-135">介绍何时使用 FILESTREAM 存储以及该存储如何将 SQL Server 数据库引擎与 NTFS 文件系统集成。</span><span class="sxs-lookup"><span data-stu-id="40d0d-135">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|  
|[<span data-ttu-id="40d0d-136">创建 FILESTREAM 数据的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="40d0d-136">Create Client Applications for FILESTREAM Data</span></span>](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|<span data-ttu-id="40d0d-137">介绍用于处理 FILESTREAM 数据的 Win32 API 函数。</span><span class="sxs-lookup"><span data-stu-id="40d0d-137">Describes the Win32 API functions for working with FILESTREAM data.</span></span>|  
|[<span data-ttu-id="40d0d-138">FILESTREAM 与其他 SQL Server 功能</span><span class="sxs-lookup"><span data-stu-id="40d0d-138">FILESTREAM and Other SQL Server Features</span></span>](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|<span data-ttu-id="40d0d-139">提供将 FILESTREAM 数据与 SQL Server 的其他功能一起使用时的注意事项、准则和限制。</span><span class="sxs-lookup"><span data-stu-id="40d0d-139">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40d0d-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="40d0d-140">See also</span></span>
- [<span data-ttu-id="40d0d-141">SQL Server 数据类型和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="40d0d-141">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [<span data-ttu-id="40d0d-142">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="40d0d-142">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="40d0d-143">代码访问安全性和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="40d0d-143">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)
- [<span data-ttu-id="40d0d-144">SQL Server 二进制和大值数据</span><span class="sxs-lookup"><span data-stu-id="40d0d-144">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="40d0d-145">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="40d0d-145">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)
