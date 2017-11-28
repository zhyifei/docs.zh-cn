---
title: Oracle BFILE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f48bd85559d55d9a1190310bcf13cd4a68625011
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-bfiles"></a><span data-ttu-id="26573-102">Oracle BFILE</span><span class="sxs-lookup"><span data-stu-id="26573-102">Oracle BFILEs</span></span>
<span data-ttu-id="26573-103">Oracle .NET Framework 数据提供程序包括 <xref:System.Data.OracleClient.OracleBFile> 类，该类用于使用 Oracle <xref:System.Data.OracleClient.OracleType.BFile> 数据类型。</span><span class="sxs-lookup"><span data-stu-id="26573-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="26573-104">Oracle **BFILE**数据类型是一种 Oracle **LOB**数据类型，包含最大大小为 4 千兆字节的二进制数据的引用。</span><span class="sxs-lookup"><span data-stu-id="26573-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="26573-105">Oracle **BFILE**不同于其他 Oracle **LOB**数据类型，因为其数据存储在服务器上的物理文件中而不是操作系统。</span><span class="sxs-lookup"><span data-stu-id="26573-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="26573-106">请注意， **BFILE**数据类型提供对数据的只读访问。</span><span class="sxs-lookup"><span data-stu-id="26573-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="26573-107">其他特征**BFILE**将它从区分开来的数据类型**LOB**数据类型是：</span><span class="sxs-lookup"><span data-stu-id="26573-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
-   <span data-ttu-id="26573-108">包含非结构化数据。</span><span class="sxs-lookup"><span data-stu-id="26573-108">Contains unstructured data.</span></span>  
  
-   <span data-ttu-id="26573-109">支持服务器端分块。</span><span class="sxs-lookup"><span data-stu-id="26573-109">Supports server-side chunking.</span></span>  
  
-   <span data-ttu-id="26573-110">使用引用复制语义。</span><span class="sxs-lookup"><span data-stu-id="26573-110">Uses reference copy semantics.</span></span> <span data-ttu-id="26573-111">例如，如果在执行复制操作**BFILE**，则只**BFILE**复制定位符 （这是对文件的引用）。</span><span class="sxs-lookup"><span data-stu-id="26573-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="26573-112">而不会复制文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="26573-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="26573-113">**BFILE**数据类型应该用于引用尺寸，较大的 Lob，因此不可行，在数据库中存储。</span><span class="sxs-lookup"><span data-stu-id="26573-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="26573-114">更多的客户端、 服务器和通信系统开销时所涉及的使用**BFILE**数据类型与比较**LOB**数据类型。</span><span class="sxs-lookup"><span data-stu-id="26573-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="26573-115">它会更加高效访问**BFILE**如果你只需以获取少量的数据。</span><span class="sxs-lookup"><span data-stu-id="26573-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="26573-116">如果需要获取整个对象，访问数据库驻留的 LOB 会更加有效。</span><span class="sxs-lookup"><span data-stu-id="26573-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="26573-117">每个非 NULL **OracleBFile**对象都与两个定义基础物理文件的位置的实体关联：</span><span class="sxs-lookup"><span data-stu-id="26573-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1.  <span data-ttu-id="26573-118">一个 Oracle DIRECTORY 对象，它是文件系统中一个目录的数据库别名，以及</span><span class="sxs-lookup"><span data-stu-id="26573-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2.  <span data-ttu-id="26573-119">基础物理文件的文件名，它位于与 DIRECTORY 对象关联的目录中。</span><span class="sxs-lookup"><span data-stu-id="26573-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26573-120">示例</span><span class="sxs-lookup"><span data-stu-id="26573-120">Example</span></span>  
 <span data-ttu-id="26573-121">下面的 C# 示例演示如何创建**BFILE**在 Oracle 表，然后检索它的形式**OracleBFile**对象。</span><span class="sxs-lookup"><span data-stu-id="26573-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="26573-122">该示例演示如何使用<xref:System.Data.OracleClient.OracleDataReader>对象和**OracleBFile** **Seek**和**读取**方法。</span><span class="sxs-lookup"><span data-stu-id="26573-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="26573-123">请注意，若要使用此示例，你必须首先创建一个名为目录"c:\\\bfiles"和 Oracle 服务器上名为"MyFile.jpg"的文件。</span><span class="sxs-lookup"><span data-stu-id="26573-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =   
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =   
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =   
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="26573-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26573-124">See Also</span></span>  
 [<span data-ttu-id="26573-125">Oracle 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="26573-125">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="26573-126">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="26573-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
