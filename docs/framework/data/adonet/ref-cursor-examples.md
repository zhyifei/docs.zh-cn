---
title: REF CURSOR 示例
ms.date: 03/30/2017
ms.assetid: c257da03-c6c9-4cf8-b591-b7740a962c40
ms.openlocfilehash: dfad86c6d5c99d7a1b99d7cfbde165d5ec39f5f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158933"
---
# <a name="ref-cursor-examples"></a><span data-ttu-id="32478-102">REF CURSOR 示例</span><span class="sxs-lookup"><span data-stu-id="32478-102">REF CURSOR Examples</span></span>
<span data-ttu-id="32478-103">REF CURSOR 示例包括下列三个 Visual Basic 示例，演示如何使用 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="32478-103">The REF CURSOR examples are comprised of the following three Microsoft Visual Basic examples that demonstrate using REF CURSORs.</span></span>  
  
|<span data-ttu-id="32478-104">示例</span><span class="sxs-lookup"><span data-stu-id="32478-104">Sample</span></span>|<span data-ttu-id="32478-105">描述</span><span class="sxs-lookup"><span data-stu-id="32478-105">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="32478-106">OracleDataReader 中的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="32478-106">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)|<span data-ttu-id="32478-107">此示例执行一个 PL/SQL 存储过程，返回 REF CURSOR 参数，并将值作为 <xref:System.Data.OracleClient.OracleDataReader> 读取。</span><span class="sxs-lookup"><span data-stu-id="32478-107">This example executes a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>|  
|[<span data-ttu-id="32478-108">使用 OracleDataReader 从多个 REF CURSOR 中检索数据</span><span class="sxs-lookup"><span data-stu-id="32478-108">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)|<span data-ttu-id="32478-109">此示例执行一个 PL/SQL 存储过程，返回两个 REF CURSOR 参数，并读取使用的值**OracleDataReader**。</span><span class="sxs-lookup"><span data-stu-id="32478-109">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>|  
|[<span data-ttu-id="32478-110">使用一个或多个 REF CURSOR 填充数据集</span><span class="sxs-lookup"><span data-stu-id="32478-110">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)|<span data-ttu-id="32478-111">此示例执行一个 PL/SQL 存储过程，返回两个 REF CURSOR 参数，并使用返回的行填充 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="32478-111">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>|  
  
 <span data-ttu-id="32478-112">要使用这些示例，可能需要创建 Oracle 表，并且必须创建 PL/SQL 包和包正文。</span><span class="sxs-lookup"><span data-stu-id="32478-112">To use these examples, you may need to create the Oracle tables, and you must create a PL/SQL package and package body.</span></span>  
  
## <a name="creating-the-oracle-tables"></a><span data-ttu-id="32478-113">创建 Oracle 表</span><span class="sxs-lookup"><span data-stu-id="32478-113">Creating the Oracle Tables</span></span>  
 <span data-ttu-id="32478-114">这些示例使用 Oracle Scott/Tiger 架构中定义的表。</span><span class="sxs-lookup"><span data-stu-id="32478-114">These examples use tables that are defined in the Oracle Scott/Tiger schema.</span></span> <span data-ttu-id="32478-115">大多数 Oracle 安装均包括 Oracle Scott/Tiger 架构。</span><span class="sxs-lookup"><span data-stu-id="32478-115">The Oracle Scott/Tiger schema is included with most Oracle installations.</span></span> <span data-ttu-id="32478-116">如果此架构不存在，可以使用 {OracleHome}\rdbms\admin\scott.sql 中的 SQL 命令文件创建供这些示例使用的表和索引。</span><span class="sxs-lookup"><span data-stu-id="32478-116">If this schema does not exist, you can use the SQL commands file in {OracleHome}\rdbms\admin\scott.sql to create the tables and indexes used by these examples.</span></span>  
  
## <a name="creating-the-oracle-package-and-package-body"></a><span data-ttu-id="32478-117">创建 Oracle 包和包正文</span><span class="sxs-lookup"><span data-stu-id="32478-117">Creating the Oracle Package and Package Body</span></span>  
 <span data-ttu-id="32478-118">这些示例要求服务器上存在以下 PL/SQL 包和包正文。</span><span class="sxs-lookup"><span data-stu-id="32478-118">These examples require the following PL/SQL package and package body on your server.</span></span> <span data-ttu-id="32478-119">在 Oracle 服务器上创建以下 Oracle 包。</span><span class="sxs-lookup"><span data-stu-id="32478-119">Create the following Oracle package on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS   
    TYPE T_CURSOR IS REF CURSOR;   
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,   
                               IO_CURSOR IN OUT T_CURSOR);   
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
                                DEPTCURSOR OUT T_CURSOR);  
END CURSPKG;  
/   
```  
  
 <span data-ttu-id="32478-120">在 Oracle 服务器上创建下面的 Oracle 包正文。</span><span class="sxs-lookup"><span data-stu-id="32478-120">Create the following Oracle package body on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE BODY CURSPKG AS  
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,  
                               IO_CURSOR IN OUT T_CURSOR)  
    IS   
        V_CURSOR T_CURSOR;   
    BEGIN   
        IF N_EMPNO <> 0   
        THEN  
             OPEN V_CURSOR FOR   
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME   
                  FROM EMP, DEPT   
                  WHERE EMP.DEPTNO = DEPT.DEPTNO   
                  AND EMP.EMPNO = N_EMPNO;  
  
        ELSE   
             OPEN V_CURSOR FOR   
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME   
                  FROM EMP, DEPT   
                  WHERE EMP.DEPTNO = DEPT.DEPTNO;  
  
        END IF;  
        IO_CURSOR := V_CURSOR;   
    END OPEN_ONE_CURSOR;   
  
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,  
                                DEPTCURSOR OUT T_CURSOR)  
    IS   
        V_CURSOR1 T_CURSOR;   
        V_CURSOR2 T_CURSOR;   
    BEGIN   
        OPEN V_CURSOR1 FOR SELECT * FROM EMP;  
        OPEN V_CURSOR2 FOR SELECT * FROM DEPT;  
        EMPCURSOR  := V_CURSOR1;   
        DEPTCURSOR := V_CURSOR2;   
    END OPEN_TWO_CURSORS;   
END CURSPKG;  
/  
```  
  
## <a name="see-also"></a><span data-ttu-id="32478-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="32478-121">See also</span></span>

- [<span data-ttu-id="32478-122">Oracle REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="32478-122">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)
- [<span data-ttu-id="32478-123">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="32478-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
