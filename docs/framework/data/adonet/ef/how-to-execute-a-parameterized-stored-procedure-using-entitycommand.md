---
title: 如何：使用 EntityCommand 执行参数化存储过程
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: 68589cf8906e35313e261e373cf87017ffe6f8f9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a>如何：使用 EntityCommand 执行参数化存储过程
本主题说明如何使用 <xref:System.Data.EntityClient.EntityCommand> 类执行参数化存储过程。  
  
### <a name="to-run-the-code-in-this-example"></a>运行本示例中的代码  
  
1.  添加[School 模型](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)到你的项目和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。 有关详细信息，请参阅[如何： 使用实体数据模型向导](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)。  
  
2.  在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  导入 `GetStudentGrades` 存储过程并将 `CourseGrade` 实体指定为返回类型。 有关如何导入存储的过程的信息，请参阅[如何： 导入存储过程](http://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d)。  
  
## <a name="example"></a>示例  
 下面的代码执行 `GetStudentGrades` 存储过程，其中，`StudentId` 为必需的参数。 然后由 <xref:System.Data.EntityClient.EntityDataReader> 读取结果。  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a>请参阅  
 [用于实体框架的 EntityClient 提供程序](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
